Image Convolution é uma estratégia na visão computacional, onde podemos alterar alguma imagem passando filtros para ela.

Assim, com filtros aplicados conseguimos treinar nossos modelos para reconhecer algum padrão, como um objeto, uma pessoa, rosto, etc...

![Neural Network - Image example 6](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%206.png)

Nessa imagem, a matrix a esquerda é a nossa imagem sendo representada por numeros.

Na matrix no canto superior direito, temos o nosso filtro.

Na matrix abaixo temos a nova imagem final, aplicada o filtro

O processo de aplicar o filtro acontece da seguinte maneira:

- Para filtrar a imagem com o kernel, começamos com o pixel com o valor 20 no canto superior esquerdo da imagem (coordenadas 1,1). 
- Então, vamos multiplicar todos os valores em torno dele pelo valor correspondente no kernel e resumi-los (10 * 0 + 20*(-1) + 30 * 0 + 10*(-1) + 20 * 5 + 30*(-1) + 20 * 0 + 30*(-1) + 40 * 0), produzindo o valor 10. 
- Em seguida, faremos o mesmo para o pixel à direita (30), o pixel abaixo do primeiro (30) e o pixel à direita deste (40). Isso produz uma imagem filtrada com os valores que vemos no canto inferior direito.

### Diferentes kernels geram diferentes resultados

![Neural Network - Image example 12](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%2012.png)

Nesse kernel, o resultado da imagem pós filtragem e transformação, será a seguinte:

![Neural Network - Image example 13](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%2013.png)

A ideia aqui é que quando o pixel é semelhante a todos os seus vizinhos, eles devem cancelar um ao outro, dando um valor de 0. Portanto, quanto mais semelhantes os pixels, mais escura a parte da imagem, e mais diferentes elas são, mais clara é.

---
## Ilustração do processo de Image Convolution

![Neural Network - Image example 7](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%207.png)![Neural Network - Image example 8](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%208.png)![Neural Network - Image example 10](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%2010.png)![Neural Network - Image example 11](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%2011.png)
