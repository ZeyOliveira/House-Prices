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
  - [`02_clustering.ipynb`](https://github.com/ZeyOliveira/ifood_case_data_analyst/blob/main/notebooks/02_clustering.ipynb): Neste notebook foi feito um estudo do comportamento dos dados no gráfico com o objetivo de saber qual o melhor pré-processamento mais adequado para cada coluna; Em seguida, foi feito a clusterização e algumas visualizações.
  - [`03_clustering_pca.ipynb`](https://github.com/ZeyOliveira/ifood_case_data_analyst/blob/main/notebooks/03_clustering_pca.ipynb)): Alguns códigos do notebook anterior foi reaproveitado. A novidade nesse notebook foi a utilização do PCA para redução de dimensionalidade.
  - [`04_classification.ipynb`](https://github.com/ZeyOliveira/ifood_case_data_analyst/blob/main/notebooks/04_classification.ipynb)): Aqui foi testado alguns modelos de classificação, que foram avaliados e o modelo selecionado para dar continuidade ao projeto foi o LogisticRegression.
  - [`05_classification_logreg.ipynb`](https://github.com/ZeyOliveira/ifood_case_data_analyst/blob/main/notebooks/05_classification_logreg.ipynb)): Para finalizar o projeto foi feito a otimização de hiperparâmetros no SelectKBest e no LogisticRegression, e o modelo foi novamente avaliado, assim foi obtido o resultado final.
  - [`auxiliary_functions.py`](https://github.com/ZeyOliveira/ifood_case_data_analyst/blob/main/notebooks/auxiliary_functions.py): Arquivo com funções auxiliares usados no projeto.
