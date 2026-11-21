# O que é uma solução?

Uma **solução** é uma sequência de ações que leva do estado inicial até o estado objetivo.
### Exemplo:
**Estado inicial**: Casa
**Objetivo**: Mercado
**Solução**:
Casa → B → Mercado

---

# Solução Ótima (Optimal Solution)

É a solução que possui o menor custo entre todas as soluções possíveis.

O custo pode representar:
- Distância
- Tempo
- Dinheiro
- Consumo de energia

---

Import [Node](./Node.md)
# Node (Nó)

Um **node** é uma estrutura de dados utilizada pelos algoritmos de busca para armazenar informações sobre um estado.

Cada node contém:
- **State:** estado atual
- **Parent:** nó que gerou o nó atual
- **Action:** ação utilizada para chegar ao estado atual
- **Path Cost:** custo acumulado desde o estado inicial

### Exemplo:
**Estado**: Mercado
**Pai**: B
**Ação**: Ir para Mercado
**Custo**: 10

---

# Por que armazenar o Parent?

O parent permite reconstruir o caminho da solução após encontrar o objetivo.
### Exemplo:

**Mercado**
↑
**B**
↑
**Casa**

Lendo de baixo para cima:
**Casa → B → Mercado**

---

# Frontier

A **frontier** é a coleção de nós que ainda precisam ser explorados.
Pode ser vista como uma lista de possibilidades pendentes.
### Exemplo:

**Frontier**:
[A]
[B]
[C]

Os algoritmos de busca retiram nós da frontier para analisá-los.

---

# Explored Set

O **explored set** armazena os estados que já foram visitados.

Seu objetivo é evitar que o algoritmo visite os mesmos estados repetidamente.

### **Exemplo de ciclo**:

A → B → C

↑ ↓

└───────┘

Sem o **explored set**, a busca poderia entrar em um loop infinito.

---

# O que significa Expandir um Nó?

Expandir um nó significa descobrir todos os estados que podem ser alcançados a partir dele.
### Exemplo:
```
  A
 / \
B   C
```

Ao expandir A, descobrimos:
- B
- C

Esses novos nós são adicionados à **frontier**.

---

# Como a Busca Funciona

**Algoritmo geral**:
1. Adicionar o estado inicial à frontier.
2. Enquanto a frontier não estiver vazia:
    - Remover um nó da frontier.
    - Verificar se ele é o objetivo.
    - Se for o objetivo:
        - Retornar a solução.
    - Caso contrário:
        - Expandir o nó.
        - Adicionar os novos nós à frontier.
        - Marcar o nó atual como explorado.
3. Se a frontier ficar vazia:
    - Não existe solução.

---

# Como a search funciona na pratica?

Para entender o funcionamento completo, **leia [Search Approach (DFS)](./Search%20Approach%20(DFS).md)**

## Intuição

A busca funciona como uma exploração sistemática:

1. Escolha um nó da frontier.
2. Verifique se ele é o objetivo.
3. Se não for, descubra seus vizinhos (expandir).
4. Adicione os novos nós à frontier.
5. Marque o nó atual como explorado.
6. Repita até encontrar o objetivo ou esgotar todas as possibilidades.

---
# Algoritmos

## Diferença entre algoritmos
Para entender melhor a diferença entre as abordagens que podem ser utilizadas, e a diferença entre os algoritmos **leia** [BFS vs DFS](./BFS%20vs%20DFS.md)

## Greedy Best-First Search (GBFS)
Para entender o funcionamento do **GBFS**, leia [GBFS (Greedy Best-First Search)](./GBFS%20(Greedy%20Best-First%20Search).md)

## A* search
Para entender o funcionamento do A*, **leia** [A* search](./A*%20search.md)

## Minimax
Para entender o funcionamento do Minimax, **leia** [Minimax](./Minimax.md)

## Alpha-Beta Pruning
Para entender o funcionamento do Alpha-Beta Prunning, **leia** [Alpha-Beta Pruning](./Alpha-Beta%20Pruning.md)

---
# Resumo

- Um problema de busca possui um estado inicial e um objetivo.
- Cada possibilidade é armazenada em um node.
- Os nodes aguardam exploração na frontier.
- O algoritmo explora os nodes um a um.
- Estados já visitados ficam no explored set.
- Quando o objetivo é encontrado, os parent nodes permitem reconstruir a sequência de ações da solução.
- A solução ótima é aquela com o menor custo.

---

Related: [Node](./Node.md), [Setting the terms](./Setting%20the%20terms.md), [Search Approach (DFS)](./Search%20Approach%20(DFS).md)