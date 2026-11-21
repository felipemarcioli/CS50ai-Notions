Existem várias maneiras de inferir novos conhecimentos com base no conhecimento existente. Primeiro, vamos considerar o algoritmo **de verificação de modelos**.

- Para determinar se **KB ⊨ α** (em outras palavras, respondendo à pergunta: “podemos concluir que α é verdadeiro com base em nossa base de conhecimento”)

    - Enumerar todos os modelos possíveis.
    
    - Se em todos os modelos onde KB é verdadeiro, α é verdade também, então KB implica α (KB ⊨ α).

---
## Exemplo de Model Checking (verificação de modelos)

P: É uma terça-feira. 
Q: Está chovendo. 
R: Harry vai correr. 
KB: (P ∧ ¬Q) → R (em palavras, P e não Q implica R)
Consulta (Query): R (Queremos saber se R é verdadeiro ou falso; KB ⊨ R?)

**Traduzindo KB**: Isso significa que, se for uma terça-feira **e** NÃO estiver chovendo, o Harry vai correr

Para responder à consulta usando o algoritmo de **verificação de modelos (Model Checking)**, enumeramos todos os modelos possíveis.

![KB - example 1](../PNGs/01-Knoweledge.png/KB%20-%20example%201.png)

Então, passamos por todos os modelos e verificamos se é verdade, dada a nossa Base de Conhecimento.

Primeiro, em nosso KB, sabemos que P é verdade. Assim, podemos dizer que o KB é falso em todos os modelos onde P não é verdadeiro.

| P     | Q     | R     | KB    |
| ----- | ----- | ----- | ----- |
| false | false | false | false |
| false | false | true  | false |
| false | true  | false | false |
| false | true  | true  | false |
| true  | false | false |       |
| true  | false | true  |       |
| true  | true  | false |       |
| true  | true  | true  |       |

Em seguida, da mesma forma, em nosso KB, sabemos que Q é falso. Assim, podemos dizer que o KB é falso em todos os modelos onde o Q é verdadeiro.

| P     | Q     | R     | KB    |
| ----- | ----- | ----- | ----- |
| false | false | false | false |
| false | false | true  | false |
| false | true  | false | false |
| false | true  | true  | false |
| true  | false | false |       |
| true  | false | true  |       |
| true  | true  | false | false |
| true  | true  | true  | false |

Por fim, ficamos com dois modelos. Em ambos, P é verdadeiro e Q é falso. Em um modelo R é verdadeiro e no outro R é falso. Devido a (P ∧ ¬Q) → R estar em nosso KB, sabemos que no caso em que P é verdadeiro e Q é falso, R deve ser verdadeiro. Assim, dizemos que nosso KB é falso para o modelo onde R é falso, e verdadeiro para o modelo onde R é verdadeiro.

![KB - example 2](../PNGs/01-Knoweledge.png/KB%20-%20example%202.png)

Olhando para esta tabela, há apenas um modelo em que a nossa base de conhecimento é verdadeira. Neste modelo, vemos que R também é verdade. Pela nossa definição de vinculação, se R é verdadeiro em todos os modelos onde o KB é verdadeiro, então KB ⊨ R.

---
Related: [Logica proposicional](./Logica%20proposicional.md), [Modelos, KB e Entailment](./Modelos,%20KB%20e%20Entailment.md)