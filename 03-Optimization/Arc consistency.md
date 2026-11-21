## Arc Consistency — Consistência de Arco

Um arco **X → Y** é consistente quando **cada valor do domínio de X possui pelo menos um valor compatível no domínio de Y**, respeitando a restrição entre as variáveis. Esse valor compatível é chamado de **suporte**.

Para tornar um arco consistente, removemos do domínio da primeira variável os valores que não possuem suporte na segunda.

### Exemplo

|Variável|Domínio|
|---|---|
|X|{1, 2, 3}|
|Y|{1, 2, 3}|

**Restrição: X < Y.**

**1. Verificando o arco X → Y**

Para cada valor de X, buscamos pelo menos um Y maior que ele:

- **X = 1:** possui suporte em Y = 2 ou Y = 3.
    
- **X = 2:** possui suporte em Y = 3.
    
- **X = 3:** não possui suporte, pois nenhum valor de Y é maior que 3. Portanto, removemos 3 do domínio de X.
    

**2. Verificando o arco Y → X**

Para cada valor de Y, buscamos pelo menos um X menor que ele:

- **Y = 1:** não possui suporte, pois nenhum valor de X é menor que 1. Portanto, removemos 1 do domínio de Y.
    
- **Y = 2:** possui suporte em X = 1.
    
- **Y = 3:** possui suporte em X = 1 ou X = 2.
    

A restrição continua sendo **X < Y** nos dois sentidos. O que muda é qual domínio estamos verificando.

### Resultado

Os domínios ficam:

- **X: {1, 2}**
    
- **Y: {2, 3}**
    

Isso **não significa que qualquer combinação dos valores restantes seja válida**. Por exemplo, X = 2 e Y = 2 não satisfazem a restrição, embora ambos permaneçam nos respectivos domínios, pois cada um possui suporte em outro valor.

**Arc consistency reduz os domínios eliminando valores sem suporte. Ela não lista as soluções e, em um CSP geral, não garante que exista uma solução completa.**