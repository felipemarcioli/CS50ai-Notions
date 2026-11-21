Overfitting é o perigo de modelar os dados de treinamento muito de perto, deixando assim de generalizar para novos dados. Uma maneira de combater o overfitting é por **desistência**. 

Nesta técnica, removemos temporariamente unidades que selecionamos aleatoriamente durante a fase de aprendizagem. 

Desta forma, tentamos evitar a dependência excessiva de qualquer unidade na rede. 

Ao longo do treinamento, a rede neural assumirá diferentes formas, cada vez deixando cair algumas outras unidades e, em seguida, usando-as novamente:

![Neural Network - Image example 5](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%205.png)

---
Related: [Overfitting](../04-Learning/Overfitting.md)