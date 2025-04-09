**MSSubClass**: Identifica o tipo de habitação envolvido na venda. **Variável Categórica Nominal**

        20 1 ANDAR 1946 E MAIS RECENTE TODOS OS ESTILOS
        30 1 ANDAR 1945 E MAIS ANTIGO
        40 1 ANDAR COM SÓTÃO ACABADO TODAS AS IDADES
        45 1-1/2 ANDAR - INACABADO TODAS AS IDADES
        50 1-1/2 ANDAR ACABADO TODAS AS IDADES
        60 2 ANDARES 1946 E MAIS RECENTES
        70 2 ANDARES 1945 E MAIS ANTIGOS
        75 2-1/2 ANDARES TODAS AS IDADES
        80 SPLIT OU MULTI-LEVEL
        85 PISO DUPLO
        90 DUPLEX - TODOS OS ESTILOS E IDADES
       120 PUD (Desenvolvimento de Unidade Planeada) de 1 piso - 1946 e mais recente
       150 1-1/2 ANDARES PUD - TODAS AS IDADES
       160 PUD DE 2 ANDARES - 1946 E MAIS RECENTE
       180 PUD - MULTILEVEL - INCL SPLIT LEV/FOYER
       190 CONVERSÃO DE 2 FAMÍLIAS - TODOS OS ESTILOS E IDADES
    
- O Relatório do ProfileReport nos disse que essa coluna possui **Alta Correlação** com 4 campos: **Alley, BldgType, HalfBath, HouseStyle**.
  
**MSZoning**: Identifica a classificação geral de zonamento da venda. **Variável Categórica Nominal**

       A Agrícola - 0
       C Comercial - 10
       FV Residencial em Aldeia Flutuante - 65
       I Industrial - 0
       RH Residencial de Alta Densidade - 16
       RL Residencial de Baixa Densidade - 1151
       RP Parque Residencial de Baixa Densidade - 0 
       RM Residencial de Média Densidade - 218

- O Relatório do ProfileReport nos disse que essa coluna possui **Alta Correlação** com 3 campos: **Alley, Neighborhood, PoolQC**.
  
- Variável com dados **desbalanceados**, algumas categorias são muito mais frequentes do que outras. E a categoria **A - Agrícola(região)** não aparece nenhuma vez.

**LotFrontage**: Pés lineares da rua ligada à propriedade(extensão da fachada de um edifício ou lote que faz fronteira com uma via pública).
- Variável do tipo "float64", porém sem valores decimais, consequentemente com uma potencial **conversão de tipos**.
- O Relatório do ProfileReport nos disse que essa coluna possui **Alta Correlação** com 2 campos: **LotArea** e **Utilities**.

**LotArea**: Tamanho do lote em pés quadrados. **Variável Discreta "int64".**
- Essa medida corresponde à área total do terreno, incluindo a área construída e o espaço não edificado.
- O Relatório do ProfileReport nos disse que essa coluna possui **Alta Correlação** com 2 campos: **Alley** e **LotFrontage**

**Street**: Rua: Tipo de estrada de acesso à propriedade. **Variável Categórica Nominal**

       Cascalho Grvl - 6
       Pave Pavimentada - 1454
  
- O Relatório do ProfileReport nos disse que essa coluna possui **Alta Correlação** com 3 campos: **Alley**, **Fence** e **PoolQC**.
- Variável com dados **desbalanceados**, algumas categorias são muito mais frequentes do que outras.

**Alley**: Beco: Tipo de beco de acesso à propriedade
- O Relatório do ProfileReport nos disse que essa coluna possui **Alta Correlação** com 20 outros campos.
       Grvl Cascalho - 50
       Pave Pavimentado - 41
       NA Sem acesso ao beco - 1369

**LotShape**: Forma do lote: Forma geral da propriedade. **Variável Categórica Ordinal**

       Reg Regular - 925	
       IR1 Ligeiramente irregular - 484
       IR2 Moderadamente irregular - 41
       IR3 Irregular - 10
       
