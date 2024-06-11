# Desafio_03_Brain
Desafio Óleo de Palma

# Objetivo:
O desafio 3 proposto pelo BRAIN consiste no desenvolvimento  e treinamento de um modelo de IA de série temporal com base nos DataFrames contidos no arquivo "kddbr-2018.zip", sendo estes dados sobre a produção de alguns campos assim como características do solo e atmosfera deles, a partir destas informações visa-se a previsão da produção destes campos. Para isto o projeto foi dividido em 3 etapas.

# Etapa I - Tratamento de dados
Foi realizado uma preparação dos dados do DataFrame para que o modelo de IA possa ter um processo de aprendizagem mais limpo, para isso foi necessário a realização de algumas sub-etapas.

## União dos dados:
Inicialmente é feita a união dos arquivos fields e soil, para que em um único arquivo contenha todas as informações disponíveis

## Organização e remoção de dados:
Posteriormente é feita remoção dos dados que não possuimos o target ('production') disponível no arquivo train.csv e reorganização dos dados remanescentes. A remoção dos dados é feitas mesclando o data frame dos que possui todas a informações, 'campos', com o 'train.csv' que possui as informações de 'production' dos campos. Esta orgnização é feita utilizando a função '.sort_values', que utilizando alguns parâmetros definidos, obtemos uma melhor organização temporal, algo crucial para o desenvolvimento de um modelo de série temporal.


# Etapa II:
Nesta etapa fazemos a definição das features que serão utilizadas para treinamento do modelo.

## Análise de dados:
Consiste na seleção das features que serão usadas para o treinamento do modelo, esta é feita com base na análise de gráfica e dos dados obtidos atráves da etapa anterior em conjunto com o julgamento do desenvolvedor. Diversos gráficos foram feitos nesta etapa, porém foi mantido apenas aqueles que foram julgados utéis para seleção das features.

### Correlação dos dados
![alt text](/desafio03/imagens/grafico_corr.png)

### Produção de cada mês:
![alt text](/desafio03/imagens/prod_meses.png)

### Produção de cada campo:
![alt text](/desafio03/imagens/prod_fields.png)

# Etapa III - Desenvolvimento e treinamento do modelo:
## Treinamento da IA:
Com as features selecionadas foi feito o treinamento do modelo de diversas formas diferentes. Utilizou-se random forest regressor e linear regression, esses 2 métodos foram testados de diferentes formas, porém o melho resultado obtido foi de utilização do random forest regressor(sem a presença de janela temporal) utilizando todos os parametros selecionados previamentes. Através da métrica de avaliação 'mean absolute error', obteu-se um desempenho de 0,0776 aproximadamente.

### Desempenho do modelo:
![alt text](/desafio03/imagens/desempenho_model.png)
