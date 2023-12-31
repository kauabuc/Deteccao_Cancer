﻿# Detecçãao de Cancêr 
 Projeto feito com intuito de aprimorar meus conhecimentos e botar eles em prática. Usando o dataset que pode ser encontrado em 'data.csv' ou no <a href="https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data">Kaggle</a> seguindo o link. O Dataset é sobre informações de possíveis causas de cancêr mamário maligno ou 'confortável', foi feita aplicação de dois algoritmos de machine learning com a precisão de 96% em futuros diagnosticos.
 Nesse projeto foi usada as seguintes tecnologias e frameworks:
 Python
 NumPy 
 Pandas
 Matplotlib
 Seaborn
 SkLearn
 E nos modelos de Machine Learning para treinar o algoritimo foi usado Logistic Regresion (sklearn) e Random Forest (sklearn) tudo feita da ide da anaconda do jupyter notebook.

 # Dentro do Projeto
 Foi feito algumas etapas e vou detalhar as seguinte aqui e o que pensei e usei para estruturá-las.
 Todos os passos a seguir podem ser vistos no código/arquivo BreastCancer.ipynb
 ### Processamento dos Dados e exploração 

 Importamos as bibliotecas necessárias em primeiro momento e utilizando o pandas e sua função para transformar o arquivo csv em dataset,
 depois foi feita uma ánalise exploratória dos dados utilizando algumas funções bastante comuns do pandas como Head (para mostrar os dados no dataframe),
 colums (para checar as colunas presentes no dataframe) e o describe (que faz calculos sobre todas colunas mostrando alguns valores importantes)

 ### Manipulação e Transoformação dos Dados

 Depois desses passos, fiz o check de colunas que apresentavam dados nulos e notei que uma coluna continha valores inválidos e foi feita a remoção da mesma utilizando a função drop do 
 pandas. Fazendo de novo a função isnull para encontrar mais valores ausentes e o restante dos dados estava de acordo.

 Após isso teria que ser feita a transformação dos atributos categóricos M = Maligno == 1, B = Bom == 0,
 utilizando a função do pandas get_dummies trasnformando em valores númericos favoráveis aos modelos.

### Ánalise dos Dados 

Usando a função seaborn de countplot montamos um gráfico com a quantidade de pessoas com seus respectivos diagnóstico.

Também foi feito dois gráficos com as correlações das colunas com o diagnostico. Sendo um gráfico de barra utilizando a função corrwith e outro
sendo um heatmap do Seaborn mostrando com mais detalhes suas respectivas correlações.

### Dados para Treinamento

Após isso foi feita a separação dos dados para montar os modelos de testes onde deixamos apenas a coluna do diagnostico em y (Alvo) e as restantes (menos idcliente)
em x.
E utilizando uma função do sklearn train_test_split separamos os dados em dados de treinamento x e y (80%) e dados de teste (20%). 
Após essa transformação usamos o método de padronização do sklearn StandardScaler para deixar os dados de x_treino e x_teste padronizados e normalizados para uma melhor compreensão do modelo.

## Modelo de Logistic Regresion
Foi feita a importação do modelo usando o sklearn, montando os dados de treinamento dentro do modelo e fizemos a previsão.
Os resultados obtidos foram de accuracia de 96% e precisão de 95% utilizando a função accuracy_score e precision_score.
Após isso foi feita a matriz de confusão dos acertos tendo apenas 4 erros totais dentro dos dados de teste.
E para finalizar foi feita a validação dos dados utilizando a função cross_val_score obtedos os resultados de precisão de 97,8% e
e o Desvio Padrão com 1,98%.

## Modelo de Random Forest 
Foi feito o mesmo processo do outro modelo, sendo importado do skleran o modelo RandomForestClassifier.
Os resultados obtidos foram de os mesmos 96% de accuracia e 93% de precisão sendo um pouco pior que o outro modelo.
E na validação dos dados com o cross_val_score tendo a precisão de 96% e desvio padrão de 3%.

