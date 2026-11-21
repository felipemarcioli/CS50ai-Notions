Os algoritmos BFS e DFS utilizam os mesmos conceitos:

- Node
- Frontier
- Explored Set
- Expansão de nós

A principal diferença está em **como a frontier é organizada**.

---
# BFS (Breadth-First Search)

BFS significa **Busca em Largura**.

A ideia é explorar todos os nós de um nível antes de avançar para o próximo.

Exemplo:
```
        A
      /   \
     B     C
    / \   / \
   D  E  F  G
```

Ordem de visita:
```
A → B → C → D → E → F → G
```

Primeiro visita todos os nós próximos da raiz.
Depois visita os nós mais profundos.

---
## Estrutura Utilizada

BFS utiliza uma **Fila (Queue)**.

Regra:
```
Primeiro que entra
Primeiro que sai
```

(FIFO - First In, First Out)

Exemplo:
```
Frontier:

[A]
[B]
[C]
```

**A** será removido primeiro.

---
## Vantagem

Se todos os passos possuem o mesmo custo, o BFS encontra o caminho mais curto.

---
## Desvantagem

Pode consumir muita memória, pois precisa armazenar muitos nós na frontier.

---
## DFS (Depth-First Search)

**DFS** significa **Busca em Profundidade**.

A ideia é seguir um caminho até o fim antes de voltar e tentar outros caminhos.

Exemplo:
```
        A
      /   \
     B     C
    / \   / \
   D  E  F  G
```

Uma possível ordem de visita:
```
A → B → D → E → C → F → G
```

O algoritmo tenta ir o mais fundo possível.

---
## Estrutura Utilizada

DFS utiliza uma **Pilha (Stack)**.

Regra:
```
Último que entra
Primeiro que sai
```

(LIFO - Last In, First Out)

Exemplo:
```
Frontier:

[A]
[B]
[C]
```

C será removido primeiro.

---
## Vantagem

Utiliza muito menos memória que o BFS.

---
## Desvantagem

Não garante encontrar o caminho mais curto.

Pode explorar caminhos muito longos antes de encontrar a solução.

---
## Exemplo Comparando os Dois

Árvore:
```
          A
        /   \
       B     C
      /
     D
    /
   E
  /
 F
```

Objetivo: C

---
## BFS

Visitas:
```
A → B → C
```

Encontra rapidamente o objetivo.

---
## DFS

Visitas:
```
A → B → D → E → F
```

Só depois volta para procurar C.

---
## Resumo

| Característica | BFS                            | DFS                                |
| -------------- | ------------------------------ | ---------------------------------- |
| Nome           | Busca em Largura               | Busca em Profundidade              |
| Estrutura      | Fila (Queue)                   | Pilha (Stack)                      |
| Exploração     | Nível por nível                | Vai até o fundo                    |
| Menor caminho  | Sim                            | Não necessariamente                |
| Memória        | Alta                           | Baixa                              |
| Velocidade     | Melhor para objetivos próximos | Melhor para explorar profundamente |

---
Related: [Search Approach (DFS)](./Search%20Approach%20(DFS).md)