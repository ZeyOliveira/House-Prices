[![author](https://img.shields.io/badge/Zeygler&nbsp;Oliveira-red.svg)](https://www.linkedin.com/in/zeygler-oliveira-a021a92a4/)
[![](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)

# HousePrices
Repositório criado para a [competição do Kaggle](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/overview) sobre a previsão de preço das casas na cidade de Ames, Iowa (Estados Unidos)

<p align="center"> 
  <a href="https://www.linkedin.com/in/zeygler-oliveira-a021a92a4/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
</p>

![heatmap](https://github.com/ZeyOliveira/House-Prices/blob/main/imagens/correlacao_heatmap.png)

O repositório está estruturado da seguinte forma:
```
├── dados
├── notebooks
├── referencias
```

- Na pasta `dados` estão os dados utilizados no projeto. Os arquivos `train.csv` e `test.csv` são os datasets utilizados originalmente. Os demais arquivos são os datasets gerados durante o projeto.
- Na pasta `notebooks` estão os notebooks organizados do projeto.
- Na pasta `referencias` estão os dicionários de dados, o [Dicionário traduzido pro português](https://github.com/ZeyOliveira/House-Prices/blob/main/referencias/01_dicionario_de_dados.md); E o [Dicionário original](https://github.com/ZeyOliveira/House-Prices/blob/main/referencias/data_description.txt), disponibilizado pela competição.

## Etapa 01
 - [`01-fb-eda.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/01-fb-eda.ipynb): Nesse etapa fizemos apenas o básico para conseguir verificar qual seria o resultado sem fazer nenhum tratamento nem engenharia dos dados. Para simplificar, substituímos todos os valores vazios por -1, o -1 for selecionado para "dizer" ao modelo que ele não é naturalmente parte do conjunto, e porque não possuimos as informações originais a respeito desses dados, em um contexto empresarial buscariamos essa informação junto ao negócio; E eliminamos todas as colunas de texto.
Criamos os modelos utilizando 3 algoritmos: **Regressão Linear**, **Árvore de Regressão** e **KNeighborsRegressor** e avaliamos os resultados utilizando o **erro médio absoluto(MAE)** e o **erro quadrático médio(MSE)**, dando preferência ao segundo pois era o critério usando na competição.
O score público retornado pelo Kaggle foi: 
  - [`02-fb-data_cleaning.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/02-fb-data_cleaning.ipynb): Foi realizada a limpeza nos dados, tratando valores faltantes seguinda as orientações do [dicionário de dados](https://github.com/ZeyOliveira/House-Prices/blob/main/referencias/data_description.txt) disponibilizado pela competição.
  - [`03-fb-execut_model.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/03-fb-execut_model.ipynb): Nessa etapa executamos os modelos que haviamos selecionado inicialmente, só que dessa vez após a limpeza dos dados.
  - [`04-fb-eda_preprocessing.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/04-fb-eda_preprocessing.ipynb): Aqui, foi feita a etapa de análise de correlações entre as variáveis, especialmente a variável alvo (SalePrice). Também foi feito o tratamento de colunas categóricas.
  - [`05-fb-execut_model.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/05-fb-execut_model.ipynb): Nessa etapa, apenas executamos os modelos de ML em questão, com as novas colunas categóricas que foram transformadas.
  - [`06-fb-execut_news_models.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/06-fb-execut_news_models.ipynb): Após finalizar o tratamento dos dados e executa-los nos modelos escolhidos inicialmente, nesse parte selecionamos novos modelos, mais específicamente o **RandomForest** e o **XGBoost**.
  - [`07-fb-utilites_gridsearch.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/07-fb-utilites_gridsearch.ipynb): Como o **RandomForest** e o **XGBoost** performaram melhor, escolhemos eles para otimização de hiperparâmetros usando a ferramenta **GridSearchCV**.


O projeto foi desenvolvido utilizando o Python 3.12.8 Para reproduzir o projeto, crie um ambiente virtual com o Conda, ou ferramenta similar, com o Python 3.12+ e instale as bibliotecas abaixo:

| Biblioteca       | Versão |
| ---------------- | ------ |
| Matplotlib       | 3.9.4  |
| NumPy            | 2.1.3 |
| Pandas           | 2.2.2  |
| Scikit-Learn     | 1.6.1  |
| Seaborn          | 0.13.2 |

Python version: 3.12.8


Essas são as bibliotecas principais utilizadas no projeto. O [relatório com a EDA](https://drive.google.com/file/d/1ABvcthaRopj2CZFP4e4hHX7xORcXu6LA/view?usp=sharing), se não conseguir visualizar o relatório no Drive, faça o Download e abra-o no seu navegador, ele foi gerado com a biblioteca [ydata-profiling](https://github.com/ydataai/ydata-profiling), instale-a se quiser reproduzir o relatório.
