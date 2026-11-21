## **Passos na Conversão de Proposições para Forma Normal Conjuntiva** (CNF)

- Elimine as bicondicionais
    - **Transforme (α ↔ β) em (α → β) ∧ (β → α).**
	
- Eliminar implicações
    - **Transforme (α → β) em ¬α ∨ β.**
	
- Mova a negação para dentro até que apenas os literais estejam sendo negados (e não cláusulas), usando as **Leis de De Morgan.**
    - **Transforme ¬(α ∧ β) em ¬α ∨ ¬β**


Aqui está um exemplo de conversão (P ∨ Q) → R para **Forma Normal Conjuntiva**:

- (P ∨ Q) → R
- ¬(P ∨ Q) ∨ R **/Eliminar implicação**
- (¬P ∧ ¬Q) ∨ R **/Lei de De Morgan**
- (¬P ∨ R) ∧ (¬Q ∨ R) **/Conceito Distributivo**

Neste ponto, podemos executar um algoritmo de inferência na forma normal conjuntiva. 

Ocasionalmente, através do processo de inferência por resolução, podemos acabar nos casos em que uma cláusula contém o mesmo literal duas vezes.

Nestes casos, é utilizado um processo chamado **factoring**, onde a duplicata literal é removida. 

---
#### Por exemplo:

- **(P ∨ Q ∨ S) ∧ (¬P ∨ R ∨ S)** 

Permite-nos inferir por resolução que: 

- **(Q ∨ S ∨ R ∨ S)** 

O **S** duplicado pode ser removido para nos dar:
- **(Q ∨ R ∨ S)**

---
## Como o algoritmo funciona?

Resolvendo um literal e sua negação, ou seja, **¬P e P**, dá a **cláusula vazia** (). 

**A cláusula vazia é sempre falsa, e isso faz sentido porque é impossível que tanto P quanto ¬P sejam verdadeiros. Este fato é usado pelo algoritmo de [Resolution](./Resolution.md).**

- Para determinar se KB ⊨ α:
    - Verificação: (KB ∧ ¬α) é uma contradição?
        - Se assim for, então KB ⊨ α.
        - Caso contrário, nenhuma vinculação.

**Prova por contradição** é uma ferramenta usada frequentemente na ciência da computação.

Se a nossa base de conhecimento é verdadeira, e contradiz ¬α, **significa que ¬α é falsa**, e, portanto, **α deve ser verdadeira**. 


Mais tecnicamente, **o algoritmo realizaria as seguintes ações**:

**Para determinar se KB ⊨ α:**

- Converta (KB ∧ ¬α) em Forma Normal Conjuntiva.
- Continue verificando se podemos usar a resolução para produzir uma nova cláusula.
- Se algum dia produzirmos a cláusula vazia (equivalente a Falso), parabéns! Chegamos a uma contradição, provando assim que KB ⊨ α.
- No entanto, se a contradição não for alcançada e não houver mais cláusulas que possam ser inferidas, não há qualquer implicação.

**Aqui está um exemplo que ilustra como esse algoritmo pode funcionar:**

- Será que (A ∨ B) ∧ (¬B ∨ C) ∧ (¬C) implica A?

- Primeiro, para provar por contradição, assumimos que A é falso. Assim, chegamos a:
	(A ∨ B) ∧ (¬B ∨ C) ∧ (¬C) ∧ (¬A).

- Agora, podemos começar a gerar novas informações. Uma vez que sabemos que C é falso (¬C), a única maneira (¬B ∨ C) pode ser verdadeira é se B é falso, também. Assim, podemos adicionar (¬B) ao nosso KB.

- Em seguida, já que sabemos (¬B), o único caminho (A ∨ B) pode ser verdadeiro é se A é verdadeiro. Assim, podemos adicionar (A) ao nosso KB.

- Agora nosso KB tem dois literais complementares, (A) e (¬A). Nós os resolvemos, chegando ao conjunto vazio, (). O conjunto vazio é falso por definição, então chegamos a uma contradição.