[![author](https://img.shields.io/badge/Zeygler&nbsp;Oliveira-red.svg)](https://www.linkedin.com/in/zeygler-oliveira-a021a92a4/)
[![](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)

# HousePrices
Repositório criado para a [competição do Kaggle](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/overview) sobre a previsão de preço das casas na cidade de Ames, Iowa (Estados Unidos)

<p align="center"> 
  <a href="https://www.linkedin.com/in/zeygler-oliveira-a021a92a4/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
</p>

O repositório está estruturado da seguinte forma:
```
├── dados
├── notebooks
├── referencias
├── relatorios
```

- Na pasta `dados` estão os dados utilizados no projeto. Os arquivos `train.csv` e `test.csv` são os datasets utilizados originalmente. Os demais arquivos são os datasets gerados durante o projeto.
- Na pasta `notebooks` estão os notebooks organizados do projeto:
 - [`01-fb-eda.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/01-fb-eda.ipynb): Avaliar a pontuação do melhor modelo no momento, sem qualquer tratamento adequado e complexo de dados previamente.
  - [`02-fb-data_cleaning.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/02-fb-data_cleaning.ipynb): Foi realizada a limpeza nos dados, tratando valores faltantes seguinda as orientações do [dicionário de dados](https://github.com/ZeyOliveira/House-Prices/blob/main/referencias/data_description.txt) disponibilizado pela competição.
  - [`03-fb-execut_model.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/03-fb-execut_model.ipynb): Nessa etapa executamos os modelos que haviamos selecionado inicialmente, só que dessa vez após a limpeza dos dados.
  - [`04-fb-eda_preprocessing.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/04-fb-eda_preprocessing.ipynb): Aqui, foi feita a etapa de análise de correlações entre as variáveis, especialmente a variável alvo (SalePrice). Também foi feito o tratamento de colunas categóricas.
  - [`05-fb-execut_model.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/05-fb-execut_model.ipynb): Nessa etapa, apenas executamos os modelos de ML em questão, com as novas colunas categóricas que foram transformadas.
  - [`06-fb-execut_news_models.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/06-fb-execut_news_models.ipynb): Após finalizar o tratamento dos dados e executa-los nos modelos escolhidos inicialmente, nesse parte selecionamos novos modelos, mais específicamente o **RandomForest** e o **XGBoost**.
  - [`07-fb-utilites_gridsearch.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/07-fb-utilites_gridsearch.ipynb): Como o **RandomForest** e o **XGBoost** performaram melhor, escolhemos eles para otimização de hiperparâmetros usando a ferramenta **GridSearchCV**.
