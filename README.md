# Health Insurance Cross-Sell



#### Made by Tiago Araujo

# Descrição

O projeto tem como objetivo rankear os clientes com mais propensão de compra, usando dados e algoritmos de machine learning, de forma a oferecer informações para decisões de negócio.

# 1. Problema de negócio

A seguradora fictícia Cuidado Seguros gostaria de aumentar a receita anual por cliente. Para isso, a estratégia adotada será realizar Cross-Sell: para os clientes que já têm seguro de vida, será ofertado também seguro para carros. No entanto, a empresa não tem muito dinheiro para realizar uma ampla campanha de marketing e contatar todos os clientes. Por isso, há a necessidade de uma solução que diminua o custo na aquisição, maximizando ao máximo a receita. 

# 2. Suposições do negócio




# 3. Estratégia de solução

**Etapa 01. Descrição dos dados:**

Os dados são da plataforma Kaggle e podem ser classificados em demográficos do consumidor (gênero, ano, região), características do veículo (ano, estado de conservação) e de marketing (canal de contato).
Link: https://www.kaggle.com/datasets/anmolkumar/health-insurance-cross-sell-prediction

**Etapa 02. Feature Engineering:**

Objetivo: 

Processo: mudanças no nome de variáveis vehicle_damage e vehicle_age para facilitar a análise.

**Etapa 04. Exploratory Data Analysis:**

Objetivo: ganhar entendimento intuitivo dos dados

Processo: série de análises entre as variáveis ( uni, bi e multi variadas) com o objetivo de encontrar padrões interessantes. 

Top 3 insights: [mostrar insights]

Pacotes usados: Seaborn, Matplotlib e Pandas

**Etapa 05. Data Preparation:**

Objetivo: preparar os dados para o treinamento de modelos

Processos:

  a) Separação dados treino, validação e teste
  
  b) Padronização: uso de StandScaler na variável annual_premium
  
  c) Reescala: uso de MinMaxScaler nas variáveis age e vintage
  
  d) Encoding: uso de One-Ho e Target nas variáveis gender, region_code, vehicle_age e policy_sales_channel
  
Pacotes usados: Pandas e Sklearn


**Etapa 06. Feature Selection:**

Objetivo: selecionar as melhores features para treinar o modelo

Processos:

a) Treinamento de algoritmo de seleção automática de features (Boruta)

b) Seleção das feateures mais importantes

Pacotes usados: Boruta, Sklearn

**Etapa 07. Machine Learning Modelling:**

Objetivo: Treinar e avaliar a performance dos modelos nos dados de validação

Modelos treinados: K-Nearest Neighbors (KNN), Regressão Logística, Extra Trees Classifier, Random Forest

Seleção do modelo com melhor performance/menos custo computacional: [falar qual o modelo]

Ferramenta de visualização: Curva comparativa de ganho acumulado

Pacotes usados: Scikitplot e Sklearn 

**Etapa 08. Hyperparameter Fine Tunning:**

Objetivo: ajustar parâmentros do modelo para otimizar a performance

Processo: Uso do algoritmo Random Search 

Pacotes usados: Sklearn

**Etapa 09. Convert Model Performance to Business Values:**

Objetivo: Traduzir as informações em linguagem simples para ser apresentada ao time de negócio

Processo: Uso do resultado do modelo para gerar métricas como ROI e ganho acumulado


# 5. Machine Learning Modelo Performance

Performance: métricas de classificação (precisão e reccal) para 20.000 clientes ( at K = 20.000)

![image](https://user-images.githubusercontent.com/88745881/205940730-b4852186-b5e8-417e-8c18-7350c38d6478.png)



# 6. Business Results




# 7. Conclusions

# 8. Lessons Learned

# 9. Next Steps to Improve


1. Colocar o modelo em um ambiente de produção que seja escalável
2. Usar outros algoritmos que posssam melhorar a performance

