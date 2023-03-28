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

Estratégias de venda para o cluster 1:

Desenvolver campanhas de marketing que enfatizem o valor dos materiais para o cliente, independente do preço do material. É um cluster com materiais de valor agregado alto que precisa ser alinhado a um público-alvo específico, os que não se preocupam com preço, mas esperam valor (qualidade, diferenciação e outros) no material.

Garantir uma boa experiência de compra. Investir em um ambiente acolhedor, atendimento atencioso, transparência sobre as características dos produtos e flexibilidade de opções.

É necessário direcionar os produtos para canais e regiões específicas,fazer uma boa análise dos dados garante um bom escoamento do produto.

Como o sucesso desse cluster depende principalmente do match com o público-alvo, investir em estratégias de marketing inbound para conseguir novos cliente. Segundo SIQUEIRA,"No Inbound Marketing, é o cliente que procura pela empresa e não o contrário. Ou seja, são realizadas ações com o intuito de atrair o potencial cliente para seu blog ou site e, a partir dessa atração, é feito todo um trabalho de relacionamento com essa pessoa. Esse relacionamento é desempenhado por meio de conteúdo personalizado e autoral".

Outra estratégia para obter novos clientes é a demonstração do produto, nesse momento o cliente conhecerá o produto e despertará o desejo de compra.

Para produtos com valor alto é uma estratégia investir em um pós-venda com serviços acima da média, o que gera valor aos olhos do cliente, atende a expectativa de diferenciação e retém o público-alvo.

Para complementar a estratégia de vendas foi desenvolvido um modelo de classificação para identificar os materiais do cluster 1 e 2 modelos de regressão para prever a quantidade de venda bruta e valor de receita líquida do cluster 1.

Comentários sobre o cluster 0

O cluster 0 representa do 49,62% do total de vendas líquidas e 64,83% da quantidade total de vendas, no entanto, esse cluster possui 2172 materiais únicos, essa quantidade quando comparada a quantidade de materiais do cluster 0 (53 materiais) evidencia o alto esforço para desenvolver uma estratégia de alavancagem de venda nesse cluster.

