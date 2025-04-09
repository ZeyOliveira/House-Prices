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

## Etapa 01:
[`01-fb-eda.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/01-fb-eda.ipynb):
- Nesse etapa foi feita apenas o básico para conseguir verificar qual seria o resultado sem fazer nenhum tratamento nem engenharia dos dados. Para simplificar, substituí todos os valores vazios por -1, o -1 foi selecionado para "dizer" ao modelo que ele não é naturalmente parte do conjunto, e porque não possuimos as informações originais a respeito desses dados, em um contexto empresarial buscariamos essa informação junto ao negócio; E eliminamos todas as colunas de texto.  

- Criei os modelos utilizando 3 algoritmos: **Regressão Linear**, **Árvore de Regressão** e **KNeighborsRegressor** e avaliei os resultados utilizando o **erro médio absoluto(MAE)** e o **erro quadrático médio(MSE)**, dando preferência ao segundo pois era o critério usando na competição.  
- O score público retornado pelo Kaggle foi: 0,25476. Você pode acessar a imagem na pasta `imagens`, com o nome de **"01_resultado_projeto"**.


## Etapa 02:
[`02-fb-data_cleaning.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/02-fb-data_cleaning.ipynb):
  - Comecei a fazer um processo de limpeza dos dados, analisando valores vazios e informações faltantes para escolher a melhor estratégia de tratamento. Em algumas colunas, valores vazios representavam *ausência dos atributos na casa*, como por exemplo o *valor vazio na coluna de piscina* significava que aquele imóvel *não possuia piscina*. Nesse caso o vazio era uma informação.
 - Em outros casos onde a informação realmente estava ausente, usei tratamentos como substituir pela média da coluna, utilizar uma agregação para encontrar a melhor média para o atributo, utilizar a moda, entre outros tratamentos.


## Etapa 03:
[`03-fb-execut_model.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/03-fb-execut_model.ipynb):
  - Utilizei os mesmos modelos da **Etapa 1** (que pode ser visto no arquivo da etapa anterior) e o score público retornado pelo Kaggle foi: 0,33718.
 - O aumento do erro(piora no resultado do modelo) mesmo após ter sido feito tratamentos mais apropriados para os valores faltantes, muito provavelmente é devido a alta correlação(multicolinearidade) entre as features do nosso database, tendo em vista que o modelo que performou melhor até então, foi o LinearRegression, mas esse modelo sofre bastante com multicolinearidade definindo coeficientes instáveis e/ou errôneos, deve ter sido isso que o prejudicou na generalização, mas resolvi isso posteriormente.


## Etapa 04:
  - [`04-fb-eda_preprocessing.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/04-fb-eda_preprocessing.ipynb):
  - Utilizei a base gerada na etapa 2, com os dados já tratados, e comecei primeiramente analisando a correlação entre as variáveis numéricas e os valores mais frequentes das variáveis de texto. Para tratar colunas do tipo texto, iniciei eliminando as colunas com muitos valores iguais e depois utilizei lambda function e criei minhas próprias funções para aplicar e fazer o tratamento.
 - Além disso, também utilizei o **OneHotEncoder** para o tratamento das variáveis que não possuem relação de ordem e o **OrdinalEncoder** para aquelas ordenadas.
 - Por fim, me aprofundei nas colunas de garagem para fazer um completo entendimento dessa categoria de variáveis. Com mais tempo e melhor entendimento do negócio, poderia estender essa análise para todos os outros grupos de colunas.
 - Nesta etapa foi gerada os arquivos `train_3.csv` e `test_3_1.csv` onde foi feito um tratamento genérico para todas as colunas de texto.


## Etapa 05
[`05-fb-execut_model.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/05-fb-execut_model.ipynb):
  - Nessa etapa, apenas executei os modelos de ML em questão, com as novas colunas categóricas que foram transformadas.
  - O score público do Kaggle de: 0,46279.
  - O resultado foi muito pior devido ao aumento do número de colunas e aos modelos utilizados. Isso será tratado nas próximas etapas!


# Etapa 06: Adicionando Novos Modelos
  - [`06-fb-execut_news_models.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/06-fb-execut_news_models.ipynb):
  - Após finalizar o tratamento dos dados e executa-los nos modelos escolhidos inicialmente, nesse parte selecionei novos modelos, mais específicamente o **RandomForest** e o **XGBoost**.
  - Apenas com a mudança dos modelos consegui um resultado muito melhor, muito provavelmente o LinearRegression passou a ser um modelo muito simples para os dados em questão, principalmente após o aumento de colunas, ele não estava conseguindo capturar a complexidade(variação) dos dados adequadamente.
  - Entre o RandomForest e o XGBoost, o RF foi o que teve o melhor resultado nas métricas MAE e MSE, utilizei o arquivo resultante para submeter ao Kaggle
  - [`07-fb-utilites_gridsearch.ipynb`](https://github.com/ZeyOliveira/House-Prices/blob/main/notebooks/07-fb-utilites_gridsearch.ipynb): Como o **RandomForest** e o **XGBoost** performaram melhor, escolhi eles para otimização de hiperparâmetros usando a ferramenta **GridSearchCV**.
  - Para o **RandomForest** o score resultante foi: 0,15570.
  - Para o **XGBoost** o score resultante foi: 0,15753.


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
