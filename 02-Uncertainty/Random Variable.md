Uma variável aleatória é uma variável na teoria da [Probability](./Probability.md) com um domínio de valores possíveis que ela pode assumir. 

Por exemplo, para representar possíveis resultados ao rolar um dado, podemos definir uma variável aleatória _Roll_, que pode assumir os valores {_1, 2, 3, 4, 5, 6_}. 

Para representar o status de um voo, podemos definir uma variável _Flight_ que assume os valores {_no prazo, atrasado, cancelado_}.

Muitas vezes, estamos interessados na probabilidade com que cada valor ocorre. Representamos isso usando uma distribuição de probabilidade. Por exemplo,

- P(_Vôo = na hora_) = 0.6
- P(_Vôo = atrasado_) = 0,3
- P(_Voo = cancelado_) = 0,1

Para interpretar a distribuição de probabilidade com palavras, isso significa que há uma chance de 60% de que o voo esteja a tempo, 30% de chance de que ele esteja atrasado e 10% de chance de ser cancelado. 
Note que, como mostrado anteriormente, a soma as probabilidades de todos os resultados possíveis é de 1.

Uma distribuição de probabilidade pode ser representada de forma mais sucinta como vetor. 
Por exemplo, **P**(_Flight_) = < _0,6, 0,3, 0,1_ >. 
Para que esta notação seja interpretável, os valores têm uma ordem definida (no nosso caso, _no prazo, atrasada, cancelada_).

---
## **Independência**

Independência é o conhecimento de que a ocorrência de um evento não afeta a probabilidade do outro evento. 

Por exemplo, ao rolar dois dados, o resultado de cada dado é independente do outro. Rolar um 4 com o primeiro dado não influencia o valor do segundo dado que nós rolamos. 

Isso se opõe a eventos dependentes, como nuvens pela manhã e chuva à tarde. 

Se estiver nublado pela manhã, é mais provável que chova à tarde, **então esses eventos são dependentes**.