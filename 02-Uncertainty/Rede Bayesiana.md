# Redes Bayesianas e Inferência Probabilística

Uma **Rede Bayesiana** é uma estrutura de dados grafo-direcionada usada para representar as dependências probabilísticas entre variáveis aleatórias.

---

## 1. Propriedades de uma Rede Bayesiana

* **Grafo Acíclico Dirigido (DAG):** Composto por nós (variáveis) e arestas direcionadas (relações de dependência).
* **[Node](../00-Search/Node.md)(Nós):** Cada nó representa uma variável aleatória (discreta ou contínua).
* **Arestas (Relações Pai-Filho):** Uma seta de $X$ para $Y$ ($X \to Y$) indica que $X$ é pai de $Y$. A distribuição de probabilidade de $Y$ depende diretamente do valor de $X$.
* **Distribuição de Probabilidade Condicional (CPT):** Cada nó $X$ possui uma tabela associada dada por $P(X \mid \text{Pais}(X))$.

---

## 2. Exemplo Prático: Chegar a um Compromisso no Horário

Considere um sistema que modela os fatores que influenciam a chegada a um compromisso no horário.

![Rede Bayesiana - example 1](../PNGs/02-Uncertainly.png/Rede%20Bayesiana%20-%20example%201.png)
### Estrutura e Tabelas de Probabilidade

#### A. Chuva ($R$) — Nó Raiz

Nó sem pais; sua distribuição de probabilidade não depende de eventos prévios no modelo.

* **Valores:** $\{\text{nenhuma}, \text{fraca}, \text{forte}\}$

| $R$ (Chuva) | $P(R)$ |
| --- | --- |
| Nenhuma | $0.70$ |
| Fraca | $0.20$ |
| Forte | $0.10$ |

#### B. Manutenção ($M$)

Indica se há manutenção nos trilhos do trem. É filho direto de $R$ ($R \to M$).

* **Valores:** $\{\text{sim}, \text{não}\}$

| $R$ (Chuva) | $P(M = \text{sim} \mid R)$ | $P(M = \text{não} \mid R)$ |
| ----------- | -------------------------- | -------------------------- |
| Nenhuma     | $0.40$                     | $0.60$                     |
| Fraca       | $0.20$                     | $0.80$                     |
| Forte       | $0.10$                     | $0.90$                     |

#### C. Trem ($T$)

Representa se o trem está no horário ou atrasado. Possui dois pais: $R$ e $M$ ($R \to T$ e $M \to T$).

* **Valores:** $\{\text{no horário}, \text{atrasado}\}$

| $R$ (Chuva) | $M$ (Manutenção) | $P(T = \text{no horário} \mid R, M)$ | $P(T = \text{atrasado} \mid R, M)$ |
| --- | --- | --- | --- |
| Nenhuma | Sim | $0.80$ | $0.20$ |
| Nenhuma | Não | $0.90$ | $0.10$ |
| Fraca | Sim | $0.60$ | $0.40$ |
| Fraca | Não | $0.70$ | $0.30$ |
| Forte | Sim | $0.40$ | $0.60$ |
| Forte | Não | $0.50$ | $0.50$ |

#### D. Compromisso ($A$)

Representa o comparecimento ao compromisso. Seu único pai direto é o Trem ($T \to A$).

* **Valores:** $\{\text{comparece}, \text{perde}\}$

| $T$ (Trem) | $P(A = \text{comparece} \mid T)$ | $P(A = \text{perde} \mid T)$ |
| --- | --- | --- |
| No horário | $0.90$ | $0.10$ |
| Atrasado | $0.60$ | $0.40$ |

> **Independência Condicional Relevante:** Os pais de um nó incluem apenas relações **diretas**. A chuva e a manutenção afetam se o trem atrasa, mas o que afeta diretamente o comparecimento ao compromisso é o estado final do trem. Se já sabemos que o trem chegou no horário, o estado da chuva torna-se irrelevante para prever a presença no compromisso.

---

### Cálculo da [Probabilidade Conjunta (Joint Probability)](./Probabilidade%20Conjunta%20(Joint%20Probability).md)

Para determinar a probabilidade de um estado completo do sistema — por exemplo, a probabilidade de perder o compromisso quando o trem atrasou, em um dia com chuva fraca e sem manutenção:

$$P(R = \text{fraca}, M = \text{não}, T = \text{atrasado}, A = \text{perde})$$

Aplica-se a **regra da cadeia para Redes Bayesianas**:

$$P(R, M, T, A) = P(R) \cdot P(M \mid R) \cdot P(T \mid R, M) \cdot P(A \mid T)$$

Substituindo os valores das tabelas:

$$P(\text{fraca}, \text{não}, \text{atrasado}, \text{perde}) = 0.20 \times 0.80 \times 0.30 \times 0.40 = 0.0192 \quad (1.92\%)$$

---

## 3. Inferência Probabilística

A inferência nos permite calcular a distribuição de probabilidade de variáveis não observadas com base em evidências parciais.

### Componentes de uma Consulta de Inferência

* **Variável de Consulta ($X$):** A variável cuja distribuição de probabilidade desejamos calcular (ex: $T = \text{Trem}$).
* **Variáveis de Evidência ($E$):** Variáveis que foram observadas com valores fixos $e$ (ex: $R = \text{fraca}$).
* **Variáveis Ocultas/Escondidas ($Y$):** Variáveis não observadas e que não fazem parte da consulta (ex: $M = \text{Manutenção}$).
* **Objetivo:** Calcular a distribuição posterior $P(X \mid e)$.

### Exemplo de Inferência por Marginalização

Queremos calcular $P(A \mid R = \text{fraca}, M = \text{não})$. Como o nó $A$ não é filho direto de $R$ ou $M$, inserimos a variável intermediária (oculta) $T$ somando sobre todos os seus valores possíveis (**marginalização**):

$$P(A \mid \text{fraca}, \text{não}) = \alpha \cdot P(A, \text{fraca}, \text{não})$$

Onde $\alpha$ é uma constante de normalização, e:

$$P(A, \text{fraca}, \text{não}) = \sum_{t \in T} P(A, \text{fraca}, \text{não}, t)$$

$$P(A, \text{fraca}, \text{não}) = P(A, \text{fraca}, \text{não}, \text{no horário}) + P(A, \text{fraca}, \text{não}, \text{atrasado})$$

---

## 4. Inferência por Enumeração

A **Inferência por Enumeração** é o algoritmo genérico para obter a distribuição de uma variável $X$, dados os dados de evidência $e$ e as variáveis ocultas $Y$:

![Rede Bayesiana - example 2](../PNGs/02-Uncertainly.png/Rede%20Bayesiana%20-%20example%202.png)

### Explicação do Algoritmo:

1. **União de Termos:** Avalia-se a probabilidade conjunta da consulta $X$, da evidência $e$ e de cada combinação de valores $y$ das variáveis ocultas $Y$.
2. **Somatório (Marginalização):** Soma-se o produto de todas as distribuições ao longo das variáveis ocultas $Y$.
3. **Normalização ($\alpha$):** Garante que a soma das probabilidades finais de todos os valores possíveis de $X$ seja igual a $1$ ($\sum P(X = x \mid e) = 1$).

---
Related: [Probability](./Probability.md)
Related: [Inference](../01-Knowledge/Inference.md) [Inference Rules](../01-Knowledge/Inference%20Rules.md)
