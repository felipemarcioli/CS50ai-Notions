Um **Modelo Oculto de Markov (HMM - _Hidden Markov Model_)** resolve um problema muito comum em inteligência artificial: **quando a IA precisa entender o que está acontecendo no mundo, mas não consegue ver a realidade diretamente — apenas seus efeitos indiretos.**

É como tentar adivinhar a causa olhando apenas para o sintoma.

---
## 1. O Conceito Fundamental: Duas Camadas

Enquanto em uma Cadeia de Markov comum tudo é visível, no HMM o sistema é dividido em duas camadas paralelas:

![HMM - example 1](../PNGs/02-Uncertainly.png/HMM%20-%20example%201.png)

1. **Estado Oculto ($X_t$):** A realidade que a IA **não consegue ver diretamente** (ex: o clima lá fora, a posição exata de um robô, as palavras pensadas por alguém).
    
2. **Observação/Evidência ($E_t$):** O sinal que a IA **pode medir** (ex: pessoas com guarda-chuva no saguão, dados de um sensor laser, ondas de áudio de um microfone).

---
## 2. As Duas Regras Matemáticas do HMM

Para um HMM funcionar, ele precisa de dois modelos probabilísticos trabalhando juntos:

### A. Modelo de Transição ($P(X_{t+1} \mid X_t)$)

Como o **estado oculto muda ao longo do tempo**. É a mesma regra da Cadeia de Markov comum:

- Se hoje é _Sol_, a chance de amanhã ser _Sol_ é 80% e _Chuva_ é 20%.


### B. Modelo de Emissão ou Sensor ($P(E_t \mid X_t)$)

Qual é a chance de ver uma **observação** específica dado o **estado oculto** atual.

- Se estiver **Sol**, a chance de ver pessoas com guarda-chuva é baixa ($20\%$), e sem guarda-chuva é alta ($80\%$).
    
- Se estiver **Chuva**, a chance de ver pessoas com guarda-chuva é alta ($90\%$), e sem guarda-chuva é baixa ($10\%$).
    

> **Assunção do Sensor de Markov:** O modelo assume que a observação de hoje depende _exclusivamente_ do estado de hoje. O fato de alguém trazer guarda-chuva depende apenas do clima de hoje, ignorando outros fatores como a personalidade da pessoa.

---
## 3. O que podemos fazer com um HMM? (As 4 Tarefas)

Com esses dois modelos em mãos, a IA pode resolver quatro tipos de problemas:

- **Filtragem (Filtration):** Descobrir o estado **atual** com base no histórico até agora.
    
    - _Exemplo:_ Com base nos guarda-chuvas de segunda até hoje, está chovendo **hoje**?
        
- **Previsão (Prediction):** Estimar um estado **futuro**.
    
    - _Exemplo:_ Qual a chance de chover **depois de amanhã**?
        
- **Suavização (Smoothing):** Reavaliar um estado **passado** com dados que você obteve depois.
    
    - _Exemplo:_ Sabendo que hoje todos trouxeram guarda-chuva, qual era a chance real de ter chovido **ontem**?
        
- **Explicação Mais Provável (Most Likely Explanation):** Dada toda a sequência de observações, reconstruir a **sequência completa de estados ocultos** mais provável.
    
    - _Exemplo:_ Mapear a sequência de clima de uma semana inteira a partir dos guarda-chuvas vistos a cada dia. 

---
Related: [Markov Models](./Markov%20Models.md)