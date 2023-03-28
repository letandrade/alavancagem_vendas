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

Utilizei o modelo K-means para clusterizar os materiais em grupos com característica comuns, e através desse modelo, melhorar os resultado de vendas da empresa. Obtive como grupo mais relevante o cluster 1 pois representa 50,38% da receita líquida com apenas 58 materiais, o que representa a oportunidade de desenvolver uma estratégia de venda com baixo esforço de implementação e alto impacto financeiro.

O cluster 1 é o grupo de materiais com valor agregado alto (Média de preço: 839,95 reais) e uma boa recência em ciclos (Média de recência: 9,81 de 10), frequência em ciclos (Média de frequência: 44 de 52) e ticket-médio por ciclo (Média de ticket por ciclo: ~ 23 Milhões de reais).

Para alavancar as vendas é necessário focar no canal anon_s7(31,14% da venda líquida total), na categoria anon_S12 (43,30% da venda líquida total), e região anon_S1 (28,60% da venda líquida total). Além disso, o cluster possui uma quantidade pequena de 19 marcas.

Sobre as campanhas de venda, a parcela maior de participação (6,61% da quantidade de campanhas) corresponde as campanhas B (5,22%) e D (1,39%). Na matriz de correlação da quantidade de vendas e quantidade de campanhas por flag, o cluster 1 teve uma correlação positiva alta de 0.6 com a campanha B e uma correlação positiva fraca de 0.2 com a campanha D. Sendo B e D as campanhas que obtiveram maior retorno financeiro.
➝
### 3) Classificação dos materiais – Cluster 1

### 4) Previsão da quantidade bruta de vendas – Cluster 1

### 5) Previsão da receita líquida – Cluster 3
