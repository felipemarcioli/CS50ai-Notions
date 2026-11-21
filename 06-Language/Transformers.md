# Arquitetura Transformer

> [!NOTE] **Resumo**
> A arquitetura **Transformer** (introduzida no artigo *"Attention Is All You Need"*, 2017) revolucionou o Processamento de Linguagem Natural (NLP) e a IA generativa ao substituir redes recorrentes (RNNs/LSTMs) e convoluções pelo processamento **totalmente paralelo** baseado no mecanismo de **Atenção**. Diferente de modelos estáticos como o **[word2vec](./word2vec.md)**, o Transformer gera **embeddings contextualizados**, alterando dinamicamente o vetor de cada token de acordo com a frase ao redor.

---

## 1. Pré-processamento Vetorial

Antes de entrar nas camadas neurais, o texto bruto passa por três etapas:

1. **[Tokenizacao](./Tokenizacao.md):** Quebra o texto em subpalavras (tokens) usando algoritmos como **BPE** (*Byte-Pair Encoding*).
2. **Input Embeddings:** Mapeia cada token para um vetor denso de dimensão $d_{\text{model}}$ (ex.: $512$, $4096$ ou $8192$).
3. **Positional Encoding (Codificação Posicional):** Injeta a noção de ordem na sequência, já que todos os tokens entram simultaneamente.
   - **Original (2017):** Funções seno e cosseno de diferentes frequências somadas ao embedding.
   - **LLMs Modernos:** Utilizam **RoPE** (*Rotary Position Embedding*), que rotaciona os vetores no espaço complexo para codificar a distância relativa entre tokens (usado em Llama, Qwen, Gemma).

---

## 2. Scaled Dot-Product Attention (Self-Attention)

O mecanismo de **Autoatenção** permite que cada token avalie a relevância de todos os outros tokens da sequência para construir seu próprio significado contextual.

Para cada token, o vetor de entrada $X$ é multiplicado por três matrizes de pesos aprendíveis ($W^Q, W^K, W^V$), gerando três vetores:

- **Query ($Q$ - Consulta):** O que este token está procurando nos outros?
- **Key ($K$ - Chave):** O que este token oferece como identificação/contexto?
- **Value ($V$ - Valor):** Qual é o conteúdo semântico transmitido se este token receber atenção?

### Equação Fundamental

$$\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V$$

#### Passo a passo:
1. **Produto Escalar ($QK^T$):** Mede a similaridade entre a *Query* de um token e a *Key* de todos os outros.
2. **Escalonamento ($\frac{1}{\sqrt{d_k}}$):** Divide pela raiz quadrada da dimensão das chaves ($d_k$) para evitar gradientes próximos de zero na *softmax* durante o treinamento.
3. **Softmax:** Converte as pontuações em pesos de probabilidade que somam $1$.
4. **Ponderação por $V$:** Multiplica os pesos pelos vetores *Value*, gerando um novo vetor enriquecido com o contexto da frase.

> [!TIP] Multi-Head Attention (Atenção Multi-Cabeças)
> Em vez de calcular a atenção uma única vez, o modelo divide os vetores em $h$ cabeças paralelas (ex.: 8, 32 ou 128). Cada cabeça especializa-se em um padrão diferente (sintaxe, resolução de pronomes, semântica). Ao final, todas as cabeças são concatenadas e projetadas novamente.

---

## 3. Anatomia de um Bloco Transformer

Um bloco Transformer empilha duas subcamadas principais, ambas envolvidas por **Conexões Residuais** (`x + Sublayer(x)`) e normalização (**LayerNorm** ou **RMSNorm**) para estabilizar redes profundas:

1. **Camada de Atenção:** Mistura informações *entre* os diferentes tokens da sequência.
2. **Feed-Forward Network (FFN / MLP):** Rede neural densa aplicada *individualmente* a cada token (sem comunicação entre posições), utilizando funções de ativação como **GELU** ou **SwiGLU**. É onde o modelo aplica transformações não lineares e armazena grande parte do conhecimento factual.

---

## 4. Variantes Arquiteturais

| Arquitetura | Componentes | Mecanismo de Atenção | Exemplos | Uso Principal |
| :--- | :--- | :--- | :--- | :--- |
| **Encoder-Only** | Apenas Encoder | **Bidirecional** (vê tokens anteriores e posteriores) | BERT, RoBERTa | Classificação, busca semântica, embeddings |
| **Encoder-Decoder** | Encoder + Decoder | Bidirecional no Encoder + **Cross-Attention** no Decoder | T5, Whisper, BART | Tradução, transcrição de áudio, resumo |
| **Decoder-Only** | Apenas Decoder | **Causal / Masked** (vê apenas si mesmo e anteriores) | GPT, Llama, Qwen, Gemma | Geração de texto, chat, código, raciocínio |

---

## 5. Inferência Autoregressiva (Geração de Texto)

Nos LLMs modernos (*Decoder-Only*), aplica-se uma **máscara causal** triangular na matriz de atenção para impedir que o token na posição $t$ veja posições futuras ($t+1, t+2 \dots$).

1. **Prefill:** O prompt inteiro é processado em paralelo; as matrizes $K$ e $V$ são salvas na VRAM da GPU como **KV Cache** para evitar recálculos nos passos seguintes.
2. **Projeção (LM Head):** O último vetor oculto passa por uma camada linear + *Softmax*, gerando probabilidades para todo o vocabulário.
3. **Amostragem (Sampling):** Parâmetros como *Temperature*, *Top-K* e *Top-P* selecionam o próximo token.
4. **Loop Autoregressivo:** O token escolhido é anexado à entrada e o processo repete-se um token por vez até gerar o token de parada (`<EOS>`).

> [!warning] Gargalo Quadrático $\mathcal{O}(n^2)$
> Como cada token é comparado com todos os outros na matriz $QK^T$, o custo computacional e de memória cresce **quadraticamente** com o tamanho do contexto ($n$). Dobrar o contexto quadruplica o custo da atenção — razão pela qual otimizações como **FlashAttention** (gerenciamento de SRAM na GPU) e **GQA** (*Grouped-Query Attention*) são indispensáveis em modelos modernos.