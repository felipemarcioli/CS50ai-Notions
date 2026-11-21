## O que é?
O **Greedy Best-First Search** é um algoritmo que funciona do mesmo jeito que o **BFS(Best-Firts Search)** porém ao inves de ter que analisar diversos states, ele se utiliza de ***Heuristica*** para tomar decisões

---
## Como funciona a busca
A busca funciona do mesmo jeito que o **BFS**, porém quando é preciso tomar uma decisão de qual caminho escolher, ele se decide pelo caminho que é **matematicamente** mais próximo, seguindo apenas por este caminho.
Até encontrar o **objetivo** ou se **encurralar** e voltar para o ponto de decisão e escolher outra opção mais agradável.

Com esse sistema de algoritmo ele consegue encontrar possiveis caminhos mais rapidos do que o **BFS** e também gastando muito menos ***RAM***.
O problema é que ele não leva em conta as **consequencias** que viram com sua tomada de decisão, que naquele momento parecia a mais agradável

---
## Quais são suas vantagens?

✅ Geralmente encontra soluções rapidamente.

✅ Usa conhecimento da heurística para guiar a busca.

✅ Costuma explorar muito menos nós que uma busca cega como **BFS**.

---
## E suas desvantagens?

❌ Não garante o caminho mais curto.

❌ Pode ficar preso seguindo uma direção que parece boa, mas não é.

❌ A qualidade depende muito da heurística.

---
## Comparação com BFS

| Característica            | BFS                 | Greedy Best-First |
| ------------------------- | ------------------- | ----------------- |
| Usa heurística?           | Não                 | Sim               |
| Encontra solução ótima?   | Sim (custos iguais) | Não               |
| Geralmente é mais rápido? | Não                 | Sim               |
| Explora muitos nós?       | Sim                 | Normalmente menos |

---
Related: [BFS vs DFS](./BFS%20vs%20DFS.md)