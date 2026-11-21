
O **Alpha-Beta Pruning** é uma otimização do algoritmo [Minimax](./Minimax.md) Ele permite que a IA encontre a mesma melhor jogada, **mas analisando muito menos posições.**

A ideia principal é:
	**Se uma jogada já é comprovadamente pior do que outra encontrada anteriormente, não faz sentido continuar analisando ela.**

---
## Como funciona?

Como o algoritmo do Minimax, o algoritmo assume que o adversário **sempre** irá fazer a melhor jogada possível.

Assumindo isso, é possível descartar opções de analise, assim, otimizando o nosso algoritmo, chamado **Alpha-Beta Pruning**.

---
## Exemplo

![Alpha-Beta Pruning - example](../PNGs/00-Search.png/Alpha-Beta%20Pruning%20-%20example.png)

**Triângulos verdes = MAX**  
**Triângulos vermelhos = MIN**

O algoritmo Minimax assume que ambos os jogadores sempre fazem a melhor jogada possível.

Neste exemplo, o computador é o jogador **MAX**, que tenta obter o maior valor possível. Já o adversário é o jogador **MIN**, que tenta reduzir esse valor.

Cada triângulo representa um estado do jogo, e seus filhos representam as jogadas possíveis a partir daquele estado.

O algoritmo começa analisando a primeira ramificação. Como o nó é um MIN, ele escolhe o menor valor entre **4, 8 e 5**, retornando **4** para a raiz.

Assim, o jogador MAX já sabe que consegue garantir um resultado de pelo menos **4**.

Ao analisar a segunda ramificação, o algoritmo encontra uma folha com valor **3**. Como esse nó pertence ao jogador MIN, ele já pode garantir um resultado de no máximo **3**. Como **3 é pior do que o 4 que MAX já possui**, MAX nunca escolherá esse ramo. Portanto, não é necessário analisar o restante dessa subárvore (poda Alpha-Beta).

O mesmo ocorre na terceira ramificação. Assim que o valor **2** é encontrado, o algoritmo sabe que esse nó retornará um valor de no máximo **2**, tornando desnecessária a análise das folhas restantes.

Dessa forma, o Alpha-Beta Pruning evita explorar partes da árvore que não podem alterar a decisão final, economizando muito tempo de processamento sem alterar o resultado do Minimax.


**Related**: [Node](./Node.md)