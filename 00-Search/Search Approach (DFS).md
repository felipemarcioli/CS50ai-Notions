# Como o Processo de Busca Funciona na Prática (DFS)

Para entender os conceitos de Node, Frontier e Explored Set, vamos acompanhar uma busca passo a passo.
## Problema

**Imagine o seguinte mapa:**
```
Casa
 /  \
A    B
|    |
C    Mercado
```

- Estado inicial: **Casa**
- Objetivo: **Mercado**

---
## Estruturas Utilizadas

Antes de começar a busca, o algoritmo cria:
### Frontier

Armazena os nós que ainda precisam ser analisados.

```
Frontier:
[Casa]
```
### Explored Set

Armazena os estados já visitados.

```
Explorados:
[]
```

---
## Passo 1: Analisar o Estado Inicial

O algoritmo remove o nó Casa da frontier.

**Pergunta**:
> Casa é o objetivo?

**Resposta**:
> Não.

Então o nó é **expandido**.

### Expandindo Casa

A partir de Casa podemos chegar em:

- A
- B

São criados dois novos nós:
```
Node(A)
Parent = Casa

Node(B)
Parent = Casa
```

Esses nós são adicionados à **frontier**.
```
Frontier:
[A]
[B]
```

**Casa** é adicionada ao conjunto de explorados.
```
Explorados:
[Casa]
```

---
## Passo 2: Analisar A

O algoritmo remove A da frontier.

Pergunta:
> A é o objetivo?

Resposta:
> Não.

**Então A é expandido.**

### Expandindo A

A partir de A podemos chegar em:

- C

Criamos:
```
Node(C)
Parent = A
```

Atualizando as estruturas:
```
Frontier:
[B]
[C]

Explorados:
[Casa, A]
```

---
## Passo 3: Analisar B

O algoritmo remove B da frontier.

Pergunta:
> B é o objetivo?

Resposta:
> Não.

**Então B é expandido.**

### Expandindo B

A partir de B podemos chegar em:

- Mercado

Criamos:
```
Node(Mercado)
Parent = B
```

Atualizando:
```
Frontier:
[C]
[Mercado]

Explorados:
[Casa, A, B]
```

---
## Passo 4: Encontrar o Objetivo

O algoritmo remove Mercado da frontier.

Pergunta:
> Mercado é o objetivo?

Resposta:
> **Sim**.

**A busca termina.**

---
## Como a Solução é Reconstruída?

O algoritmo não guarda apenas os estados. Cada nó também guarda quem foi seu pai (Parent).

Durante a busca foi criado:
```
Casa
 ├─ A
 │   └─ C
 └─ B
     └─ Mercado
```

O nó **Mercado** possui:
```
State = Mercado
Parent = B
```

O nó **B** possui:
```
State = B
Parent = Casa
```

Então o algoritmo volta pelos **pais**:
```
Mercado
↑
B
↑
Casa
```

Invertendo a ordem:
```
Casa → B → Mercado
```

**Essa é a solução encontrada.**