A forma do lote, ou a forma geral de uma propriedade, refere-se ao formato e às dimensões do terreno onde a propriedade está localizada. Essa forma pode variar significativamente e é um fator importante a ser considerado em diversos aspectos, como:

**1. Projeto arquitetônico**: A forma do lote influencia diretamente o projeto da construção, determinando como os espaços podem ser organizados e aproveitados. Lotes retangulares são geralmente mais fáceis de projetar, enquanto lotes irregulares podem exigir soluções criativas e personalizadas.

**2. Uso do solo**: A forma do lote pode afetar o uso do solo, determinando se é adequado para construção residencial, comercial ou industrial. Lotes com formatos específicos podem ser mais adequados para determinados tipos de atividades.

**3. Valor do imóvel**: *A forma do lote é um dos fatores que influenciam o valor do imóvel. Lotes regulares e com boa topografia tendem a ser mais valorizados do que lotes irregulares ou com declives acentuados.*

**LandContour**: Planura da propriedade. **Variável Categórica Nominal**
- Variável com dados **desbalanceados**, algumas categorias são muito mais frequentes do que outras.

       Lvl Quase plano/nível - 1311	
       Bnk Banked - Subida rápida e significativa do nível da rua até ao edifício - 63
       HLS Hillside - Inclinação significativa de um lado ao outro - 50
       Low Baixa depressão - 36

**Utilities**: Serviços públicos: Tipo de serviços públicos disponíveis. **Variável Categórica Nominal**
- O Relatório do ProfileReport nos disse que essa coluna possui **Alta Correlação** com 5 campos: **Alley**, **Fence**, **LotFrontage**, **MiscFeature**, **PoolQC**.
- Categoria Desbalanceada.

       AllPub Todos os serviços públicos (**E,G,W,& S**) - 1459
**Eletricidade (E)**
Descrição: Compreende a geração, transmissão e distribuição de energia elétrica para residências, empresas, indústrias e iluminação pública.
Importância: Essencial para o funcionamento da maioria das atividades modernas, como comunicação, transporte, saúde, educação e lazer.

**Gás (G)**
Descrição: Inclui a produção, distribuição e comercialização de gás natural ou GLP (gás liquefeito de petróleo) para uso doméstico, comercial e industrial.
Importância: Fonte de energia para aquecimento, cocção de alimentos, processos industriais e geração de energia em alguns casos.

**Água (W)**
Descrição: Abrange a captação, tratamento e distribuição de água potável para abastecimento humano, uso industrial, irrigação e outros fins.
Importância: Fundamental para a saúde, higiene, alimentação e diversas atividades econômicas.
Exemplos:
Captação de água em rios, lagos e aquíferos.
Tratamento de água em estações de tratamento (ETAs).
Coleta e tratamento de esgoto sanitário.
    
**Saneamento (S)**
Descrição: Engloba a coleta, transporte, tratamento e destinação final de esgoto sanitário, resíduos sólidos (lixo) e drenagem urbana (águas pluviais).
Importância: Essencial para a saúde pública, prevenção de doenças, proteção do meio ambiente e qualidade de vida.
Exemplos:
Coleta de esgoto em residências e estabelecimentos comerciais.
Tratamento de esgoto em estações de tratamento de esgoto (ETEs).
Coleta de lixo domiciliar e comercial.
Limpeza urbana de ruas e espaços públicos.
Drenagem de águas pluviais para evitar enchentes.

       NoSewr Eletricidade, gás e água (fossa séptica) - 0
       NoSeWa Apenas eletricidade e gás - 1
       ELO Apenas eletricidade - 0

**LotConfig**: LotConfig: Configuração do lote. **Variável Categórica Nominal**

       Inside Interior do lote - 1052
       Corner Lote de canto - 263
       CulDSac Cul-de-sac - 94
       FR2 Frente em 2 lados da propriedade - 47
       FR3 Frente em 3 lados da propriedade - 4

