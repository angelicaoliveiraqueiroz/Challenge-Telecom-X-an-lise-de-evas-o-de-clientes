Análise de Evasão de Clientes (Customer Churn Analysis)

Visão Geral
Este projeto foca na análise de dados de uma empresa de telecomunicações para identificar as causas da evasão de clientes (churn). Através da exploração de dados, análise estatística e visualizações, buscamos entender quais fatores contribuem para que os clientes cancelem seus serviços.

Conjunto de Dados
O conjunto de dados TelecomX_Data.json contém informações detalhadas sobre clientes de uma empresa de telecomunicações, incluindo dados demográficos, serviços contratados, informações de faturamento e o status de evasão (Churn).

Objetivo
Identificar padrões e características que distinguem clientes que evadiram daqueles que permaneceram, a fim de propor estratégias de retenção eficazes.

Etapas da Análise
1. Carregamento e Pré-processamento dos Dados
O arquivo TelecomX_Data.json foi carregado em um DataFrame pandas.
Colunas aninhadas (customer, phone, internet, account) foram expandidas para o DataFrame principal para facilitar a análise.
A coluna account_Charges.Total foi convertida para tipo numérico e valores ausentes foram preenchidos com 0.
A coluna Churn foi limpa, garantindo que contenha apenas 'Yes' ou 'No'.
2. Exploração Inicial de Dados
Foram exibidas as primeiras linhas do DataFrame para inspeção rápida.
Verificou-se os tipos de dados e informações gerais do DataFrame (df.info()).
Estatísticas descritivas foram geradas para colunas numéricas e categóricas, fornecendo um panorama inicial da distribuição dos dados.
3. Análise da Coluna de Evasão (Churn)
A distribuição da variável Churn foi analisada, revelando que 25.72% dos clientes evadiram e 74.28% não.
Estatísticas descritivas de colunas numéricas (e.g., customer_tenure, account_Charges.Monthly, account_Charges.Total) foram comparadas entre clientes com e sem churn para identificar diferenças significativas.
A distribuição de colunas categóricas importantes foi analisada em relação ao status de churn para entender associações.
4. Visualização de Fatores Chave
Gráficos de Densidade (KDE plots) foram utilizados para visualizar a distribuição de customer_tenure e account_Charges.Monthly para clientes que evadiram e não evadiram.
Gráficos de Barras foram gerados para mostrar a porcentagem de churn em relação a categorias-chave como account_Contract, internet_InternetService, internet_OnlineSecurity e account_PaymentMethod.
Principais Descobertas
Menor tempo de permanência (customer_tenure): Clientes que evadiram apresentaram um tempo de permanência médio significativamente menor (18 meses) em comparação com clientes que não evadiram (37 meses).
Maiores cobranças mensais (account_Charges.Monthly): Clientes que evadiram tendem a ter cobranças mensais médias mais altas ($74.44) do que clientes que não evadiram ($61.35).
Tipo de contrato: 88.55% dos clientes que evadiram tinham contratos mensais (Month-to-month), indicando um alto risco neste tipo de contrato.
Serviço de Internet Fibra Óptica: 69.40% dos clientes que evadiram utilizavam o serviço de internet fibra óptica, sugerindo possível insatisfação com este serviço.
Ausência de serviços adicionais de internet: A falta de serviços como Segurança Online (internet_OnlineSecurity), Backup Online, Proteção de Dispositivo e Suporte Técnico foi fortemente associada à evasão (e.g., 78.17% dos clientes que evadiram não tinham Segurança Online).
Método de pagamento: Clientes que utilizam Electronic check como método de pagamento apresentaram uma maior propensão à evasão (57.30% dos clientes que evadiram).
Faturamento sem papel (PaperlessBilling): 74.91% dos clientes que evadiram optaram pelo faturamento sem papel.
Demografia: Clientes sem parceiro ou dependentes mostraram maior propensão à evasão.
Insights e Próximos Passos
Programas de Retenção Segmentados: Focar esforços de retenção em clientes com menor tempo de permanência, contratos mensais, usuários de fibra óptica e aqueles que pagam via cheque eletrônico.
Investigar Satisfação de Serviço: Realizar análises mais aprofundadas ou pesquisas de satisfação para entender as razões da alta evasão entre usuários de fibra óptica e aqueles sem serviços de segurança online.
Modelagem Preditiva: Desenvolver modelos de Machine Learning para prever a probabilidade de churn de clientes com base nos fatores identificados, permitindo intervenções proativas.
Análise de Custo-Benefício: Avaliar o impacto financeiro da evasão e o retorno sobre o investimento de diferentes estratégias de retenção.
