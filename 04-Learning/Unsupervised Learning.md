Diferentemente do [Reinforcement Learning](./Reinforcement%20Learning.md) e [Aprendizado Supervisionado](./Aprendizado%20Supervisionado.md), o Unsupervised Learning ela é um algoritmo para classificar determinados states a partir de grupo sem rotulos ou rewards previos.

Por exemplo:
![Learning - example image 6](../PNGs/04-Learning.png/Learning%20-%20example%20image%206.png)

Na image temos os grupo que chamamos de **cluster**, para determinar a cor de cada ponto temos os losangos que são o **k-means Clustering**, para determinar suas posições é preciso pegar a distancia media dos pontos.

No começo o nosso k-means Clustering não sabe onde ficar, depois ele se ajusta e a ultima imagem mostra ele no devido lugar usando uma media ponderada para saber qual deve ser sua posição de acordo com a distancia media dos pontos do seu grupo.

A partir disso, podemos reclassificar os dados, passando novos cluster para os pontos que estão muito longe de seus cluster previo, assim podemos reajustar sem ter um rotulo e sem receber rewards

Sempre que fazemos reajustes de clustering, temos que tirar a nova media ponderado do posicionamento do nosso losango.

Apos os reajustes nosso cluster ficará assim:

![Learning - example image 7](../PNGs/04-Learning.png/Learning%20-%20example%20image%207.png)

Com isso, podemos classificar novos states a partir da distancia dele com os clustering, caso esteja mais perto do vermelho ele se tornaria vermelho, por exemplo.