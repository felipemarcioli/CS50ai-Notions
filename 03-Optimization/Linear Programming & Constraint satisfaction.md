É um método de otimização que busca **maximizar ou minimizar uma função objetivo, respeitando restrições**, com todas essas expressões sendo lineares.

Um problema de programação linear possui:
- **Variáveis de decisão:** valores que queremos descobrir.
    
- **Função objetivo:** o que queremos maximizar, como lucro, ou minimizar, como custo.
    
- **Restrições:** limites que a solução precisa respeitar, como tempo e recursos disponíveis.


**Exemplo: produção de uma padaria**

|Produto|Lucro|Tempo|Farinha|
|---|---|---|---|
|Bolo|R$ 30|2 horas|1 kg|
|Torta|R$ 20|1 hora|1 kg|

Disponibilidade: **8 horas e 5 kg de farinha**.

Definimos (x) como a quantidade de bolos e (y) como a quantidade de tortas.

O objetivo é **maximizar o lucro**:

**Lucro = 30x + 20y**

Em que:
- **x** = quantidade de bolos.
    
- **y** = quantidade de tortas.

Precisamos respeitar as seguintes restrições:
- **Tempo:** 2x + y ≤ 8 — no máximo 8 horas disponíveis.
    
- **Farinha:** x + y ≤ 5 — no máximo 5 kg disponíveis.
    
- **Quantidades não negativas:** x ≥ 0 e y ≥ 0.

A solução ótima é produzir **3 bolos e 2 tortas**:
- **Lucro:** 30 × 3 + 20 × 2 = **R$ 130**.
    
- **Tempo:** 2 × 3 + 2 = **8 horas**.
    
- **Farinha:** 3 + 2 = **5 kg**.

Essa combinação gera o maior lucro possível respeitando todas as restrições.

Produzir 8 tortas daria um lucro maior, mas exigiria 8 kg de farinha. Portanto, seria uma **solução inviável**: uma solução válida precisa respeitar **todas as restrições simultaneamente**.

**Por que “linear”?**

As expressões contêm somas de variáveis multiplicadas por constantes, como (30x + 20y). Não contêm termos como (x^2) ou (xy).

**Observação:** programação linear permite valores fracionários. Exigir que as variáveis sejam inteiras caracteriza um problema de _programação inteira_.

---
## Constraint satisfaction

Constraint satisfaction problems são problemas onde variaveis precisam atribir um valor e ao mesmo tempo estar favorendo algumas condições pré estabelecidas.

No caso da torta, as variaveis são o lucro, e como queremos deixar ele o maximo possivel é preciso respeitar algumas condições que estabelecemos antes, o quantidade de horas e de farinha

- variavel: lucro
- condições: quantidade de farinha e tempo