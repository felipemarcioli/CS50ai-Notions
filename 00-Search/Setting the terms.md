
**Agent**: Uma entidade que percebe que está em um ambiente e é capaz de agir dentro deste ambiente

**State**: É o estado onde o agente esta inserido, a configuração
	Initial State: Estado onde o state se inicia

Exemplo: GPS
	Agent = A representação do carro
	State = Mapa

------------------------------------------------------------------------

**Actions**: Ações que o **Agent** pode tomar dentro do **State**

É possível definir o **Actions** como uma função

	Actions(s)

Assim o parâmetro ***s*** irá retornar todos os valores possíveis de ***Actions*** que podem ser tomadas

---

**Transition Model**: É o que vai relacionar as ações tomadas pelo **Actions** e aplicar elas no **State**

	example(input, s) = output

**Example** = Seria a nossa função onde iria aplicar o código do nosso **Transition Model**
**Input** = Seria o nosso **State** atual
**s** = Seria o nosso **Actions** onde irá representar qual ação nós queremos representar no **State**
**Output** = Seria o nosso novo **State** com o nosso **Actions** já executado

---

**Space State**: É o conjunto de states que podermos criar a partir de um **Initial State**

Eles podem ser criados por ações de 1 ação ou até mais ações, mais ações iria requerer mais states para analisar, assim iria precisar fazer a **search** para descobrir qual ação é a melhor para se tomar, e depois para otimizar os resultados seria preciso fazer a fase de **optimization**

Exemplo: Uma **chess engine**, onde ela analisa varias possibilidades de ações que poderá tomar para decidir qual é a melhor jogada, ela faz isso analisando o tabuleiro atual e decidindo qual é a melhor jogada
	Uma chess engine grande como o **[Stockfish](https://en.wikipedia.org/wiki/Stockfish_(chess))** ele analisa mais de 1 ação, claro. Assim, demonstrando que quanto maior for as **ações** analisadas, maior será o **Space State**

---

**Goal Test**: É um jeito de dizer para a IA se ela está indo para o caminho certo e realizando a tarefa de forma correta, é um jeito de falar se ela esta indo para o **Goal State**

**Goal State**: É o resultado que pretendemos ter após a IA tomar as actions e chegar ao resultado correto, é o estado desejado.

---

**Path Cost**: É o que determinará se um resultado é bom ou se tem melhores no nossos resultados finais

Um problema pode ter diversas soluções, mas o que determinará qual é bom e qual é ruim será o nosso **path cost**

Exemplo: GPS
Pode ter diversas rotas, porem o path cost irá classificar e me entregar qual é a melhor rota para eu fazer, descartando as rotas que dão voltas desnecessárias para eu chegar ao meu destino, ele irá entregar o melhor resultado