 Explorando Modelos de Machine Learning para Predição de Churn 

Recentemente, trabalhei em um projeto para prever a taxa de churn em uma base de dados de clientes utilizando diferentes modelos de machine learning. Aqui está um resumo das etapas que segui, as comparações das métricas de desempenho, como os modelos se comportaram antes e depois da tunagem, e o que cada métrica significa:

Pré-processamento dos Dados:

Inicialmente, carreguei o dataset e realizei a limpeza, removendo a coluna customerID e verificando a presença de valores nulos. Em seguida, transformei as variáveis categóricas em variáveis dummy para facilitar o uso nos modelos.
Modelagem:

Testei três modelos principais: Regressão Logística, Árvore de Decisão e Random Forest. Para cada um deles, separei os dados em treino e teste (70/30), ajustei os modelos e avaliei suas performances utilizando várias métricas.
Aprimoramento com Grid Search:

Para otimizar os modelos, utilizei Grid Search para ajustar os hiperparâmetros da Regressão Logística e do Random Forest, buscando maximizar a performance, especialmente o recall, que era a métrica de maior interesse.
Comparação de Métricas:

Antes da Tunagem:

Regressão Logística:
Acurácia teste: 79.67%
F1 Score teste: 58.31%
Precisão teste: 64.10%
Recall teste: 53.48%
Árvore de Decisão:
Acurácia teste: 72.51%
F1 Score teste: 49.39%
Precisão teste: 48.38%
Recall teste: 50.45%
Random Forest:
Acurácia teste: 77.96%
F1 Score teste: 53.17%
Precisão teste: 61.11%
Recall teste: 47.06%
Após a Tunagem:

Regressão Logística Tunada:
Acurácia teste: 79.53%
F1 Score teste: 58.06%
Precisão teste: 63.75%
Recall teste: 53.30%
Árvore de Decisão (não tunada):
Acurácia teste: 72.51%
F1 Score teste: 49.39%
Precisão teste: 48.38%
Recall teste: 50.45%
Random Forest Tunado:
Acurácia teste: 79.57%
F1 Score teste: 55.43%
Precisão teste: 66.01%
Recall teste: 47.77%
Integração das Métricas:

Após a obtenção dos resultados, anexei as predições dos três modelos (Regressão Logística, Árvore de Decisão e Random Forest), tanto antes quanto depois da tunagem, ao dataset original. Isso permitiu bater os resultados e realizar análises comparativas entre as diferentes abordagens.
Entendendo as Métricas:

Acurácia: Mede a porcentagem de previsões corretas sobre o total. É útil quando as classes estão equilibradas, mas pode ser enganosa em casos de desequilíbrio.
F1 Score: É a média harmônica entre precisão e recall, sendo mais relevante quando há uma necessidade de equilíbrio entre as duas.
Precisão: Indica a proporção de verdadeiros positivos entre as previsões positivas feitas pelo modelo, mostrando a exatidão das previsões positivas.
Recall: Mede a capacidade do modelo de identificar todos os verdadeiros positivos, sendo crucial em cenários onde é importante capturar o máximo de casos positivos.
O Melhor Modelo:

Random Forest Tunado foi considerado o melhor modelo no geral. Embora a Regressão Logística tenha apresentado uma acurácia similar e um melhor equilíbrio entre as métricas, o Random Forest Tunado obteve uma precisão mais alta, o que é essencial em cenários onde minimizar falsos positivos é crítico. Além disso, o Random Forest também demonstrou uma robustez maior em relação à variação dos dados, o que o torna uma escolha mais confiável para este tipo de problema.
Insights:

A análise das métricas mostrou que, para a Regressão Logística, a tunagem não trouxe uma melhoria significativa, enquanto para o Random Forest, a tunagem melhorou ligeiramente a acurácia e a precisão, mas com um impacto misto nas outras métricas.
Este projeto reforçou minha compreensão sobre técnicas de pré-processamento, ajuste de hiperparâmetros, e a importância de validar os resultados comparando modelos antes e depois da tunagem.
