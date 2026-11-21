## O que é Probabilidade Conjunta?

A **probabilidade conjunta** (_Joint Probability_) representa a probabilidade de **dois ou mais eventos acontecerem ao mesmo tempo**.

### Exemplo
Considere dois eventos:

- **C** = Há nuvens pela manhã.
- **R** = Chove à tarde.

Sabemos apenas as probabilidades individuais:
###### Probabilidade de nuvens pela manhã

| Evento          | Probabilidade |
| --------------- | ------------- |
| C = Nuvens      | 0.4           |
| ¬C = Sem nuvens | 0.6           |

###### Probabilidade de chuva à tarde

|                |               |
| -------------- | ------------- |
| Evento         | Probabilidade |
| R = Chuva      | 0.1           |
| ¬R = Sem chuva | 0.9           |

---
## O problema

Com essas probabilidades **não conseguimos saber** se a presença de nuvens pela manhã influencia a chance de chover à tarde.

Por exemplo:
- As nuvens aumentam a chance de chuva?
- Não fazem diferença?
- Ou até diminuem essa chance?

As probabilidades individuais não respondem essas perguntas.

Para entender a relação entre os eventos, precisamos analisar a **probabilidade conjunta**.

---
# Tabela de Probabilidade Conjunta

|                     | R = Chuva | ¬R = Sem chuva |
| ------------------- | --------- | -------------- |
| **C = Nuvens**      | **0.08**  | **0.32**       |
| **¬C = Sem nuvens** | **0.02**  | **0.58**       |
Cada célula representa a probabilidade de **dois eventos ocorrerem simultaneamente**.

### Exemplos:
- **P(C ∧ R) = 0.08**
    - Há nuvens pela manhã **e** chove à tarde.
- **P(C ∧ ¬R) = 0.32**
    - Há nuvens pela manhã **e** não chove à tarde.
- **P(¬C ∧ R) = 0.02**
    - Não há nuvens pela manhã **e** chove à tarde.
- **P(¬C ∧ ¬R) = 0.58**
    - Não há nuvens pela manhã **e** não chove à tarde.

Observe que todas as probabilidades da tabela somam **1**, pois representam todos os cenários possíveis.
	0.08 + 0.32 + 0.02 + 0.58 = 1  


---
# Resumo

- **P(A)** → Probabilidade de A acontecer.
- **¬A** → Não A.
- **A ∧ B** → A **e** B acontecem juntos.
- **P(A ∧ B)** → Probabilidade conjunta.
- **A | B** → A **dado que** B aconteceu.
- **P(A | B)** → Probabilidade condicional.
- A probabilidade condicional é calculada por:

```
P(A | B) = P(A ∧ B) / P(B)
```

A ideia principal é simples:

> Primeiro observamos todos os cenários possíveis (probabilidade conjunta). Depois, quando recebemos uma nova informação ("sabemos que B aconteceu"), ignoramos todos os casos incompatíveis e recalculamos as probabilidades apenas entre os cenários restantes.

---
Related: [Probability](./Probability.md)