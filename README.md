# Health Insurance Cross-Sell



#### Made by Tiago Araujo

# Descrição

O projeto tem como objetivo rankear os clientes com mais propensão de compra, usando dados e algoritmos de Machine Learning, de forma a oferecer informações para decisões de negócio.

# 1. Problema de negócio

A seguradora fictícia Cuidado Seguros gostaria de aumentar a receita anual por cliente. Para isso, a estratégia adotada será realizar Cross-Sell: para os clientes que já têm seguro de vida, será ofertado também seguro para carros. No entanto, a empresa não tem muito dinheiro para realizar uma ampla campanha de marketing e contatar todos os clientes. Por isso, há a necessidade de uma solução que diminua o custo na aquisição, maximizando ao máximo a receita. 

# 2. Estratégia de solução

**Etapa 01. Descrição dos dados:**

Os dados são da plataforma Kaggle e podem ser classificados em demográficos do consumidor (gênero, ano, região), características do veículo (ano, estado de conservação) e de marketing (canal de contato).
Link: https://www.kaggle.com/datasets/anmolkumar/health-insurance-cross-sell-prediction

**Etapa 02. Feature Engineering:**

Objetivo: para facilitar a análise e descobrir novos insights.

Processo: mudanças no nome de variáveis vehicle_damage e vehicle_age. 

**Etapa 04. EDA:**

Objetivo: ganhar entendimento intuitivo dos dados

Processo: série de análises entre as variáveis ( uni, bi e multi variadas) com o objetivo de encontrar padrões interessantes. 

Top 3 insights: [mostrar insights]

Pacotes usados: Seaborn, Matplotlib e Pandas

**Etapa 05. Preparação dos dados:**

Objetivo: preparar os dados para o treinamento de modelos

Processos:

  a) Separação dados treino, validação e teste
  
  b) Padronização: uso de StandScaler na variável annual_premium
  
  c) Reescala: uso de MinMaxScaler nas variáveis age e vintage
  
  d) Encoding: uso de One-Ho e Target nas variáveis gender, region_code, vehicle_age e policy_sales_channel
  
Pacotes usados: Pandas e Sklearn


**Etapa 06. Seleção de Features:**

Objetivo: selecionar as melhores features para treinar o modelo

Processos:

a) Treinamento de algoritmo de seleção automática de features (Boruta)

b) Seleção das feateures mais importantes

Pacotes usados: Boruta, Sklearn

**Etapa 07. Treinamento de modelos Machine Learning:**

Objetivo: Treinar e avaliar a performance dos modelos nos dados de validação

Modelos treinados: K-Nearest Neighbors (KNN), Regressão Logística, Extra Trees Classifier, Random Forest

Seleção do modelo com melhor performance/menos custo computacional: [falar qual o modelo]

Ferramenta de visualização: Curva comparativa de ganho acumulado

Pacotes usados: Scikitplot e Sklearn 

**Etapa 08. Fine Tunning:**

Objetivo: ajustar parâmentros do modelo para otimizar a performance

Processo: Uso do algoritmo Random Search 

Pacotes usados: Sklearn

**Etapa 09. Tradução para métricas de negócio:**

Objetivo: Traduzir as informações em linguagem simples para ser apresentada ao time de negócio

Processo: Uso do resultado do modelo para gerar métricas como ROI e ganho acumulado


# 3. Avaliação dos modelos

A etapa de machine learning onde a modelagem de ML é realizada. Três modelos foram treinados usando validação cruzada:

* K-nearest neighbors
* Logistic regression
* Xgboost classifier

![image](https://user-images.githubusercontent.com/88745881/206483721-c572893d-929b-43a8-9049-5dbd947e5dc5.png)

* K é igual a 20.000 ou 40.000, dado nosso problema de negócios.

* O modelo escolhido neste projeto foi o XGBoost : pois o algoritmo mais rápido para treinar e ajustar.

* Precision at K : Mostra a fração de previsões corretas feitas até K de todas as previsões.

* Recall at K : Mostra a fração de previsões corretas feitas até K de todos os exemplos verdadeiros.

* Duas curvas podem ser plotadas e oservadas:

 * * Cumulative Gains Curve: indica a porcentagem de clientes, ordenada por pontuação de probabilidade, contendo a porcentagem de todos os clientes interessados no novo seguro de veículo.
 * * Lift Curve: que indica quantas vezes o modelo ML é melhor que o modelo baseline.

![image](https://user-images.githubusercontent.com/88745881/206483935-24e37a52-b7df-4228-88a3-5d698f74e433.png)

# 4. Resultado de Negócio

Dentre os 76.622 cliente, um total de 9.342 estão interessados no seguro de veículos. O ticket médio para um seguro de saúde anual é de $ 31669. As perguntas abaixo foram respondidas seguindo a premissa de que os clientes interessados no seguro veicular irão assinar o contrato, e que o valor médio do seguro do veículos será o mesmo do seguro saúde.

**1) Qual a porcentagem de clientes interessados em seguro veicular, o call center conseguirá contatar fazendo 20 mil ligações?**

R: 20.000 chamadas representam 26,24% do nosso banco de dados. Portanto, se a equipe de vendas fizesse todas essas ligações, a seguradora conseguiria entrar em contato com 71,29% dos clientes interessados no seguro de veículos novos (o valor de 0,7129 é o nosso recall em 20.000).

**2) Se a capacidade do call center aumentar para 40 mil ligações, qual a porcentagem de clientes interessados em adquirir um seguro veicular o call center conseguirá contatar?**

R: 40.000 chamadas representam 52,48% do nosso banco de dados. Nesse caso, se a equipe de vendas fizesse todas essas ligações, a seguradora conseguiria entrar em contato com 99,48% dos clientes interessados no seguro de veículos novos. O valor de 0,9948 é o nosso recall em 40.000.

**3) Qual o retorno sobre o investimento(ROI)**

R: o ROI segue a curva abaixo, de acordo com o custo e a receita que o negócio pode assumir.

![image](https://user-images.githubusercontent.com/88745881/206486621-2da95845-c1d0-4ee6-8e52-5dfb58d087ae.png)


# 5. Conclusão

* Com base nos resultados comerciais, a seguradora passa a ter uma vantagem competitiva sobre seus concorrentes, reduzindo o custo de aquisição de clientes e aumentando sua receita.
* A equipe de vendas pode focar sua atenção nos primeiros 20.000 ou 40.000 clientes da lista e, no futuro, focar nos primeiros K clientes da nova lista.
* Insights foram revelados e com os resultados obtidos é possível simular perfis de clientes, funcionalidade de grande valia para a empresa.


# 6. Próximos passos


1. Colocar o modelo em um ambiente de produção que seja escalável.
2. Usar outros algoritmos que posssam melhorar a performance.

