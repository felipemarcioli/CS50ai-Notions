A regra de Bayes é comumente usada na teoria da [Probability](./Probability.md) para calcular a probabilidade condicional. 

Em palavras, a regra de Bayes diz que a probabilidade de _b_ _dada_ a é igual à probabilidade _de_ um _determinado_ b, vezes a probabilidade _de_ b, dividida pela probabilidade _de_ a.

![Bayes' Rules - example 1](../PNGs/02-Uncertainly.png/Bayes'%20Rules%20-%20example%201.png)

Por exemplo, gostaríamos de calcular a probabilidade de chover à tarde se houver nuvens pela manhã, ou P(_chuva_ _| nuvens_). Começamos com as seguintes informações:

- 80% das tardes chuvosas começam com manhãs nubladas, ou P(_nuvens | chuva_).
- 40% dos dias têm manhãs nubladas, ou P(_nuvens_).
- 10% dos dias têm tardes chuvosas, ou P(_chuva_).

Aplicando a regra de Bayes, nós calculamos (0.1)(0.8)/(0.4) = 0.2. Ou seja, a probabilidade de que chova à tarde dado que estava nublado pela manhã é de 20%.

---
## Um exemplo simples

Imagine que uma IA quer descobrir se um e-mail é spam.

Antes de ler o e-mail, ela sabe que:

- Apenas **5%** dos e-mails são spam.
- Portanto:
    - P(Spam) = 0,05
    - P(Não Spam) = 0,95

Agora ela percebe uma evidência:

> O e-mail contém a palavra **"GRÁTIS"**.

Ela sabe pelos dados históricos que:

- 80% dos spams possuem essa palavra.
- Apenas 10% dos e-mails normais possuem essa palavra.

Então:

- P("GRÁTIS" | Spam) = 0,80
- P("GRÁTIS" | Não Spam) = 0,10

Aplicando Bayes, a IA calcula:

> **"Agora que vi a palavra 'GRÁTIS', qual a chance deste e-mail realmente ser spam?"**

Perceba que a probabilidade muda porque surgiu uma nova evidência.

---
### Resumindo

A Regra de Bayes é um método matemático que permite a uma IA:

1. Começar com uma crença inicial (_prior_).
2. Observar uma nova evidência.
3. Atualizar essa crença de forma matemática.
4. Tomar decisões mais precisas à medida que aprende novas informações.