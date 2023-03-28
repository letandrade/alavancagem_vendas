# Problema de alavancagem de vendas em uma empresa fictícia do ramo do varejo 
O objetivo deste case é trazer insights sobre o que um time de uma empresa fictícia do ramo do varejo poderia fazer para alavancar as vendas via análise de dados e machine learning. 

Para desenvolver as análises foi importado o dataset "base.csv" com as seguintes variáveis:

![download](https://user-images.githubusercontent.com/86376728/228221204-958ebaec-9a3c-4adf-a8eb-f3cc814deb83.png)

A resolução do problema foi dividida nos seguintes tópicos:

### 1) Contextualização

Na primeira etapa, busquei entender o que cada variável significava e como elas estavam relacionadas com o problema de negócio.
Um ponto importante é que nessa primeira etapa verifiquei que a quantidade de materiais era grande (2230 materiais únicos)
e que por esse motivo seria difícil desenvolver uma estratégia de vendas material a material, logo decidi criar agrupamentos
de materiais para que pudesse desenvolver uma estratégia. 

### 2) Segmentação dos materiais (Clusterização)

Utilizei o modelo K-means para clusterizar os materiais em grupos com característica comuns, e através desse modelo, melhorar os resultado de vendas da empresa. Como métricas de performance do cluster foi usado o índice de silhueta e o método do cotovelo. Foram gerados 2 grupos (0 e 1), sendo  o  cluster 1 o mais relevante por representar 50,38% da receita líquida com apenas 58 materiais, o que representa a oportunidade de desenvolver uma estratégia de venda com baixo esforço de implementação e alto impacto financeiro.

### 3) Classificação dos materiais – Cluster 1

Com o resultado do cluster foi possível verificar que o grupo mais relevante para alavancagem de vendas é cluster 1, sendo assim iniciou-se uma tarefa de aprendizagem supervisonada para classificar os produtos em pertencentes ao cluster 1 (1) e não pertencente ao cluster 1 (0). Esse modelo é importante para classificar novos materiais de acordo com o desempenho das variáveis históricas. Além disso, a classificação desses materiais traz a vantagem do conhecimento prévio do comportamento do material,ou seja, quais canais,regiões, marcas, categorias, campanhas e outras variáveis com as quais o material performa melhor em venda.

O modelo campeão foi um XGBClassifier treinado com as variáveis selecionadas pelo método RFE (Recursive Feature Elimination). Apresenta acuracidade de ~ 96,8% e recall ~ 67%.

### 4) Previsão da quantidade bruta de vendas – Cluster 1

As previsões da quantidade bruta de vendas e da receita líquida para os materiais do cluster 1 são importantes para conhecermos o comportamento da venda, além disso, traz benefícios como:

<p>➝ Controle de estoque (Maior acuracidade e menos custos com estoque excessivo).
<p>➝ Com a previsão é possível encontrar pontos de maior venda e elaborar ações de marketing eficientes.
<p>➝ Traz a possibilidade de preparar a equipe de vendas para uma alta demanda.
<p>➝ Possibilita gerar expectativas corretas sobre o faturamento esperado.
<p>➝ Ajuda a empresa a conhecer melhor o seu público-alvo e direcionar uma abordagem de vendas mais assertiva.

O modelo campeão para prever a quantidade bruta de vendas dos materiais do cluster 1 foi o Random Forest com feature selection, com a seguinte performance:

<p>Mean absolute error (MAE): 21698.916
<p>Mean squared error (MSE): 2508817703.987
<p>Mean absolute percentage error(MAPE): 0.479
<p>R² Score: 0.786

### 5) Previsão da receita líquida – Cluster 3
  
O modelo campeão para prever a receita líquida dos materiais do cluster 1 foi o Random Forest Regression com feature selection, com a seguinte performance:
  
<p>➝ Mean absolute error (MAE): 1678680.315
<p>➝ Mean squared error (MSE): 18468268225530.199
<p>➝ Mean absolute percentage error(MAPE): 0.726
<p>➝ R² Score: 0.809
  
### Para ter acesso aos resultados detalhados consulte o código e a apresentação de resultados.
