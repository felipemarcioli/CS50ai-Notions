# Regras de Probabilidade

## 1. Negação (Complementar)

![Probability rules - example 1](../PNGs/02-Uncertainly.png/Probability%20rules%20-%20example%201.png)

**Conceito:** A probabilidade do complemento de um evento $a$ é igual a $1$ menos a probabilidade do evento ocorrer. Isso decorre do axioma de que a soma das probabilidades de todos os mundos possíveis é igual a $1$. Como os literais complementares $a$ e $\neg a$ cobrem a totalidade dos mundos possíveis de forma disjunta, temos:

---

## 2. Princípio da Inclusão-Exclusão

![Probability rules - example 2](../PNGs/02-Uncertainly.png/Probability%20rules%20-%20example%202.png)

**Conceito:** A probabilidade de ocorrer $a$ ou $b$ é dada pela soma das probabilidades individuais de $a$ e de $b$. Contudo, ao somá-las, os mundos onde $a$ e $b$ ocorrem simultaneamente são contabilizados duas vezes. Para corrigir essa sobreposição, subtrai-se uma vez a probabilidade da intersecção $P(a \land b)$.

> **Exemplo Prático:**  
> Suponha que eu coma sorvete em 80% dos dias ($P(\text{sorvete}) = 0{,}8$) e biscoitos em 70% dos dias ($P(\text{biscoito}) = 0{,}7$). Se calcularmos a probabilidade de eu comer sorvete **ou** biscoito sem subtrair a intersecção, obtemos:
> 
> $$0{,}8 + 0{,}7 = 1{,}5$$
> 
> Isso viola o axioma fundamental de que a probabilidade varia entre 0 e 1 ($0 \le P(E) \le 1$). Para corrigir a contagem dupla dos dias em que consumo ambos, devemos subtrair $P(\text{sorvete} \land \text{biscoito})$ uma vez.

---

## 3. Marginalização (Soma das Probabilidades)

### Caso Booleano
![Probability rules - example 3](../PNGs/02-Uncertainly.png/Probability%20rules%20-%20example%203.png)

**Conceito:** Como $b$ e $\neg b$ são eventos mutuamente exclusivos (disjuntos) e exaustivos ($P(b \land \neg b) = 0$ e $P(b) + P(\neg b) = 1$), o evento $a$ só pode ocorrer em conjunto com $b$ ou em conjunto com $\neg b$. A probabilidade marginal de $a$ é, portanto, a soma das probabilidades conjuntas.

### Caso Geral (Variáveis Aleatórias Discretas)
![Probability rules - example 4](../PNGs/02-Uncertainly.png/Probability%20rules%20-%20example%204.png)

* O lado esquerdo representa a probabilidade de a variável aleatória $X$ assumir o valor $x_i$.
* O lado direito expressa a marginalização: $P(X = x_i)$ é a soma de todas as probabilidades conjuntas de $x_i$ combinada com cada valor possível $y_j$ da variável $Y$.

> **Exemplo:**  
> Seja $C$ a variável que indica presença de nuvens de manhã ($C \in \{\text{nuvem}, \neg\text{nuvem}\}$) e $R$ a ocorrência de chuva ($R \in \{\text{chuva}, \neg\text{chuva}\}$):

![Probability rules - example 5](../PNGs/02-Uncertainly.png/Probability%20rules%20-%20example%205.png)

---

## 4. Condicionamento (Lei da Probabilidade Total)

### Caso Booleano
![Probability rules - example 6](../PNGs/02-Uncertainly.png/Probability%20rules%20-%20example%206.png)

### Caso Geral (Variáveis Aleatórias Discretas)
![Probability rules - example 7](../PNGs/02-Uncertainly.png/Probability%20rules%20-%20example%207.png)

**Conceito:** A probabilidade de $X = x_i$ é calculada somando a probabilidade condicional de $X = x_i$ dado cada valor $y_j$ da variável $Y$, multiplicada pela probabilidade marginal do respectivo valor de $Y$.

A conexão com a marginalização fica evidente ao lembrar da definição de probabilidade condicional:

$$P(a \mid b) = \frac{P(a, b)}{P(b)} \implies P(a \mid b)P(b) = P(a, b)$$

Substituindo essa relação na fórmula do condicionamento, reobtemos exatamente a fórmula da marginalização:

$$P(a) = P(a, b) + P(a, \neg b)$$

---
Related: [Probability](./Probability.md)
Related: [Logica proposicional](../01-Knowledge/Logica%20proposicional.md)