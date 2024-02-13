# **IMPLEMENTAÇÃO DE UMA REDE NEURAL**
Projeto avaliativo desenvolvido no âmbito da disciplina de computação inteligente, no Instituto Federal de Educação, Ciência e Tecnologia (IFS). O problema escolhido foi de classificação simples para classificar a flores de íris. O objetivo foi treinar a rede neural para aprender a distinguir entre as três espécies de flores com base nas medidas das características (comprimento e largura das sépalas e pétalas).
 

## **DESCRIÇÃO DO DATASET**
[*Link do dataset, basta clicar*]( https://archive.ics.uci.edu/dataset/53/iris-/)

Ele contém informações sobre três espécies de íris (setosa, versicolor e virginica), com quatro características medidas em cada amostra:

1. Comprimento da sépala em centímetros.
2. Largura da sépala em centímetros.
3. Comprimento da pétala em centímetros.
4. Largura da pétala em centímetros.

![Captura de tela 2024-02-12 212729](https://github.com/Gabriellacode/FloresIris_RedeNeural/assets/108696464/8783bb53-3a08-4dfb-bd38-238784ed8bf1)

**fonte:** https://pt.wikipedia.org/wiki/Conjunto_de_dados_flor_Iris

O conjunto de dados Iris possui 150 amostras no total, com 50 amostras para cada uma das três espécies de íris.
É bastante usado para demonstrar técnicas de classificação, agrupamento e visualização de dados, sendo uma referência básica para muitos algoritmos de aprendizado de máquina. Ele também é considerado um bom ponto de partida para iniciantes devido ao seu tamanho gerenciável e à clareza das informações fornecidas, o que facilita a compreensão e a prática de várias técnicas de análise de dados e aprendizado de máquina.


### **QUAL TIPO DE REDE NEURAL UTILIZADO**
  Rede neural artificial do tipo Feedforward. No nosso caso, a rede é construída usando a classe Sequential do TensorFlow, o que implica que cada camada é adicionada sequencialmente uma após a outra. Isso cria uma arquitetura de rede neural do tipo feedforward, onde a informação flui da entrada para as camadas ocultas e finalmente para a camada de saída.


### **ESTRUTURADO DA  REDE** 
Implementação em python utilizando Tensorflow/Keras. A estrutura consiste em três camadas densas:

**1. Camada de Entrada:**

A primeira camada é uma camada densa com 6 neurônios. Ela recebe dados com quatro características, este valor corresponde ao número de características do conjunto de dados Iris.


**2.  Camada Oculta:**

A segunda camada é outra camada densa com 12 neurônios. Ambas as camadas ocultas utilizam a função de ativação ReLU' (Unidade Linear Retificada): esta função de ativa os neurônios se o valor de entrada for > 0, retornando o próprio valor de entrada. Se o valor de entrada for 0<= , retorna zero. 
Ela introduz não-linearidade na rede, ajudando a aprender e representar relações complexas nos dados.


**3. Camada de Saída:**

A terceira camada é a camada de saída com 3 neurônios, correspondendo às três classes possíveis no problema da classificação das flores Iris ('Iris-setosa', 'Iris-versicolor', 'Iris-virginica'). A função de ativação 'softmax' é usada na camada de saída para produzir uma distribuição de probabilidade sobre as classes. Ela converte um conjunto de valores para uma distribuição de probabilidades, onde cada classe recebe um valor de probabilidade entre 0 e 1, e a soma de todas as probabilidades é igual a 1. Isso permite que o modelo faça previsões sobre várias classes, escolhendo a classe com a maior probabilidade como a resposta final.
É utilizado o otimizador Adam: um algoritmo de otimização muito popular em redes neurais profundas, escolhido por ser eficiente em muitos problemas. Ele ajusta a taxa de aprendizado de forma adaptativa com base nas médias dos gradientes recentes.


### **DADOS DO EXPERIMENTO** 
A acurácia final do modelo nos dados de teste é de aproximadamente 98%. Isso significa que, ao usar os dados de teste, o modelo alcança uma precisão de classificação de 98% para as amostras que não foram vistas durante o treinamento.
Para testes foram utilizados 33% dos dados totais (⅓), e 67% foram utilizados para treinamento. Foram definidas 100 épocas e o tamanho do batch foi igual a 4.

**As  métricas de avaliação do modelo foram usadas:**

**Precisão (Precision):** medida da precisão do modelo em prever instâncias positivas. É calculada como o número de verdadeiros positivos dividido pela soma de verdadeiros positivos e falsos positivos para cada classe. No nosso caso, variou de 94% a 100%, dependendo da classe.

**Revocação (Recall):**  medida da completude do modelo em encontrar todas as instâncias positivas. É calculada como o número de verdadeiros positivos dividido pela soma de verdadeiros positivos e falsos negativos para cada classe. No nosso caso, variou de 94% a 100% também.

**F1-Score:** média harmônica entre precisão e recall. É útil quando há um desequilíbrio nas classes, pois leva em consideração tanto falsos positivos quanto falsos negativos. No nosso caso, ficou em torno de 97% para a maioria das classes.

 **Support:** representa o número de ocorrências de cada classe no conjunto de testes.

**Acurácia (Accuracy):** medida geral da precisão do modelo em prever corretamente todas as classes. É a relação entre o número de previsões corretas e o número total de previsões.
A convergência do modelo (a estabilização das métricas de treinamento como a perda/loss e a acurácia) ao longo das épocas, aparentou está sendo alcançada por volta da 50ª época,  a precisão atingiu em torno de 95% a 98%, e a perda estava diminuindo gradualmente.


