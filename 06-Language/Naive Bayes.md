Naive Bayes é uma técnica que pode ser usada na análise de sentimento. Na análise de sentimento, estamos perguntando “Qual é a probabilidade de que a frase seja positiva/negativa, dadas as palavras na frase”.
Responder a essa pergunta requer [Probability](../02-Uncertainty/Probability.md) condicional computacional

A formula para descobrir se um texto ou palavra expressa algo positivo ou negativo é a seguinte:
![Language Image example 1](../PNGs/06-Language.png/Language%20Image%20example%201.png)

Imagine o seguinte caso, temos uma e-commerce e nessa loja precisamos classificar as avaliações dos produtos como positiva ou negativa.

Para isso, vamos passar uma lista de palavras que são frequentemente classificadas como positiva e outra lista para palavras que são frequentemente classificadas como negativas.

Assim, nossa rede neural irá aprender o padrão e vai conseguir classificar os comentarios de acordo com as palavras que foram utilizadas.

Por exemplo: 
	Alguém comentou o seguinte comentario: "My grandson loved it"
	para classificar a seguinte frase como positiva ou negativa, primeiro
	precisamos fazer o processo de [Tokenizacao](./Tokenizacao.md), e depois aplica-lo a formula do naive bayes
Após isso, vamos obter o seguinte resultado:

![Language Image example 2](../PNGs/06-Language.png/Language%20Image%20example%202.png)

Após fazermos os cálculos, descobrimos os seguintes valores para essa frase:

![Language Image example 3](../PNGs/06-Language.png/Language%20Image%20example%203.png)

---
Related: [Rede Bayesiana](../02-Uncertainty/Rede%20Bayesiana.md) & [Bayes' Rules](../02-Uncertainty/Bayes'%20Rules.md)