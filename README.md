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

A análise mais detalhada do cluster 1 encontra-se comentada no código e na apresentação dos resultados. 

### 3) Classificação dos materiais – Cluster 1

### 4) Previsão da quantidade bruta de vendas – Cluster 1

### 5) Previsão da receita líquida – Cluster 3
