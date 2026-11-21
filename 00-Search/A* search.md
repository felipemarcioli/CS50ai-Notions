Para melhorar o algoritmo do [GBFS (Greedy Best-First Search)](./GBFS%20(Greedy%20Best-First%20Search).md) o algoritmo **A**** é utilizado, ele evita que o **algoritmo** faça decisões erradas e escolhe a melhor **matematicamente**

## Como funciona?

A ideia central é simples: ao explorar um nó, A* considera **dois fatores juntos**:

```
f(n) = g(n) + h(n)
```

- **g(n)** → custo real acumulado do início até o node **n**
- **h(n)** → estimativa heurística de **n** até o objetivo
- **f(n)** → custo total estimado do caminho passando por n

A fila de prioridade sempre expande o nó com **menor f(n)** primeiro.

---
## Como funciona na pratica?

**A** = Ponto de Partida
**B** = Objetivo
**Blocos** = Node

Nesse examplo, ele demonstra como o **A* search** funciona na pratica, mostrando os states que ele preciso analisar para encontrar o melhor caminho

O numero que vem na frente  do bloco representa quantos blocos precisou percorrer até chegar no **bloco atual ([Node](./Node.md)).**
	**g(n)**

O segundo numero dentro do bloco mostra o quanto o ele está longe do **objetivo(B)**.
	**h(n)**

Com esse dois valores o **A**** faz a soma e se decide pelo bloco com o menor valor.
	**f(n)**

No ponto de decisao, que no exemplo é o bloco **5+12**, o **A**** deixa o bloco **6+13** na **fronteier**, e passa para o proximo bloco com o valor menor.

Quando os valores ficam maiores pela decisão que foi tomada pelo algoritmo, ele decide voltar pelo caminho do **6+13**, que ele havia armazenado na **frontier**, e com isso ele percebe que esse caminho é menor e que tem um menor custo para chegar até o **objetivo(B)**

![A* search - Image Example](../PNGs/00-Search.png/A*%20search%20-%20Image%20Example.png)

---
## Por que isso funciona?

O g(n) impede que o algoritmo ignore caminhos caros. O h(n) impede que ele explore cegamente como o Dijkstra. Juntos, eles direcionam a busca de forma eficiente _sem abrir mão da otimalidade_.

---
## Condição para ser ótimo: heurística admissível

h(n) precisa **nunca superestimar** o custo real até o objetivo.

> Se o caminho real custa 10, h(n) pode ser 7 ou 10, mas nunca 12.

Um exemplo clássico: em mapas com coordenadas, usar a **distância em linha reta** como h(n) é sempre admissível, porque nenhum caminho real pode ser mais curto que a reta.

---
Related: [GBFS (Greedy Best-First Search)](./GBFS%20(Greedy%20Best-First%20Search).md)