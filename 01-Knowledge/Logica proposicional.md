
# Símbolos Proposicionais

Símbolos proposicionais são na maioria das vezes letras **(P, Q, R)** que são usadas para representar uma proposição

---
# Conexões Lógicos

Conjuntivos lógicos são símbolos lógicos que conectam símbolos proposicionais para raciocinar de uma maneira mais complexa sobre o mundo.

- **Not (¬)**
- **And (∧)** 
- **Or (∨)**
- **Implication (→)** 
- **Biconditional (↔)**

---
## **Not (¬)**

Inverte o valor da verdade da proposição. Então, por exemplo, se P: “Está chovendo”, então ¬P: “Não está chovendo”.

| P     | ¬P    |
| ----- | ----- |
| false | true  |
| true  | false |

---
## **And (∧)**

Conecta duas proposições diferentes. Quando essas duas proposições, P e Q, estão conectadas por ∧, a proposição resultante P ∧ Q é verdadeira apenas no caso de P e Q serem verdadeiros.

| P     | Q     | P ∧ Q |
| ----- | ----- | ----- |
| false | false | false |
| false | true  | false |
| true  | false | false |
| true  | true  | true  |

---
## **Or (∨)**

É verdade enquanto qualquer um de seus argumentos for verdadeiro. Isso significa que para P ∨ Q ser verdade, pelo menos um de P ou Q tem que ser verdadeiro.

|P|Q|P ∨ Q|
|---|---|---|
|false|false|false|
|false|true|true|
|true|false|true|
|true|true|true|

 **Existem dois tipos de "Or": o inclusivo e o exclusivo.** O **Or inclusivo (∨)**, utilizado na lógica proposicional, é verdadeiro sempre que **pelo menos uma** das proposições for verdadeira, incluindo o caso em que **ambas** são verdadeiras ("P ou Q, ou ambos"). Já o **Or exclusivo (XOR)** é verdadeiro apenas quando **exatamente uma** das proposições é verdadeira; se **P e Q** forem verdadeiros ao mesmo tempo, o resultado será **false**. Portanto, sempre que o símbolo **∨** aparecer em lógica, ele representa o **Or inclusivo**, e não o exclusivo.

---
## **Implication (→)**

Representa uma estrutura de “se P então Q”. Por exemplo, se P: “Está chovendo” e Q: “Estou dentro de casa”, então P → Q significa “Se está chovendo, então estou dentro de casa”. No caso de P implica Q (P → Q), P é chamado de **antecedente** e Q é chamado de **consequente.

Quando o **antecedente** é verdadeiro, toda a implicação é verdadeira no caso de que o **consequente** é verdadeiro (isso faz sentido: se está chovendo e eu estou dentro de casa, então a frase “se está chovendo, então eu estou dentro de casa” é verdadeira). Quando o **antecedente** é verdadeiro, a implicação é falsa se o **consequente é falso (se eu estou fora enquanto está chovendo, então a frase “Se está chovendo, então eu estou dentro de casa” é falsa). No entanto, quando o antecedente** é falso, a implicação é sempre verdadeira, independentemente da **consequente**. Logicamente, não podemos aprender nada com uma implicação (P → Q) se o **antecedente** (P) é falso. Olhando para o nosso exemplo, se não está chovendo, a implicação não diz nada sobre se estou dentro de casa ou não. Quando o antecedente é falso, dizemos que a implicação é **_trivialmente_** verdadeira.

|P|Q|P → Q|
|---|---|---|
|false|false|true|
|false|true|true|
|true|false|false|
|true|true|true|

---
## **Biconditional (↔)**

É uma implicação que vai a ambas as direções. Você pode lê-lo como “se e somente se”. **P ↔ Q é o mesmo que P → Q e Q → P tomados juntos**. Por exemplo, se P: “Está chovendo.” e Q: “Estou dentro de casa”, então **P ↔ Q** significa que **“Se está chovendo, então eu estou dentro de casa”, e “se eu estou dentro de casa, então está chovendo”.** Isso significa que podemos inferir mais do que poderíamos com uma simples implicação. **Se P é falso, então Q também é falso; se não está chovendo, sabemos que eu também não estou dentro de casa.**

| P     | Q     | P ↔ Q |
| ----- | ----- | ----- |
| false | false | true  |
| false | true  | false |
| true  | false | false |
| true  | true  | true  |

---
