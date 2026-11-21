Nearest-Neighbor Classification é um algoritmo para determinar qual seria o resultado de determinado **state**, atraves do seu vizinho mais proximo

No exemplo do chuva, ela pode ser representado em um grafico de pontos da seguinte maneira:

![Learning - example image 1](../PNGs/04-Learning.png/Learning%20-%20example%20image%201.png)

Nesse exemplo, usando o **Nearest-Neighbor Classification** o ponto branco no grafico seria classificado como vermelho, levando em conta o seu vizinho mais proximo que é vermelho

Porém essa afirmação não é muito confiavel por conta do ponto branco estar cercado de pontos azuis, porem o nosso algoritmo de Nearest-Neighbor Classification não enxerga isso.

---
## Solução

Para contornar esse tipo de problema podemos analisar mais de um vizinho mais proximo e tiramos uma media dessa distancia.

Isso é uma variavel que é chamada de _k_, passando a variavel de **k-nearest-neighbors classification**

Classificando o _k_ como 3 por exemplo, a media dos azuis vão prevalecer porque tem mais 3 pontos azuis mais proximos do ponto branco do que pontos vermelhos, então podemos inferir com mais confiança de que o ponto branco deve ser azul.

**Quanto maior for o _k_ mais confiança terá nossa inferência, por outro lado ela levará mais tempo para calcular**