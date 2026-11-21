word2vec é um algoritmo para fazer o computador conseguir entender o contexto de uma palavra.

Antes o problema era tratado com o one-hot encoding, o problema dessa arquitetura antiga é que os vetores ficavam cheios de 0 e apenas um 1, isso é ineficiente.

Ele funciona da seguinte forma: palavras que aparecem em contextos semelhantes, tendem a ter significados semelhantes

![Language Image example 7](../PNGs/06-Language.png/Language%20Image%20example%207.png)

Com isso, usando o nosso algoritmo do word2vec conseguimos classificar o contexto de uma palavra vendo pelos textos em qual contexto elas aparecem, se elas estiverem em contextos proximos, **provavalmente** elas tem um significado parecido.

Assim conseguimos fazer algumas inferencias, como homem - rei + mulher = rainha

![Language Image example 6](../PNGs/06-Language.png/Language%20Image%20example%206.png)

