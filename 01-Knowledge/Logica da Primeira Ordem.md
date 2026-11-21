A lógica de primeira ordem é outro tipo de lógica que nos permite expressar ideias mais complexas de forma mais sucinta do que a [Logica proposicional](./Logica%20proposicional.md). 

A lógica de primeira ordem usa dois tipos de símbolos: _Símbolos Constantes_ e _Símbolos de Predicado_. 

**Símbolos constantes representam objetos**, enquanto **símbolos de predicado são como relações ou funções** que tomam um argumento e retornam um valor verdadeiro ou falso.

---
## Como funciona?

**Os símbolos constantes são pessoas ou casas**, como Minerva, Pomona, Gryffindor, Hufflepuff, etc. 

**Os símbolos do predicado são propriedades que são verdadeiras ou falsas de alguns símbolos constantes. **

Por exemplo, podemos expressar a ideia de que Minerva é uma pessoa usando a frase **Pessoa(Minerva)**. 

Da mesma forma, podemos expressar a ideia de que a Gryffindor é uma casa usando a sentença **House (Gryffindor)**. 

**Todos os conectivos lógicos funcionam na lógica de primeira ordem da mesma maneira que antes. **

Por exemplo, ¬House (Minerva) expressa a ideia de que **Minerva não é uma casa**. 

Um símbolo de predicado também pode pegar dois ou mais argumentos e expressar uma relação entre eles. 

Por exemplo, a **BelongsTo** expressa uma relação entre dois argumentos, a pessoa e a casa à qual a pessoa pertence. 

Assim, a ideia de que Minerva pertence à Gryffindor pode ser expressa como **BelongsTo(Minerva, Gryffindor)**. 

A lógica de primeira ordem permite ter um **símbolo para cada pessoa** e um símbolo **para cada casa**. 

Isso é mais sucinto do que a [Logica proposicional](./Logica%20proposicional.md), **onde cada pessoa – a atribuição da casa exigiria um símbolo diferente.**

---
## **Quantificação Universal**

Quantificação é uma ferramenta que pode ser usada na lógica de primeira ordem para representar frases sem usar um símbolo constante específico. 

A quantificação universal usa o símbolo ∀ para expressar “para todos”. 

Então, por exemplo, a frase:

**∀x. BelongsTo(x, Gryffindor) → ¬BelongsTo(x, Hufflepuff)**

Expressa a ideia de que é verdade para cada símbolo que se este símbolo pertence à **Gryffindor**, não pertence a **Hufflepuff.**

---
## **Quantificação Existencial**

A quantificação existencial é uma ideia paralela à quantificação universal. 

No entanto, enquanto a quantificação universal foi usada para criar sentenças que são verdadeiras para **todos os x**, a quantificação existencial é usada para criar sentenças que são verdadeiras para **pelo menos um x**. 

É expresso usando o símbolo **∃**. 
Por exemplo, a frase:

**∃x. Casa(x) ∧ BelongsTo(Minerva, x)**

Significa que há pelo menos um símbolo que é tanto uma casa quanto que a Minerva pertence a ela. 

Em outras palavras, **isso expressa a ideia de que Minerva pertence a uma casa**.

---
## Quantificação existencial e universal

A quantificação existencial e universal pode ser utilizada na mesma frase. 
Por exemplo, a frase:

**∀x. Pessoa(x) → (∃y. Casa(y) ∧ BelongsTo(x, y))** 

Expressa a ideia de que se **x é uma pessoa**, então há pelo menos uma **casa, y**, à qual essa pessoa pertence. 

Em outras palavras, **esta frase significa que cada pessoa pertence a uma casa**.