**LandSlope**: Declive da propriedade. **Variável Categórica Ordinal**
- Alta Correlação com: **PoolQC**.
- Desbalanceada.

       Gtl Declive suave - 1382
       Mod Declive moderado	- 65
       Sev Declive severo - 13

**Neighborhood**: Bairro: Localizações físicas dentro dos limites da cidade de Ames. **Variável Categórica Nominal**
- Alta Correlação com: **Alley, BsmtQual, MSZoning, PoolQC**.

**Condition1**: Proximidade de várias condições. **Variável Categórica Nominal**
- Desbalanceada.
	
       Artery Adjacente à rua arterial
        Feedr Adjacente à rua alimentadora	
       Norm Normal	
       RRNn A menos de 200' da linha férrea Norte-Sul
       RRAn Adjacente à ferrovia norte-sul
       PosN Perto de um elemento positivo fora do local - parque, cinturão verde, etc.
       PosA Adjacente a um elemento positivo fora do local
       RRNe A menos de 200' da Ferrovia Leste-Oeste
       RRAe Adjacente à Ferrovia Leste-Oeste

**Condition2**: Proximidade de várias condições (se estiver presente mais do que uma). **Variável Categórica Nominal**
		
       Artery Adjacente a uma rua arterial
       Feedr Adjacente à rua alimentadora	
       Norm Normal	
       RRNn A menos de 200' da linha férrea Norte-Sul
       RRAn Adjacente à linha férrea Norte-Sul
       PosN Perto de um elemento positivo fora do local - parque, cinturão verde, etc.
       PosA Adjacente a um elemento positivo fora do local
       RRNe A menos de 200' da Ferrovia Leste-Oeste
       RRAe Adjacente à Ferrovia Leste-Oeste

**BldgType**: Tipo de habitação. **Variável Categórica Nominal**
- Alta correlação com: **Alley, MSSubClass, PoolQC**.
- Desbalanceada.

       1Fam Moradia unifamiliar isolada	
       2FmCon Conversão para duas famílias; originalmente construída como habitação unifamiliar
       Duplx Duplex
       TwnhsE Townhouse Unidade final
       TwnhsI Townhouse Unidade interior

**HouseStylese**: Estilo de casa: Estilo de habitação. **Variável Categórica Nominal**
- Alta correlação com: **MSSubClass**.
	
       1Story Um andar
       1.5Fin Um andar e meio: 2º nível acabado
       1.5Unf Um andar e meio: 2.o andar inacabado
       2Story Dois pisos
       2.5Fin Dois andares e meio: 2º andar acabado
       2.5Unf Dois andares e meio: 2º nível inacabado
       SFoyer hall de entrada dividido
       SLvl Nível dividido

**OverallQual**: Qualidade geral: Avalia o material e o acabamento geral da casa. **Variável Categoria Ordinal**
- Alta correlação com 10 colunas.

       10 Muito excelente
       9 Excelente
       8 Muito bom
       7 Bom
       6 Acima da média
       5 Médio
       4 Abaixo da média
       3 Regular
       2 Fraco
       1 Muito fraco

**OverallCond**: Avalia o estado(condição) geral da casa. **Variável Categórica Ordinal**

       10 Muito excelente
       9 Excelente
       8 Muito bom
       7 Bom
       6 Acima da média	
       5 Médio
       4 Abaixo da média	
       3 Regular
       2 Fraco
       1 Muito fraco

**YearBuilt**: Ano de construção: Data de construção original.
- Alta correlação com 8 colunas.

**YearRemodAdd**: Data de remodelação (igual à data de construção se não houver remodelação ou adições).
- Alta correlação com: **GarageYrBlt, OverallQual, SalePrice, YearBuilt**.

