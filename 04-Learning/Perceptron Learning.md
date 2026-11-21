## O que é Perceptron Learning?

O Perceptron Learning é um algoritmo de aprendizado supervisionado utilizado para problemas de classificação binária, ou seja, quando queremos classificar alguma coisa em duas categorias, como 0 ou 1.

Diferente do KNN ([Nearest-Neighbor Classification](./Nearest-Neighbor%20Classification.md)), que classifica dados com base nos vizinhos mais próximos, o perceptron tenta encontrar uma **Decision Boundary** (fronteira de decisão) para separar as duas categorias.

**O perceptron aprende ajustando seus pesos (weights) e seu bias de acordo com os erros que comete.**

---
## Como funciona?

Imagine uma IA que precisa prever se vai chover utilizando duas informações:

x₁ = Umidade

x₂ = Pressão atmosférica

O perceptron utiliza a seguinte equação:

$$
w_0+w_1x_1+w_2x_2
$$

Onde:

Inputs (x): informações fornecidas ao modelo.

Weights (w): pesos que determinam a influência de cada entrada.

Bias (w₀): constante que ajusta o limite da decisão.

O modelo utiliza o resultado da equação para classificar:

Resultado ≥ 0: retorna 1 (vai chover).

Resultado < 0: retorna 0 (não vai chover).

---
## O que é Bias?

O bias é uma constante que permite ao perceptron ajustar o limite a partir do qual ele toma uma decisão.

Por exemplo, imagine uma IA que aprova alunos com base na nota:

$$
Resultado=Nota-6
$$

Nesse caso, o bias é -6.

Nota 5 → Resultado -1 → Reprovado.

Nota 6 → Resultado 0 → Aprovado.

Nota 8 → Resultado 2 → Aprovado.

Se alterarmos o bias para -7, a nota mínima para aprovação passa a ser 7.

Resumindo: os pesos controlam a influência das entradas, enquanto o bias ajuda a deslocar a fronteira de decisão.

---
## Decision Boundary

A Decision Boundary é a fronteira que separa as duas categorias.

Em um gráfico com duas entradas, essa fronteira é representada por uma linha.

O objetivo do perceptron é aprender pesos e bias que posicionem essa linha de maneira a classificar os dados corretamente.

Entretanto, nem sempre é possível separar todos os dados perfeitamente com uma linha reta. Essa é uma limitação do perceptron simples.

---
## Como o perceptron aprende?

O perceptron aprende corrigindo os pesos quando realiza uma classificação incorreta.

A fórmula do Perceptron Learning Rule é:

$$
w_i \leftarrow w_i+\alpha(y-h_w(x))x_i
$$

Onde:

wᵢ: peso atual.

α (alpha): Learning Rate, que controla o tamanho dos ajustes.

y: resposta correta.

h_w(x): previsão feita pelo perceptron.

xᵢ: valor da entrada correspondente ao peso.

---
## O que acontece durante o aprendizado?

O perceptron recebe uma entrada e faz uma previsão.

Compara sua previsão com a resposta correta.

Se acertar, não modifica os pesos.

Se errar, ajusta os pesos utilizando a fórmula.

Repete esse processo com os dados de treinamento.

### Exemplo:

Imagine que temos:

Peso atual: 0.5

Learning Rate: 0.1

Entrada: 3

Resposta correta: 1

Previsão do perceptron: 0

Aplicando a fórmula:

$$
w=0.5+0.1(1-0)\times3
$$

$$
w=0.8
$$

O peso foi atualizado de 0.5 para 0.8.

Como o perceptron previu 0 quando deveria prever 1, ele aumentou o peso para tentar corrigir o erro.

Importante
O perceptron não aprende criando novas regras manualmente. Ele aprende ajustando os valores numéricos dos pesos e do bias com base nos erros de classificação.

---
## Hard Threshold vs. Soft Threshold

O perceptron tradicional utiliza um Hard Threshold, que retorna apenas dois valores:

0 — Negativo

1 — Positivo

Isso significa que ele não consegue expressar incerteza diretamente.

Já uma função logística (Logistic Function) utiliza um Soft Threshold, produzindo valores entre 0 e 1, que podem ser interpretados como probabilidades em modelos apropriados.

---
## Resumo

O Perceptron Learning é um algoritmo que aprende a classificar dados ajustando pesos e bias.

Weights: determinam como cada entrada influencia a classificação.

Bias: ajuda a definir o limite da decisão.

Decision Boundary: fronteira que separa as categorias.

Learning Rate: controla o tamanho dos ajustes.

Learning Rule: fórmula usada para atualizar os pesos após um erro.

A principal ideia é que o perceptron aprende com seus erros, ajustando seus parâmetros para melhorar suas classificações.