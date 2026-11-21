**Redes Neurais Feed-Forward** são o tipo de redes neurais que discutimos até agora, onde os dados de entrada são fornecidos à rede, o que eventualmente produz alguma saída. 

Um diagrama de como as redes neurais feed-forward funcionam pode ser visto abaixo.

![Neural Network - Image example 15](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%2015.png)

Ao contrário disso, **as Redes Neurais Recorrentes** consistem em uma estrutura não-linear, onde a rede usa sua própria saída como entrada. 

Por exemplo, o [captionbot](https://www.captionbot.ai) da Microsoft é capaz de descrever o conteúdo de uma imagem com palavras em uma frase. 

Isso é diferente da classificação, pois a saída pode ter um comprimento variável com base nas propriedades da imagem. 

Embora as redes neurais feed-forward sejam incapazes de variar o número de saídas, as redes neurais recorrentes são capazes de fazer isso devido à sua estrutura. 

Na tarefa de legendagem, uma rede processaria a entrada para produzir uma saída e, em seguida, continuaria processando a partir desse ponto, produzindo outra saída e repetindo o quanto necessário.

![Neural Network - Image example 16](../PNGs/05-Neural%20Network.png/Neural%20Network%20-%20Image%20example%2016.png)

Redes neurais recorrentes são úteis nos casos em que a rede lida com sequências e não um único objeto individual. Acima, a rede neural precisava produzir uma sequência de palavras. 

No entanto, o mesmo princípio pode ser aplicado à análise de arquivos de vídeo, que consistem em uma sequência de imagens, ou em tarefas de tradução, onde uma sequência de entradas (palavras no idioma de origem) é processada para produzir uma sequência de saídas (palavras no idioma de destino).