**RoofStyle**: Tipo de telhado. **Variável Categórica Nominal**
- Desbalanceado.

       Flat	 Plano - 13
       Gable De duas águas - 1141
       Gambrel Gabrel (Celeiro) - 11
       Hip Quadril - 286
       Mansard Mansarda - 7
       Shed Galpão - 2

**RoofMatl**: Material do telhado. **Variável Categórica Nominal*
- Alta Correlação com: **Alley e MiscFeature**.
- Desbalanceada.

       ClyTile Barro ou telha - 1
       CompShg Telha padrão (composta) - 1434
       Membran Membrana - 1
       Metal Metal - 1
       Roll Rolo - 1
       Tar&Grv Cascalho e alcatrão - 11
       WdShake Tremores de madeira - 5  
       WdShngl Telhas de madeira - 6

**Exterior1st**: Revestimento exterior da casa. **Variável Categórica Nominal**
- Alta correlação com:**Exterior2nd**.
           
       AsbShng Telhas de amianto
       AsphShn Telhas de asfalto
       BrkComm Tijolo Comum
       BrkFace Tijolo à face
       CBlock Bloco de cimento
       CemntBd Placa de cimento
       HdBoard Placa dura
       ImStucc Imitação de estuque
       MetalSd Revestimento metálico
       Other Outros
       Plywood Contraplacado
       PreCast Pré-fabricado	
       Stone Pedra
       Stucco Estuque
       VinylSd Revestimento de vinil
       Wd Sdng Revestimento de madeira
       WdShing Telhas de madeira

**Exterior2nd**: Revestimento exterior da casa (se houver mais do que um material).**Variável Categórica Nominal**
- Alta correlação com:**Exterior1st**.
           
       AsbShng Telhas de amianto
       AsphShn Telhas de asfalto
       BrkComm Tijolo Comum
       BrkFace Tijolo à face
       CBlock Bloco de cimento
       CemntBd Placa de cimento
       HdBoard Placa dura
       ImStucc Imitação de estuque
       MetalSd Revestimento metálico
       Other Outros
       Plywood Contraplacado
       PreCast Pré-fabricado
       Stone Pedra
       Stucco Estuque
       VinylSd Revestimento de vinil
       Wd Sdng Revestimento de madeira
       WdShing Telhas de madeira

**MasVnrType**: Tipo de revestimento de alvenaria.**Variável Categórica Nominal** 
- Alta correlação com: **LowQualFinSF**.
           
       BrkCmn Tijolo Comum - 15
       BrkFace Face de tijolo - 445
       CBlock Bloco de cimento 
       None Nenhum
       Stone Pedra - 128


**MasVnrArea**: Área folheada de alvenaria em pés quadrados.
- Variável com muitos valores em 0. É também uma Variável do tipo "float64", porém com possibilidade de **conversão de tipos**.

**ExterQual**: Avalia a qualidade do material no exterior. **Variável Categórica Ordinal** 
**Alta correlação com: **Alley, KitchenQual, OverallQual**.
           
       Ex Excelente - 52
       Gd Bom - 488
       TA Médio/Típico - 906
       Fa Razoável - 14
       Po Pobre - 0

**ExterCond**: Avalia o estado atual do material no exterior. **Variável Categórica Ordinal**
- Desbalanceada.
           
       Ex Excelente - 3
       Gd Bom - 146
       TA Médio/Típico - 1282
       Fa Razoável - 28
       Po Pobre - 1

**Foundation**: Tipo de fundação. **Variável Categórica Nominal**
- Alta correlação com: **Alley, PoolQC, YearBuilt**.
		
       BrkTil Tijolo e telha - 146
       CBlock Bloco de cimento - 634
       PConc Contrete vazado - 647	
       Slab	 Laje - 24
       Stone Pedra - 6
       Wood Madeira - 3

**BsmtQual**: Avalia a altura do porão. **Variável Categórica Ordinal**
- Alta correlação com: **Alley, Neighborhood, OverallQual, YearBuilt**.
           
       Ex Excelente (100+ polegadas) - 121	
       Gd Bom (90-99 polegadas) - 618
       TA Típico (80-89 polegadas) - 649
       Fa Razoável (70-79 polegadas) - 35
       Po Pobre (<70 polegadas) - 0
       NA Sem porão

