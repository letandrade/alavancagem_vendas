# Problema de alavancagem de vendas em uma empresa fictícia do ramo de varejo 

### 1.0 Descrição 
O objetivo deste case é trazer insights sobre o que um time de uma empresa fictícia do ramo de varejo poderia fazer para alavancar as vendas via análise de dados e machine learning. 
<p>Para criar uma estratégia de alavancagem de vendas priorizei um grupo de materias que representa uma oportunidade de aumento de vendas com baixo esforço de implementação e relevante impacto financeiro. Além disso, desenvolvi um modelo de classificação dos materiais com o objetivo de identificar os materiais do grupo priorizado e um modelo de regressão para prever a quantidade bruta de vendas dos materiais.

### 2.0 Como usar o projeto

➝ Linguagem Python
<p>➝ Base em csv

### 3.0 Desenvolvimento e resultados

Para desenvolver as análises foi importado o dataset "base.csv" com as seguintes variáveis:

![download](https://user-images.githubusercontent.com/86376728/228221204-958ebaec-9a3c-4adf-a8eb-f3cc814deb83.png)

A resolução do problema foi dividida nos seguintes tópicos:

### 3.1) Contextualização

Na primeira etapa, busquei entender o que cada variável significava e como elas estavam relacionadas com o problema de negócio.
Um ponto importante é que nessa primeira etapa verifiquei que a quantidade de materiais era grande (2230 materiais únicos)
e que por esse motivo seria difícil desenvolver uma estratégia de vendas material a material, logo decidi criar agrupamentos
de materiais para que pudesse desenvolver uma estratégia. 

### 3.2) Segmentação dos materiais (Clusterização)

Utilizei o modelo K-means para clusterizar os materiais em grupos com característica comuns, e através desse modelo, melhorar os resultado de vendas da empresa. Como métricas de performance do cluster foi usado o índice de silhueta e o método do cotovelo. Foram gerados 2 grupos (0 e 1), sendo  o  cluster 1 o mais relevante por representar 50,38% da receita líquida com apenas 58 materiais, o que representa a oportunidade de desenvolver uma estratégia de venda com baixo esforço de implementação e alto impacto financeiro.

O cluster 1 é o grupo de materiais de alto valor agregado (Média de preço: 839,95 reais) e uma boa recência em ciclos (Média de recência nos últimos 10 ciclos: 9,81 de 10), frequência em ciclos (Média de frequência: 44 de 52) e ticket-médio por ciclo (Média de ticket por ciclo: ~ 23 Milhões de reais).

Para alavancar as vendas é necessário focar no canal anon_s7(31,14% da venda líquida total), na categoria anon_S12 (43,30% da venda líquida total), e região anon_S1 (28,60% da venda líquida total). Além disso, o cluster possui uma quantidade pequena de 19 marcas.

A campanha de venda mais relevante no cluster 1 foi a campanha B pois há uma correlação positiva alta de ~ 60% entre a quantidade de campanhas realizadas e o valor de receita líquida. Como alternativa a campanha B, sugiro uma redistribuição dos investimentos das campanhas A e C para a campanha D.

### 3.3) Classificação dos materiais

Com o resultado do cluster foi possível verificar que o grupo mais relevante para alavancagem de vendas é cluster 1, sendo assim iniciou-se uma tarefa de aprendizagem supervisonada para classificar os produtos em pertencentes ao cluster 1 (1) e não pertencente ao cluster 1 (0). Esse modelo é importante para classificar novos materiais de acordo com o desempenho das variáveis históricas. Além disso, a classificação desses materiais traz a vantagem do conhecimento prévio do comportamento do material,ou seja, quais canais,regiões, marcas, categorias, campanhas e outras variáveis com as quais o material performa melhor em venda.

O modelo campeão foi um XGBClassifier treinado com as variáveis selecionadas pelo método RFE (Recursive Feature Elimination), com a seguinte performance:

<p>Accuracy: 96,8%
<p>Precision: 77,00%
<p>Recall: 67,00%
<p>F1 - Score: 72,00%

### 3.4) Previsão da quantidade bruta de vendas por ciclo dos materiais do cluster 1

A previsão da quantidade bruta de vendas é importante para conhecermos o comportamento da venda, além disso, traz benefícios como:

<p>➝ Controle de estoque (Maior acuracidade e menos custos com estoque excessivo).
<p>➝ Com a previsão é possível encontrar pontos de maior venda e elaborar ações de marketing eficientes.
<p>➝ Traz a possibilidade de preparar a equipe de vendas para uma alta demanda.
<p>➝ Possibilita gerar expectativas corretas sobre o faturamento esperado.
<p>➝ Ajuda a empresa a conhecer melhor o seu público-alvo e direcionar uma abordagem de vendas mais assertiva.

O modelo campeão para prever a quantidade bruta de vendas dos materiais do cluster 1 foi o Random Forest Regressor com feature selection, com a seguinte performance:

<p>Mean absolute error (MAE): 21698.916
<p>Mean squared error (MSE): 2508817703.987
<p>Mean absolute percentage error(MAPE): 0.479
<p>R² Score: 0.786
 
 ### 4.0 Conclusão
 
A proposta de solução trouxe insights relevantes sobre os melhores canais, regiões, categorias, campanhas e outras características onde o cluster 1 tem uma boa performance de receita líquida. Ter o perfil de um grupo de materiais mapeado é essencial para se ter um bom escoamento do estoque. 
 
Com o modelo de classificação foi possível verificar as variáveis que possuem maior influência na classificação dos materiais como pertencentes ao cluster 1. E com o modelo de regressão foi possível prever a quantidade bruta de vendas por ciclo dos materiais do cluster 1. 

 É preciso dizer que os modelos de classificação e previsão criados podem ser aplicados a materiais novos do cluster 1, no entanto, o ideal é que esses produtos apresentem um período transacional de pelo menos 6 meses. 
 
### Para ter acesso aos resultados detalhados consulte o código e a apresentação de resultados.
