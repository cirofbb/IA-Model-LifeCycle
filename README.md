# Análise de Churn de Clientes com KNN

Este projeto em Python explora a análise de churn de clientes utilizando o algoritmo K-Nearest Neighbors (KNN). O objetivo é prever quais clientes têm maior probabilidade de deixar a base ("Churn"). O projeto envolve o carregamento, pré-processamento de dados e aplicação do modelo KNN, seguido pela avaliação de seu desempenho.

## Conteúdo do Projeto

O notebook Python aborda os seguintes passos:

1.  **Carregamento e Pré-Processamento de Dados com Pandas:**
    * Carregamento do dataset "AT\_Customer\_Churn" em um DataFrame Pandas.
    * **Eliminação de Variáveis:** Remoção das colunas "Customer Value" e "Status" por serem consideradas irrelevantes para a modelagem ou por causarem vazamento de dados.
    * **Transformação de Variável:** Conversão da variável "Seconds of Use" para "Hours of Use" dividindo os valores por 3600 e renomeando a coluna.

2.  **Separação em Treino e Teste:**
    * Divisão do DataFrame pré-processado em conjuntos de treino e teste na proporção de 70% para treino e 30% para teste, garantindo a avaliação do modelo em dados não vistos.

3.  **Identificação do Melhor K para KNN:**
    * Exploração de diferentes valores de K (número de vizinhos) para o algoritmo KNN.
    * Justificativa da escolha do melhor valor de K com base em técnicas como a análise da curva de erro no conjunto de validação (implícito na busca pelo melhor K) para otimizar o desempenho e evitar overfitting ou underfitting.

4.  **Execução do Modelo KNN com o Melhor K:**
    * Treinamento do modelo KNN utilizando o valor de K identificado como o mais adequado no conjunto de treino.
    * Avaliação do desempenho do modelo no conjunto de teste, apresentando a métrica de **acurácia**.

5.  **Explicação das Curvas de Aprendizado para Avaliação de Overfitting:**
    * Explicação conceitual de como as curvas de aprendizado (plotando o desempenho do modelo nos conjuntos de treino e validação em função do tamanho do conjunto de treino) podem ser utilizadas para diagnosticar problemas de overfitting (alto desempenho no treino e baixo na validação com aumento do tamanho da amostra) ou underfitting (baixo desempenho em ambos os conjuntos).

6.  **Aplicação de KNN com Validação Cruzada:**
    * Aplicação do modelo KNN com o mesmo valor de K ótimo, utilizando a técnica de **validação cruzada com 5 dobras** no conjunto de treino.
    * Apresentação da **acurácia média** obtida através das diferentes dobras da validação cruzada, fornecendo uma estimativa mais robusta do desempenho do modelo.

7.  **Influência do Parâmetro K no Overfitting em Modelos KNN:**
    * Explicação da relação entre o valor de K e o overfitting em modelos KNN. Valores de K muito pequenos tendem a tornar o modelo mais sensível ao ruído nos dados de treino, levando ao overfitting. Valores de K muito grandes podem suavizar demais as fronteiras de decisão, causando underfitting.

8.  **Importância da Abordagem Treino-Teste na Prevenção de Overfitting:**
    * Discussão sobre como a separação dos dados em conjuntos de treino e teste é crucial para evitar o overfitting. O conjunto de teste serve como uma amostra independente para avaliar o quão bem o modelo generaliza para dados não vistos durante o treinamento.

9.  **Curva ROC e Métrica AUC:**
    * Criação e apresentação da **curva ROC (Receiver Operating Characteristic)** para o modelo KNN.
    * Apresentação da métrica **AUC (Area Under the ROC Curve)**, que quantifica a capacidade do modelo de distinguir entre as classes positivas e negativas.

10. **Curva Precision-Recall e Métrica Average Precision:**
    * Criação e apresentação da **curva Precision-Recall** para o modelo KNN.
    * Apresentação da métrica **Average Precision**, que resume a curva Precision-Recall. Essa métrica é especialmente útil para datasets desbalanceados.

11. **Matriz de Confusão e Métricas de Avaliação:**
    * Apresentação da **matriz de confusão**, que detalha o número de verdadeiros positivos, verdadeiros negativos, falsos positivos e falsos negativos.
    * Apresentação das métricas de **acurácia**, **precision** (precisão) e **recall** (revocação) calculadas a partir da matriz de confusão, fornecendo uma visão completa do desempenho do classificador.

12. **Avaliação da Adequação do Modelo KNN para o Cenário de Dados:**
    * Discussão sobre as vantagens e desvantagens do modelo KNN em relação ao dataset de churn de clientes apresentado. Considerações sobre a interpretabilidade, sensibilidade à escala das features, custo computacional e adequação para a natureza dos dados (por exemplo, número de features, tamanho do dataset).

## Como Usar

Para executar este projeto, você precisará ter o Python instalado, juntamente com as seguintes bibliotecas:

* pandas
* scikit-learn
* matplotlib (para visualização das curvas)

Você pode instalar as dependências utilizando o pip:

```bash
pip install pandas scikit-learn matplotlib