**BsmtCond**: Avalia o estado geral do porão. **Variável Categórica Ordinal**
- Alta correlação com: **PoolQC**.
          
       Ex Excelente
       Gd Bom - 65
       TA Típico - humidade ligeira permitida - 1311
       Fa Razoável - humidade ou algumas fissuras ou assentamento - 45
       Po Pobre - fissuração grave, assentamento ou humidade - 2
       NA Sem porão

**BsmtExposure**: Refere-se a paredes de nível de jardim ou de passagem. **Variável Categórica Ordinal**

       Gd Boa exposição - 134
       Av Exposição média (níveis divididos ou halls de entrada normalmente têm uma pontuação média ou superior) - 221	
       Mn Exposição mínima - 114
       No Não há exposição - 953
       NA Sem Porão

**BsmtFinType1**: Classificação da área acabada do subsolo. **Variável Categórica Ordinal**

        GLQ Bons alojamentos
       ALQ Alojamento médio
       BLQ Quartos para viver abaixo da média	
       Rec Sala de convívio média
       LwQ Baixa qualidade
       Unf Inacabado
       NA Sem Porão

**BsmtFinSF1**: Pés quadrados acabados tipo 1. **Variável Discreta**
- Alta correlação com: **BsmtUnfSF, PoolQC**.
- Muitos valores 0.

**BsmtFinType2**: Classificação da área acabada do subsolo (se houver vários tipos). **Variável Categórica Ordinal**
- Alta correlação com: **PoolQC**. 
- Desbalanceado.
           
       GLQ Bons alojamentos
       ALQ Alojamento médio
       BLQ Quartos para viver abaixo da média	
       Rec Sala de convívio média
       LwQ Baixa qualidade
       Unf Inacabado
       NA Sem subsolo

**BsmtFinSF2**: Pés quadrados acabados tipo 2. **Variável Discreta**
- Alta correlação com: **MiscFeature, PoolQC**. 
- Quantidade alta de valores zerados.

**BsmtUnfSF**: Pés quadrados inacabados de área de porão. **Variável Discreta**
- Alta correlação com: **BsmtFinSF1**.
- Quantidade alta de valores zerados.

**TotalBsmtSF**: Total de pés quadrados de área do porão. **Variável Discreta**
- Alta correlação com: **1stFlrSF, SalePrice**. 
- Muitos valores zerados. 

**Heating**: Tipo de aquecimento. **Variável Categórica Nominal**
- Alta correlação com: **PoolQC** 
- Desbalanceada.

       Floor Forno de chão
       GasA Forno de ar quente forçado a gás
       GasW Aquecimento a água quente ou vapor a gás
       Grav Forno de gravidade	
       OthW Aquecimento a água quente ou a vapor, exceto a gás
        Wall Forno de parede

**HeatingQC**: Qualidade e estado do aquecimento. **Variável Categórica Ordinal** 

        Ex Excelente
       Gd Bom
       TA Médio/Típico
       Fa Razoável
       Po Pobre

**CentralAir**:  Ar condicionado central. **Variável Binária** 
- Alta correlação com: **PoolQC**.
- Desbalanceada.                       
        N Não
        Y Sim

**Electrical**: Eléctrica: Sistema elétrico. **Variável Categórica Nominal**
- Alta correlação com: **PoolQC**.
- Desbalanceada.

       SBrkr Disjuntores padrão e Romex
       FuseA Caixa de fusíveis de mais de 60 AMP e toda a cablagem Romex (Média)	
       FuseF Caixa de fusíveis de 60 AMP e maioritariamente cablagem Romex (Razoável)
       FuseP Caixa de fusíveis de 60 AMP e cablagem maioritariamente em knob & tube (fraca)
       Mix Misto

