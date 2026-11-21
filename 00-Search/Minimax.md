O **Minimax** é um dos algoritmos mais importantes da Inteligência Artificial clássica. Ele é usado para tomar decisões em **jogos de dois jogadores, de soma zero e informação perfeita**, como xadrez, damas, jogo da velha e Connect Four.

A ideia é simples:

- **Você (MAX)** quer maximizar suas chances de vencer.
- **Seu adversário (MIN)** quer minimizar suas chances de vencer.

O algoritmo assume que **o adversário sempre fará a melhor jogada possível**.

---

![Minimax example 1](../PNGs/00-Search.png/Minimax%20example%201.png)Neste caso do jogo da velha, o adversario é o **O**, onde ele está tentando minizar o resultado, você é representado pelo **X**, que está tentando maximizar o resultado.

---
## ⚙️ Como Funciona?

O algoritmo simula **todas as jogadas possíveis** a partir do estado atual do jogo até o final (ou até uma profundidade limite), construindo uma **árvore de decisão**. Ele assume que **ambos os jogadores jogam da maneira impecável (ótima)**.

### Os Dois Jogadores:

- 🟢 **MAX (O Robô/IA):** Quer **maximizar** a pontuação final (escolhe o maior valor).
    
- 🔴 **MIN (O Oponente):** Quer **minimizar** a pontuação do MAX (escolhe o menor valor).

---
## 🌳 Árvore de decisão

Neste exemplo, a vez da jogada está com o **X(a IA)**, e ela precisa achar qual cenário seria o mais **agradável** para ela **maximizar** o jogo.

Ela assume que o jogador **minimo(O)** não cometerá erros após sua escolha, então ela classifica o **cenário**:
	cenário 1 = min-value:0
	cenário 2 = min-value:-1

Com isso, ela assume que o **melhor** cenário é o terceiro, que **ela ganha o jogo** apenas com uma jogada **recebendo o valor de 1**. Que é o **valor maximo**.

![Minimax example 2](../PNGs/00-Search.png/Minimax%20example%202.png)