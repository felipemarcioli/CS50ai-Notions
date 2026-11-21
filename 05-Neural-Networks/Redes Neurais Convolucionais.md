Vimos que [Image Convolution (Kernel)](./Image%20Convolution%20(Kernel).md) é usado para adicionar filtros em uma imagem, mas como fariamos para adicionar kernels á um video?

Bom, um video é uma sequencia de imagem, com isso, usamos redes neurais convolucionais

Vale lembrar que Redes Neurais Convolucionais são usadas para processar qualquer tipo de dados que possuem uma estrutura em grade, como imagens ou videos.

![Neural Network - Image example 14](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%2014.png)

### Funciona da seguinte forma:

- **Camada Convolucional:** É o núcleo da rede. Ela aplica pequenos filtros chamados **kernels** (ou matrizes de pesos) que deslizam sobre a imagem de entrada. Cada kernel serve para extrair características específicas, como bordas, linhas, texturas ou formas geométricas.
- **Camada de _Pooling_ (Subamostragem):** Reduz o tamanho espacial (dimensionalidade) dos mapas de características gerados pela convolução. Isso diminui o esforço computacional e torna a rede mais invariante a pequenas mudanças de posição na imagem. Os tipos mais comuns são o _Max Pooling_ (que pega o maior valor da região) e o _Average Pooling_ (média).
- **Camada de Flattening (achatamento)**: é uma etapa de transição estrutural que transforma uma matriz de dados multidimensional em um único vetor linear (unidimensional), sem alterar ou processar os valores originais. Nas Redes Neurais Convolucionais, ela funciona como uma ponte indispensável, pegando os mapas de características espaciais gerados pelas camadas de convolução e pooling (em 3D) e enfileirando-os em uma sequência de dados 1D para que possam ser devidamente interpretados pelas camadas densas totalmente conectadas que realizam a classificação final.