**1stFlrSF**: pés quadrados do primeiro andar. **Discreta**
- Alta correlação com: **SalePrice, TotalBsmtSF**.

**2ndFlrSF**: Pés quadrados do segundo andar. **Discreta**
- Alta correlação com: **BedroomAbvGr, GrLivArea, TotRmsAbvGrd**. 
- Muitos zeros.

**LowQualFinSF**: Pés quadrados com acabamento de baixa qualidade (todos os andares). **Discreta**
- Alta correlação com: **MasVnrType**.
- Muitos zerados.

**GrLivArea**: pés quadrados de área de estar acima do nível do solo (solo). **Discreta**
- Alta correlação com: **2ndFlrSF, BedroomAbvGr, OverallQual, SalePrice, TotRmsAbvGrd**.

**BsmtFullBath**: Banheiros completos no porão. **Discreta Ordinal**

**BsmtHalfBath**: Meias casas de banho no porão. **Discreta Ordinal**
- Desbalanceada.

**FullBath**: Casas de banho completas acima do nível. **Discreta Ordinal**
- Alta correlação com: **MiscFeature**.

**HalfBath**: Meias casas de banho acima do nível. **Discreta Ordinal**
- Alta correlação com: **MSSubClass**.

**BedroomAbvGr**: Quartos acima do nível do solo (NÃO inclui quartos na cave)
- Alta correlação com: **2ndFlrSF, GrLivArea, TotRmsAbvGrd**.

**KitchenAbvGr**: Cozinhas acima do nível **Discreta Ordinal**
- Alta correlação com: **PoolQCC**
- Desbalanceada.
    
**KitchenQual**: Qualidade da cozinha **Categórica Ordinal**
- Alta correlação com: **ExterQual, OverallQual**
    
       Ex Excelente
       Gd Bom
       TA Típico/Médio
       Fa Razoável
       Po Pobre
       	
**TotRmsAbvGrd**: Total de divisões acima do nível do chão (não inclui casas de banho)
- Alta correlação com: **2ndFlrSF, BedroomAbvGr, GrLivArea, SalePrice**.

**Functional**: Funcionalidade da casa (Assume-se típica a menos que se justifiquem deduções). **Categórica Nominal**
- Alta correlação com: **PoolQC**.
- Desbalanceada.
    
       Typ	Funcionalidade típica
       Min1 Deduções menores 1
       Min2 Deduções menores 2
       Mod Deduções moderadas
       Maj1 Deduções principais 1
       Maj2 Deduções principais 2
       Sev Severamente danificado
       Sal Apenas salvamento
		
**Fireplaces**: Número de lareiras. **Discreta Ordinal**.

**FireplaceQu**: Qualidade da lareira. **Categórica Ordinal**

       Ex Excelente - Lareira de alvenaria excecional
       Gd Bom - Lareira de alvenaria no nível principal
       TA Média - Lareira pré-fabricada na sala de estar principal ou Lareira de alvenaria na cave
       Fa Razoável - Lareira pré-fabricada na cave
       Po Pobre - Fogão Ben Franklin
       NA Sem lareira
		
**GarageType**: Localização da garagem. **Categórica Nominal**
		
       2Types Mais de um tipo de garagem
       Attchd Anexada à casa
       Basment	Porão Garagem
       BuiltIn Built-In (a garagem faz parte da casa - normalmente tem uma divisão por cima da garagem)
       CarPort Car Port
       Detchd Separada da casa
       NA Sem garagem
		
**GarageYrBlt**: Ano de construção da garagem
- Alta correlação com 6 colunas.
           
**GarageFinish**: Acabamento interior da garagem **Categórica**
-Alta correlação com: **Alley, PoolQC**.

        Fin Acabado
       RFn Acabamento em bruto	
       Unf Inacabado
       NA Sem garagem
		
**GarageCars**: Tamanho da garagem em capacidade de carros. **Discreta Ordinal**
- Alta correlação com: *GarageArea**.

