# Análise dos Microdados do ENEM - Resumo

O objetivo é realizar uma análise qunatitativa sobre a dinâmica dos perfis inscritos no ENEM entre 2009 (ano em que passou por uma reformulação metodológica, tomando uma forma similar à que se é conhecida atualmente) e 2019, tendo em vista as condições socioeconômicas ou quaisquer outras características que possam ser o reflexo do cenário socioeconômico nacional.  

Com os [dados](https://github.com/e-moncao-lima/UC_Data_Science-Analise_ENEM/blob/dados/README.md) já à disposição no Google Drive, é aconselhável, caso o Google Colab seja utilizado, que se monte o Drive na plataforma. 

Ao tentar realizar o pré-processamento dos microdados dos anos 2009 a 2015, houve o seguinte erro: (imagem ERRO).

## Pré-processamento

Foi realizado um pré-processamento dos microdados do ENEM de 2017 a 2019, retirando 
algumas colunas julgadas desnecessárias. Escolheu-se trabalhar apenas com os inscritos presentes nas provas, enxugando, assim, os datasets.

## Análise Exploratória dos Dados

Escrever aqui

## Algoritmos de Machine Learning

Foram executados dois algoritmos de ML, a serem: Feature Selection e Redes Neurais (regressão).

### Feature Selection

Foi realizado para reduzir as dimensões do dataset, já que possuem em torno de 120 colunas cada. A ideia era reduzir o máximo ao mesmo tempo que informações úteis não fossem perdidas. Em outros trabalhos, foram utilizados, em sua maioria, o algoritmo PCA (Principal Component Analysis) e a matriz de correlação entre vaiáveis, como neste [aqui](https://medium.com/@wesleywatanabe/data-science-machine-learning-enem-regressao-linear-5cd140459dc3). Nesse trabalho, optou-se por utilizar o método *SelectKBest* do módulo *SciKit Learn* juntamente com a função de scores *f_regression* (F-score), visto que *mutual_info_regression* não suporta tão bem conjuntos grandes de dados e esgota toda a RAM disponível do Google Colab..

O hiperparâmetro *k* escolhido foi 7, representando as 7 features mais relevantes  a serem escolhidas de acordo com o F-score (menos de 10% do dataset original). A métrica utilizada é o próximo algoritmo de ML a seguir, com o *Mean Squared Error* e *Mean Absolute Error*. 

O dado de treinamento do algoritmo de FS foi o dataframe com todas as features normalizadas com *MinMaxScaler*.

(INSERIR as Features Escolhidas)


### Redes Neurais

Para tesstar o algoritmo anterior, foi utilizado um algoritmo simples de redes neurais para prever as notas do ENEM com as *features* previamente selecionadas. A ideia é que se tenha um resultado satisfatório com elas.

Para prever notas do ENEM, outros trabalhos fizeram uso de Random Forest, Decision Trees e KNN, como visto [aqui](https://ensinandomaquinasblog.wordpress.com/2017/12/15/modelos-preditivos-de-notas-de-redacao-do-enem-2015/).

Para a rede neural, foi escolhido utilizar somente uma *hidden layer* por ser um algoritmo simples de teste de regressão de uma variável, tendo esta camada 5 neurônios. Os neurônios foram escolhidos empiricamente como um número entre a quantidade de entradas (7) e saídas (1).

As métricas utilizadas foram *Mean Squared Error (MSE)* e *Mean Absolute Error (MAE)*. Os dados de entrada foram as 7 *features* previamente mencionadas dividias em 75%-25% Train e Test dataset com cross-validation de 20%.







## Códigos

O notebook python relativo à análise do ENEM do ano de 2019 está [aqui]().






