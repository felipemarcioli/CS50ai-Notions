Hill climbing é um algoritmo de busca para otimização. Nesse algoritmo os states vizinhos são comparados com os states atuais, se o state vizinho é melhor que o state atual, nos trocamos o state atual pelo state do vizinho. Se nenhum state do vizinho for melhor do que o state atual, nos retornamos o state atual. 

Para analisarmos os vizinho podemos mover o state atual para cima, baixo, esquerda e direita.

Em pseudocode o algoritmo do Hill Climbing é representado assim:

	function Hill-Climb(problem):
	
	current = initial state of problem
	repeat:
	    neighbor = best valued neighbor of current
	    if neighbor not better than current:
	        return current
	    current = neighbor

No exemplo das casas com o hospital, no state atual nos temos 17 de cost, porem podemos mover os hospitais para os vizinhos, caso o vizinho seja melhor que o state atual nos trocamos o state atual e repitimos o processo
![Optimization Image 2](../PNGs/03-Optimization.png/Optimization%20Image%202.png)

Assim movendo os hospitais pelas direções que são consideradas vizinhas dos hospitais, vamos obter o seguinte resultado:

![Optimization Image 3](../PNGs/03-Optimization.png/Optimization%20Image%203.png)

Houve uma diminuição significativa no cost, mas será que esse é o menor cost que podemos ter??

Não, se movermos o hospital do lado esquerdo para a casa inferior esquerda dele poderiamos diminuir seu cost, porem os vizinho são apenas os das 4 direções, nenhum dos vizinhos diminuem o cost atual, então nosso algoritmo retorna o state.

Isso é um problema que existe quando usamos o Hill Climbing, ele limita a possibilidade de diminuir o cost a partir do menor Local State que ele encontra, mas não garante que esse state é o menor Global State

Para contornarmos esse problema, devemos utilizar o random-restart, ele refaz a busca que o Hill Climbing vai fazer sendo definido pela quantidade de vezes que for passada na random-restart. Assim ele entrega o menor resultado daquelas buscas que foram repetitidas, mas isso não garante que vai ser o menor resultado possivel de um Global states. Então sempre que recebemos o cost de um Hill Climbing, devemos perguntar se aquele é o menor resultado possivel.

---
## [Simulated Annealing](./Simulated%20Annealing.md)

Uma forma de minimizarmos o problema do Hill Climbing, é usando o Simulated Annealing

---
## Hill Climbing variants

![Optimization Image 4](../PNGs/03-Optimization.png/Optimization%20Image%204.png)
