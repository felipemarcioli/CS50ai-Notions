**Backtracking Search** é um algoritmo que resolve problemas de satisfação de restrições (CSPs) construindo uma solução aos poucos. Ele atribui um valor a uma variável por vez e usa **recursão** para continuar preenchendo as demais.

Se uma escolha impede a solução, o algoritmo desfaz essa escolha e tenta outra possibilidade.

**Funcionamento:**

1. Se a atribuição estiver completa, retorna a solução.
2. Seleciona uma variável ainda não preenchida.
3. Para cada valor do domínio, verifica se ele é compatível com as atribuições atuais.
4. Se for, atribui o valor e chama o algoritmo novamente.
5. Se a chamada retornar falha, desfaz a atribuição e tenta o próximo valor.
6. Se nenhum valor funcionar, retorna falha à chamada anterior.

**Inference (inferência)** usa as restrições para deduzir consequências de uma escolha antes de continuar a busca.

No **Maintaining Arc Consistency (MAC)**, após atribuir `X = valor`, restringimos o domínio de X a esse valor e executamos AC-3, começando pelos arcos `(Y, X)` dos seus vizinhos. Isso propaga reduções nos domínios.

Se algum domínio ficar vazio, voltamos imediatamente. Ao voltar, também restauramos os domínios e desfazemos as inferências daquela tentativa. Domínios não vazios, porém, não garantem uma solução completa.

**Exemplo de inferência durante a busca:**

|Variável|Domínio inicial|
|---|---|
|A|{1, 2}|
|B|{1, 2}|
|C|{1, 2}|

Restrições: **A ≠ B** e **B < C**.

Suponha que o backtracking comece escolhendo **A = 1**:

- Pela restrição A ≠ B, a inferência remove 1 do domínio de B. Portanto, **B só pode ser 2**.
- Pela restrição B < C, C precisaria ser maior que 2. Como não existe esse valor no domínio, **C fica sem opções**.
- O algoritmo detecta a falha sem precisar testar individualmente os valores de C.

Ele desfaz a tentativa e suas reduções de domínio, então escolhe **A = 2**. Agora, a inferência permite deduzir **B = 1** e **C = 2**, encontrando uma solução.

---
Related: [Inference](../01-Knowledge/Inference.md)