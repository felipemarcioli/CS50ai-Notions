## 1. O Problema do Tempo e a Assunção de Markov

Até agora, em [Probability](./Probability.md) tradicional ou [Rede Bayesiana](./Rede%20Bayesiana.md) atemporais, calculávamos a chance de um evento com base em condições fixas. Mas o mundo real muda com o tempo ($t$).

Representamos o tempo em passos:

- $X_t$: O estado no momento **atual** (ex: clima de hoje).
    
- $X_{t+1}$: O estado no **próximo** momento (ex: clima de amanhã).
    
- $X_{t+2}$: O estado **depois de amanhã**.
    

### O que é a Assunção de Markov?

Historicamente, o clima de hoje foi influenciado pelo clima de ontem, que foi influenciado pelo de anteontem, e assim por diante até o início dos tempos. Analisar todo o histórico é computacionalmente inviável.

A **Assunção de Markov (Propriedade de Markov)** faz uma simplificação inteligente:

> **O futuro depende APENAS do presente, e não do passado.**

Ou seja, para prever o clima de amanhã ($X_{t+1}$), você **só precisa saber o clima de hoje ($X_t$)**. O que aconteceu há 100 dias não importa diretamente.

Em linguagem matemática (para um Modelo de Markov de 1ª ordem):

$$P(X_{t+1} \mid X_t, X_{t-1}, X_{t-2}, \dots) = P(X_{t+1} \mid X_t)$$

---

## 2. Cadeia de Markov e Matriz de Transição

Uma **Cadeia de Markov** é a sequência dessas mudanças de estado ao longo do tempo. Para construir essa cadeia, precisamos de um **Modelo de Transição** (as regras de mudança).

Voltando ao exemplo do clima (com estados: Sol e Chuva):

- Se hoje está **Sol** ($X_t = \text{sol}$):
    
    - Chance de amanhã fazer **Sol**: $0.8$ ($80\%$)
        
    - Chance de amanhã **Chover**: $0.2$ ($20\%$)
        
- Se hoje está **Chuva** ($X_t = \text{chuva}$):
    
    - Chance de amanhã fazer **Sol**: $0.3$ ($30\%$)
        
    - Chance de amanhã **Chover**: $0.7$ ($70\%$)
        

Essas regras formam a **Matriz de Transição de Probabilidades**:

![Markov - example 1](../PNGs/02-Uncertainly.png/Markov%20-%20example%201.png)

_A soma das probabilidades de cada linha é sempre $1.0$ ($100\%$)._

---

## 3. Como calcular a probabilidade na prática

Se hoje está **Chuva** ($X_0 = \text{chuva}$), qual é a probabilidade de termos 3 dias seguidos de chuva ($X_1 = \text{chuva}$ e $X_2 = \text{chuva}$)?

Basta multiplicar as probabilidades de transição passo a passo usando a Regra da Cadeia:

$$P(X_1=\text{chuva}, X_2=\text{chuva} \mid X_0=\text{chuva}) = P(X_1=\text{chuva} \mid X_0=\text{chuva}) \times P(X_2=\text{chuva} \mid X_1=\text{chuva})$$

$$0.7 \times 0.7 = 0.49 \quad (49\%)$$

---

## Por que os Modelos de Markov são úteis?

1. **Previsão de Séries Temporais:** Mercado financeiro (altas e baixas de ações), previsão do tempo.
    
2. **Processamento de Linguagem Natural (PLN):** Corretores ortográficos e geradores de texto básicos prevêem a próxima palavra com base na palavra atual ($P(\text{palavra}_{t+1} \mid \text{palavra}_t)$).
    
3. **Bioinformática:** Análise de sequências de DNA e proteínas.