**GarageArea**: Tamanho da garagem em pés quadrados
- Alta correlação com outras 6 colunas.
- Muitos valores zerados.

**GarageQual**: Qualidade da garagem. **Categórica Ordinal**
- Alta correlação com: **GarageCond**
- Desbalanceada.

       Ex Excelente
       Gd Bom
       TA Típico/Médio
       Fa Razoável
       Po Pobre
       NA Sem garagem
		
**GarageCond**: Condição da garagem. **Categórica Ordinal**
- Alta correlação com: **GarageQual**
- Desbalanceada.

       Ex Excelente
       Gd Bom
       TA Típico/Médio
       Fa Razoável
       Po Pobre
       NA Sem garagem
		
**PavedDrive**: Entrada pavimentada. **Categórica Nominal**
- Alta correlação com: **PoolQC**.
- Desbalanceada.
           
       Y Pavimentada 
       P Pavimento parcial
       N Terra/cascalho
		
**WoodDeckSF**: Área do deck de madeira em pés quadrados
- Muitos valores zerados.
    
**OpenPorchSF**: Área de alpendre aberto em pés quadrados
- Muitos valores zerados.

**EnclosedPorch**: Área do alpendre fechado em pés quadrados
- Muitos valores zerados.

**3SsnPorch**: Área do alpendre de três estações em pés quadrados
- Alta correlação com: **Alley, PoolQC**.
- Desbalanceada.
    
**ScreenPorch**: Área do alpendre de tela em pés quadrados
- Muitos valores zerados.

**PoolArea**: Área da piscina em pés quadrados
- Alta correlação com: **Alley, MiscFeature**.
- Muitos valores zerados.

**PoolQC**: Qualidade da piscina. **Categórica Ordinal**
-- Alta correlação com 23 colunas.	

       Ex Excelente
       Gd Boa
       TA Média/Típica
       Fa Razoável
       NA Sem piscina
		
**Fence**: Qualidade da Cerca. **Categórica Nominal**
- Alta correlação com: **Street, Utilities**.
		
       GdPrv Boa privacidade
       MnPrv Privacidade mínima
       GdWo Boa madeira
       MnWw Mínimo de madeira/arame
       NA Sem Cerca

**MiscFeature**: Caraterística diversa não abrangida noutras categorias
- Alta correlação com 7 colunas.
- Desbalanceada.
		
       Elev Elevador
       Gar2 2ª Garagem (se não estiver descrita na secção da garagem)
       Othr Outros
       Shed  Galpão (mais de 100 SF)
       TenC Campo de ténis
       NA Nenhum
		
**MiscVal**: $Valor da caraterística diversa
- Alta correlação com: **Alley, MiscFeature**. 

**MoSold**: Mês vendido (MM)

**YrSold**: Ano vendido (AAAA)

**SaleType**: Tipo de venda
- Desbalanceada.
		
       WD Warranty Deed - Convencional
       CWD Escritura de Garantia - Dinheiro
       Escritura de Garantia VWD - Empréstimo VA
       Casa nova acabada de construir e vendida
       COD Escritura de Oficial de Justiça/Estado
       Contrato Con 15% de entrada em condições normais
       Contrato ConLw Baixa entrada e juros baixos
       Contrato ConLI Juros baixos
       Contrato ConLD Baixa entrada
       Outros
		
**SaleCondition**: Condição de venda
- Alta correlação com: **PoolQC**.
       Normal Normal Venda
       Abnorml Venda anormal - troca, execução hipotecária, venda a descoberto
       AdjLand Compra de terreno adjacente
       Alloca Allocation - duas propriedades ligadas com escrituras separadas, normalmente um condomínio com uma unidade de garagem	
       Family familiar Venda entre membros da família
       Partial A casa não estava concluída aquando da última avaliação (associada a casas novas)

**SalePrice**: Preço de venda **Alvo**.
- Alta correlação com outras 10 colunas.