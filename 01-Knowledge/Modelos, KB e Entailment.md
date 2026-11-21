### 1. Modelo (Model) — O "Estado do Mundo"

- **Definição Técnica:** É uma função matemática/mapeamento que atribui um valor de verdade (**True** ou **False**) a cada proposição atômica do sistema.
    
- **O que representa na prática:** Representa uma **hipótese completa sobre como o mundo é**. Cada modelo é um "universo paralelo" possível dentro do problema.

#### Como funciona a atribuição:

Se temos as proposições:
- $P$: _"Está chovendo"_
    
- $Q$: _"É terça-feira"_

Um modelo específico $M_1 = \{P = \text{True}, Q = \text{False}\}$ descreve a situação: _"Está chovendo e não é terça-feira"_.

#### 🔢 A Regra dos Espaços de Estados ($2^N$)

O número de modelos cresce exponencialmente com a quantidade de proposições ($N$):

$$\text{Número de Modelos} = 2^N$$

- **1 proposição:** $2^1 = 2$ modelos ($\text{True}$ ou $\text{False}$)
    
- **2 proposições:** $2^2 = 4$ modelos
    
- **10 proposições:** $2^{10} = 1.024$ modelos possíveis!

|**Modelo**|**P (Chovendo)**|**Q (Terça)**|**Descrição do "Mundo"**|
|---|---|---|---|
|**$M_1$**|**True**|**True**|Chove e é terça|
|**$M_2$**|**True**|**False**|Chove e não é terça|
|**$M_3$**|**False**|**True**|Não chove e é terça|
|**$M_4$**|**False**|**False**|Não chove e não é terça|

#### 💡 Papel do Modelo no Raciocínio da IA

1. **Satisfazibilidade:** Dizemos que um modelo $M$ _satisfaz_ uma sentença $\alpha$ (ou é um "modelo de $\alpha$") se $\alpha$ for **True** sob as atribuições desse modelo. Notação: $M(\alpha) = \text{True}$.
    
2. **O Conjunto $M(KB)$:** A _Base de Conhecimento_ (KB) é apenas um filtro sobre esses modelos. O objetivo da IA é pegar todos os $2^N$ modelos possíveis e eliminar aqueles que violam as regras da KB, ficando apenas com os modelos que **satisfazem a KB**.

---
## 2. Base de Conhecimento (Knowledge Base - KB)

- **Definição:** Conjunto de sentenças em lógica proposicional fornecidas a um agente inteligente sobre a realidade.
    
- **Função:** Representa tudo o que o sistema sabe sobre o mundo e serve para descartar modelos que sejam biologicamente/logicamente impossíveis.

---
## 3. Acarretamento / Implicação Semântica (Entailment - $\models$)

- **Definição:** Relação lógica onde $\alpha \models \beta$ ($\alpha$ acarreta $\beta$) significa que **em qualquer modelo onde $\alpha$ é verdadeiro, $\beta$ também é obrigatoriamente verdadeiro**.
    
- **Exemplo:**
    
    - $\alpha$: _"É uma terça-feira de janeiro"_
        
    - $\beta$: _"É janeiro"_
        
    - Relação: $\alpha \models \beta$ (Se $\alpha$ for verdade, $\beta$ é inevitavelmente verdade).
        

### Diferença Fundamental:

- **Implicação ($\rightarrow$):** Conectivo lógico entre duas proposições simples (ex: $P \rightarrow Q$). É uma regra dentro de uma frase.
    
- **Entailment ($\models$):** Relação semântica de garantia de verdade. Significa que a conclusão $\beta$ decorre logicamente das informações de $\alpha$.

---
**Related:** [Logica proposicional](./Logica%20proposicional.md)