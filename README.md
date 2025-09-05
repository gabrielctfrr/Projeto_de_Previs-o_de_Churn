# Projeto de Previsão de Churn (Cancelamento de Clientes)

Este projeto de Data Science tem como objetivo construir um modelo de Machine Learning para prever quais clientes de uma empresa de telecomunicações estão mais propensos a cancelar seus serviços (churn).

## 🎯 1. Objetivo de Negócio

A perda de clientes (churn) é um desafio crítico para empresas com modelos de assinatura. Identificar clientes em risco de forma proativa permite que a empresa tome ações de retenção direcionadas, como ofertas especiais ou suporte aprimorado, reduzindo a perda de receita e aumentando a lealdade do cliente.

Este modelo foi desenvolvido para prever a probabilidade de churn com base no perfil e nos serviços contratados por cada cliente.

## 📊 2. Fonte dos Dados

O conjunto de dados utilizado foi o "Telco Customer Churn", obtido na plataforma Kaggle. Ele contém 7043 registros de clientes e 21 colunas, incluindo:

* **Dados Demográficos:** Gênero, se é idoso, se possui parceiro(a) e dependentes.
* **Serviços Contratados:** Telefonia, múltiplos serviços de linha, serviço de internet (DSL, Fibra Ótica), segurança online, backup online, etc.
* **Dados da Conta:** Tempo de contrato (tenure), tipo de contrato (mensal, anual), método de pagamento e faturas.
* **Variável Alvo:** A coluna `Churn`, indicando se o cliente cancelou ('Yes') ou não ('No').

## 🛠️ 3. Metodologia

O projeto foi estruturado seguindo as seguintes etapas:

1.  **Limpeza e Pré-processamento:**
    * Tratamento da coluna `TotalCharges`, que continha valores ausentes disfarçados de espaços vazios.
    * Conversão de todas as variáveis categóricas para um formato numérico utilizando One-Hot Encoding (`pd.get_dummies`), preparando os dados para o modelo.

2.  **Análise Exploratória de Dados (EDA):**
    * Geração de visualizações para identificar os principais fatores que influenciam o churn.
    * **Principais Insights:** Clientes com **contrato mensal** e **pouco tempo de serviço (baixo tenure)** mostraram uma propensão ao cancelamento muito maior. Além disso, o serviço de **Internet de Fibra Ótica** está associado a uma taxa de churn mais elevada.

3.  **Treinamento do Modelo:**
    * Os dados foram divididos em conjuntos de treino (80%) e teste (20%).
    * Foi utilizado um modelo de **Regressão Logística**, um algoritmo de classificação robusto e interpretável, ideal para problemas de previsão binária.
    * Os dados foram escalonados com `StandardScaler` para otimizar a performance do modelo.

## 📈 4. Resultados

O modelo foi avaliado no conjunto de teste, que ele nunca havia visto antes, e alcançou os seguintes resultados:

* **Acurácia Geral:** 78%

Mais importante, ao analisar a capacidade do modelo de prever especificamente os clientes que cancelam (Classe 1), obtivemos:

* **Precisão (Precision) para Churn:** **[insira aqui o valor da sua precisão para a classe 1]%**
* **Recall (Sensibilidade) para Churn:** **[insira aqui o valor do seu recall para a classe 1]%**

O **Recall** de **[seu valor de recall]%** significa que o modelo foi capaz de identificar corretamente **[seu valor de recall]%** de todos os clientes que, de fato, cancelaram o serviço. Este é um indicador crucial, pois mede a eficácia do modelo em não deixar "passar" clientes em risco.

## ✅ 5. Conclusão

O modelo de Regressão Logística se mostrou uma ferramenta eficaz e de baixo custo computacional para a identificação de clientes com alta probabilidade de churn.

A análise sugere que as estratégias de retenção da empresa devem focar principalmente em **clientes de contrato mensal** e naqueles que estão nos **primeiros meses de serviço**, oferecendo incentivos para migração para contratos de longo prazo ou benefícios de fidelidade.

Como próximos passos, recomenda-se a experimentação com algoritmos mais complexos (como Random Forest ou XGBoost) para avaliar se é possível obter um aumento significativo na taxa de **Recall** sem comprometer a precisão.

## 💻 6. Ferramentas Utilizadas
* **Linguagem:** Python
* **Bibliotecas:** Pandas, NumPy, Matplotlib, Seaborn e Scikit-learn
* **Ambiente:** Google Colab
