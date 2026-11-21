Queremos representar significados de palavras em nossa IA. Como vimos antes, é conveniente fornecer informações sobre a IA na forma de números. 

Uma maneira de fazer isso é usando **a Representação One-Hot**, onde cada palavra é representada com um vetor que consiste em tantos valores que temos as palavras. Exceto por um único valor no vetor que é igual a 1, todos os outros valores são iguais a 0.

Um exemplo visual seria:

![Language Image example 4](../PNGs/06-Language.png/Language%20Image%20example%204.png)

No entanto, enquanto esta representação funciona em um mundo com quatro palavras, se quisermos representar palavras de um dicionário, quando podemos ter 50.000 palavras, vamos acabar com 50.000 vetores de comprimento 50.000. Isto é computacionalmente ineficiente. 

Outro problema nesse tipo de representação é que somos incapazes de representar semelhança entre palavras como “escrevido” e “autoria”. 

Em vez disso, nos vamos para a ideia de **Representação Distribuída**, onde o significado é distribuído através de vários valores em um vetor. Com a representação distribuída, cada vetor tem um número limitado de valores (muito menos de 50.000).

![Language Image example 5](../PNGs/06-Language.png/Language%20Image%20example%205.png)