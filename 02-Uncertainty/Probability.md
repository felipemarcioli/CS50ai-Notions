Toda situação possivel pode ser representada como um **mundo**, um mundo é representado pela letra grega Omega ω. 

Por exemplo, um dado tem 1/6 de cair no numero desejado, isso significa que o dado tem 1/6 de cair no **mundo** que queremos.

Para representar a probabilidade de um determinado mundo, escrevemos **P(_ω_)**

---
## Regras da probabilidade

- 0 < P(_ω_) < 1: cada valor que representa a probabilidade deve variar entre 0 e 1.
    - Zero é um evento impossível, como rolar um dado padrão e obter um 7.
    - Um é um evento que certamente acontecerá, como rolar um dado padrão e obter um valor inferior a 10.
    - Em geral, quanto maior o valor, maior a probabilidade de o evento acontecer.
- As probabilidades de todos os eventos possíveis, quando somadas, são iguais a 1.

---

![Probability - example 1](../PNGs/02-Uncertainly.png/Probability%20-%20example%201.png)

A probabilidade de rolar um número _R_ com uma matriz padrão pode ser representada como P(_R_). 
No nosso caso, P(_R_) = 1/6, porque existem seis mundos possíveis (rolando qualquer número de 1 a 6) e cada um é igualmente provável que aconteça. 

Agora, considere o evento de rolar dois dados. Agora, existem 36 eventos possíveis, que são, novamente, igualmente prováveis.
![Probability - example 2](../PNGs/02-Uncertainly.png/Probability%20-%20example%202.png)

No entanto, o que acontece se tentarmos prever a soma dos dois dados? Neste caso, temos apenas 11 valores possíveis (a soma tem que variar de 2 a 12), e eles não ocorrem com igual frequência.

![Probability - example 3](../PNGs/02-Uncertainly.png/Probability%20-%20example%203.png)

Para obter a probabilidade de um evento, dividimos o número de mundos em que ele ocorre pelo número de mundos totais possíveis. 

Por exemplo, existem 36 mundos possíveis ao rolar dois dados. 

Somente em um desses mundos, quando ambos os dados produzem um 6, temos a soma de 12. 

Assim, P(_12_) = 1/36, ou, em palavras, a probabilidade de rolar dois dados e obter dois números cuja soma é 12 é 1/36. 

O que é P(_7_)? Contamos e vemos que a soma 7 ocorre em 6 mundos. Assim, P(_7_) = 6/36 = 1/6.

![Probability - example 4](../PNGs/02-Uncertainly.png/Probability%20-%20example%204.png)

---
## Probabilidade incondicional

A probabilidade incondicional é a chance de um evento acontecer **sem considerar nenhuma outra informação ou evento prévio**, sendo representada simplesmente como P(A).

---
## Probabilidade Condicional

A probabilidade condicional é a chance de um evento A acontecer sabendo que um evento B já ocorreu. 

A principal fórmula usada para calcular esse valor é:
![Probability - example 5](../PNGs/02-Uncertainly.png/Probability%20-%20example%205.png)
- **P(_a | b_)**, significa “a probabilidade de evento _ocorrer_, dado que sabemos que _b_ evento _b_ ocorreu”

Algumas vezes, você verá essa mesma formula escrita diferente, por exemplo, algebraticamente:
![Probability - example 8](../PNGs/02-Uncertainly.png/Probability%20-%20example%208.png)

### Example

Por exemplo, considere **P(_sum 12 | roll six on one die_)**, ou a probabilidade de rolar dois dados e obter uma soma de doze, dado que já rolamos um dado e conseguimos um seis. 

Para calcular isso, primeiro restringimos nossos mundos àqueles em que o valor do primeiro dado é seis:

![Probability - example 6](../PNGs/02-Uncertainly.png/Probability%20-%20example%206.png)

Agora perguntamos quantas vezes ocorre o evento _a_ (a soma sendo 12) nos mundos a que restringimos a questão (dividindo por P(_b_), ou a probabilidade de o primeiro dado ceder 6).

![Probability - example 7](../PNGs/02-Uncertainly.png/Probability%20-%20example%207.png)