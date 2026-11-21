Estruturas da Rede Neural Artificial são baseadas me estruturas de redes neurais biologicas, cada [Node](../00-Search/Node.md) representa um neuronio, e cada um possui ser determinado valor e em cada seta, vai ter um peso que será reajustado conforme o aprendizado, o processo de [Learning (Aprendizado)](../04-Learning/Learning%20(Aprendizado).md) funciona atraves do reajuste desses valores para determinado resultado.

![Neural Network - Image example 1](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%201.png)

Aqui a gente tem os nossos valores x1 e x2, cada um tem o seu weight(peso) w1 e w2, respectivamente.

O nosso output é a formula de uma **bias** que é um valor base que será somado, nesse caso o **w0** + w1.x1 + w2.x2

---
## Exemplo

Para construirmos uma rede neural para determinar a função **or**, o que precisamos fazer é definir o nosso bias de -1, e todas as vezes que o nosso output for 0 ou 1, ele será **TRUE**.

Possible cases:

|_x_|_y_|_f(x, y)_|
|---|---|---|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|1|

![Neural Network - Image example 2](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%202.png)