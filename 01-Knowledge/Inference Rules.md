A verificação de modelo não é um algoritmo eficiente porque tem que considerar todos os modelos possíveis antes de dar a resposta (um lembrete: uma consulta R é verdadeira se sob todos os modelos (atribuições da verdade) onde o KB é verdadeiro, R também é verdadeiro). As regras de inferência nos permitem gerar novas informações com base no conhecimento existente sem considerar todos os modelos possíveis.

As regras de inferência são geralmente representadas usando uma barra horizontal que separa a parte superior, a premissa, da parte inferior, a conclusão. A premissa é qualquer conhecimento que tenhamos, e a conclusão é o que o conhecimento pode ser gerado com base na premissa.

![Inference Rules - example 1](../PNGs/01-Knoweledge.png/Inference%20Rules%20-%20example%201.png)

Neste exemplo, nossa premissa consiste nas seguintes proposições:

- Se está chovendo, então Harry está dentro.
- Está a chover.

Com base nisso, a maioria dos humanos razoáveis pode concluir que

- O Harry está lá dentro.

---
## Modus Ponens

O tipo de regra de inferência que usamos neste exemplo é **Modus Ponens**, que é uma maneira extravagante de dizer que se conhecemos uma implicação e seu antecedente para ser verdade, então o consequente é verdadeiro também.

![Inference Rules - example 2](../PNGs/01-Knoweledge.png/Inference%20Rules%20-%20example%202.png)

---
## **And Eliminação**

Se uma **And** proposição é verdadeira, então qualquer uma proposição atômica dentro dela é verdadeira também. **Por exemplo, se sabemos que Harry é amigo de Ron e Hermione, podemos concluir que Harry é amigo de Hermione.**

![Inference Rules - example 3](../PNGs/01-Knoweledge.png/Inference%20Rules%20-%20example%203.png)

---
## **Eliminação de Dupla Negação**

**Uma proposição que é negada duas vezes é verdadeira**. 
Por exemplo, considere a proposição “Não é verdade que Harry não passou no teste”. 
Podemos analisar da seguinte maneira: “Não é verdade que (Harry não passou no teste)”, ou “¬(Harry não passou no teste)”, e, finalmente “¬(¬(Harry passou no teste))”. 
**As duas negações se anulam, marcando a proposição de “Harry passou no teste” como verdadeira.**

![Inference Rules - example 4](../PNGs/01-Knoweledge.png/Inference%20Rules%20-%20example%204.png)

---
## **Implicação Eliminação**

Uma implicação é equivalente a uma **Or** relação entre o **antecedente negado** e o **consequente**. Como exemplo, a proposição “Se está chovendo, Harry está dentro” é equivalente à proposição “(não está chovendo) ou (Harry está dentro)”.

![Inference Rules - example 5](../PNGs/01-Knoweledge.png/Inference%20Rules%20-%20example%205.png)

Este pode ser um pouco confuso. No entanto, considere a seguinte tabela de verdade:

| P     | Q     | P → Q | ¬P ∨ Q |
| ----- | ----- | ----- | ------ |
| false | false | true  | true   |
| false | true  | true  | true   |
| true  | false | false | false  |
| true  | true  | true  | true   |

Uma vez que **P → Q** e **¬P ∨ Q** têm a mesma atribuição de valor de verdade, nós sabemos que eles são equivalentes logicamente. 
Outra maneira de pensar sobre isso é que uma implicação é verdadeira se qualquer uma das duas condições possíveis for atendida: primeiro, se o antecedente é falso, a implicação é trivialmente verdadeira (como vimos na seção **Implication** do [Logica proposicional](./Logica%20proposicional.md)). 
Isso é representado pelo precedente negado P em ¬P ∨ Q, **o que significa que a proposição é sempre verdadeira se P é falsa.**
Em segundo lugar, a implicação é verdadeira quando o **antecedente** é verdadeiro somente quando o **consequente** é verdadeiro também. 
Isto é, se P e Q são ambos verdadeiros, então ¬P ∨ Q é verdade. No entanto, se P é verdadeiro e Q não é, então ¬P ∨ Q é falso.

---
## **Eliminação Bicondicional**

Uma proposição bicondicional é equivalente a uma implicação **And** seu inverso com um e conjuntivo. 
Por exemplo, “Está chovendo se e somente se Harry estiver dentro” é equivalente a (“Se está chovendo, Harry está dentro” **And(E)** “Se Harry está dentro, está chovendo”).

![Inference Rules - example 6](../PNGs/01-Knoweledge.png/Inference%20Rules%20-%20example%206.png)

---
## **Lei de De Morgan**

É possível transformar um **And** conectivo em um **Or** conjuntivo. Considere a seguinte proposição: “Não é verdade que tanto Harry quanto Ron passaram no teste”. A partir disso, é possível concluir que “Não é verdade que Harry passou no teste” Ou “Não é verdade que Ron passou no teste”. Isto é, para que a **And** proposição anteriormente seja verdadeira, pelo menos uma das proposições nas **Or** proposições deve ser verdadeira.

![Inference Rules - example 7](../PNGs/01-Knoweledge.png/Inference%20Rules%20-%20example%207.png)

Da mesma forma, é possível concluir o inverso. Considere a proposição: “Não é verdade que Harry ou Ron passaram no teste”. Isso pode ser reformulado como “Harry não passou no teste” E “Ron não passou no teste”.

![Inference Rules - example 8](../PNGs/01-Knoweledge.png/Inference%20Rules%20-%20example%208.png)

---
## **Propriedade Distributiva**

Uma proposição com dois elementos que são agrupados com **And** ou **Or** conectivos pode ser distribuída, ou dividida em, unidades menores que consistem em **And** e **Or**.

![Inference Rules - example 9](../PNGs/01-Knoweledge.png/Inference%20Rules%20-%20example%209.png)
![Inference Rules - example 10](../PNGs/01-Knoweledge.png/Inference%20Rules%20-%20example%2010.png)

---
## **Problemas de Conhecimento e Busca**

A inferência pode ser vista como um problema de pesquisa com as seguintes propriedades:

- Estado inicial: iniciando a base de conhecimento
-  Ações: regras de inferência (**Inference Rules**)
- Modelo de transição: nova base de conhecimento após inferência
- Teste de meta: verificar se a declaração que estamos tentando provar está no KB
- Função de custo do caminho: o número de passos na prova

Isso mostra o quão versáteis são os algoritmos de pesquisa, permitindo-nos obter novas informações com base no conhecimento existente usando regras de inferência.

---
Related: [Inference](./Inference.md)