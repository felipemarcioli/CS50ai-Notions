Diferente do [Aprendizado Supervisionado](./Aprendizado%20Supervisionado.md), no reinforcement learning a IA vai descobrir sozinha o que é certo e o que é errado atraves de um reward que será passado, ela será treinada um monte de vezes para tomar um monte de ações e com isso ela aprende a como agir em determinado state por conta do reward que foi passado anteriormente para ela.

O processo de aprendizado de ML, é:

Agent: que irá executar as escolhas
Enviroment: as opções e o ambiente atual que se situa-mos

![Learning - example image 5](../PNGs/04-Learning.png/Learning%20-%20example%20image%205.png)

Agent recebe um **state** passado pelo enviroment --> agent toma uma **action** e passa para o enviroment --> enviroment recebe essa action e passa um **reward** de acordo com ela, junto a isso ele passe um novo state

Esse é o processo de aprendizado, sendo tomado por ações e com elas ganhando uma recompensa para cada ação tomada, assim a nossa maquina aprende o que fazer e o que não fazer se baseando no **reward** que ela ganhou