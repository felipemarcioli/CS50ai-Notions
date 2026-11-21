A resolução é uma poderosa [Inference Rules](./Inference%20Rules.md) que afirma que, se uma das duas proposições atômicas em uma **Or** proposta é falsa, a outra **tem que ser verdadeira**. 

Por exemplo, dada a proposição “Ron está no Grande Salão” **Or** “Hermione está na biblioteca”, **além da proposição** “Ron não está no Grande Salão”, **podemos concluir que** “Hermione está na biblioteca”. 

- P = Ron está no Grande Salão
- Q = Hermione está na biblioteca

Mais formalmente, podemos definir a resolução da seguinte maneira:

![Resolution - example 1](../PNGs/01-Knoweledge.png/Resolution%20-%20example%201.png)

Resolução se baseia em **Literais Complementares**, duas das mesmas proposições atômicas onde uma é negada e a outra não é, como P e ¬P.


Suponha que, além da proposição “Ron está no Grande Salão” **Or** “Hermione está na biblioteca”, também sabemos que “Ron não está no Grande Salão” **Or** “Harry está dormindo”. 

- P = Ron está no Grande Salão
- Q = Hermione está na biblioteca
- ¬P = Ron não está no Grande Salão
- R = Harry está dormindo

Podemos inferir a partir disso, usando a resolução, que “Hermione está na biblioteca” **Or** “Harry está dormindo”. Para colocá-lo em termos formais:

![Resolution - example 2](../PNGs/01-Knoweledge.png/Resolution%20-%20example%202.png)

Literais complementares nos permitem gerar novas frases através de inferências por resolução. Assim, os algoritmos de inferência localizam literais complementares para gerar novos conhecimentos.

Uma **Cláusula** é uma disjunção de literais (um símbolo proposicional ou uma negação de um símbolo proposicional, como P, ¬P). 

Uma **disjunção** consiste em proposições que estão conectadas com um **Or** lógico conjuntivo (P ∨ Q ∨ R). 

Uma **conjunção**, por outro lado, consiste em proposições que estão conectadas com um **And** conjuntivo lógico (P ∧ Q ∧ R). 

As cláusulas nos permitem converter qualquer declaração lógica em uma **Forma Normal Conjuntiva** (CNF), que é uma conjunção de cláusulas, por exemplo: **(A ∨ B ∨ C) ∧ (D ∨ ¬E) ∧ (F ∨ G)**.

---
## Forma Normal Conjuntiva (CNF)
Para entender o funcionamento da Forma Normal Conjuntiva (CNF), **leia** [Forma Normal Conjuntiva (CNF)](./Forma%20Normal%20Conjuntiva%20(CNF).md)