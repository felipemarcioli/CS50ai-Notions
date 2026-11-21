É um algoritmo de busca local usado para encontrar boas soluções em problemas de otimização. Ele **aceita, às vezes, mudanças para pior**, permitindo escapar de mínimos ou máximos locais.

Diferentemente do [Hill Climbing](./Hill%20Climbing.md), ele não encerra a busca simplesmente porque não encontrou uma melhora imediata.

**Funcionamento**

1. Começa em um estado inicial (`current`).
    
2. Define a temperatura (`T`) da iteração.
    
3. Escolhe um vizinho aleatório.
    
4. Se o vizinho for melhor, aceita a mudança.
    
5. Se for pior, aceita ou rejeita conforme uma probabilidade.
    
6. **Se rejeitar, mantém** `**current**` **e continua na próxima iteração.**
    
7. No pseudocódigo do CS50, retorna o estado atual quando termina o número definido de iterações.
    

**Temperatura**

A temperatura é um parâmetro numérico que diminui durante a execução:

- **Alta:** maior probabilidade de aceitar pioras, favorecendo a exploração.
    
- **Baixa:** menor probabilidade de aceitar pioras, tornando a busca mais seletiva.
    

**Probabilidade de aceitar uma piora**

Para (T > 0):

[  
P = e^{\Delta E/T}  
]

(\Delta E) representa quanto o vizinho melhora o resultado; uma piora gera um valor negativo. Quanto maior a piora ou menor a temperatura, menor a chance de aceitá-la.

**Exemplo**

Considere rotas vizinhas com distâncias:

**B (10 km) → C (12 km) → D (8 km) → E (5 km)**

Para chegar à rota de 5 km, pode ser necessário aceitar temporariamente uma rota pior, de 12 km.

O algoritmo **não sabe antecipadamente** que essa mudança levará a uma solução melhor. Ele explora possibilidades e pode aceitar caminhos que não ajudam. Por isso, uma execução finita não garante encontrar a melhor solução global. Assim como no [Hill Climbing](./Hill%20Climbing.md)