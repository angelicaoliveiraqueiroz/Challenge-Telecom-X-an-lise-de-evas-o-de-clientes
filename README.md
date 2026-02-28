Estudo sobre Cancelamento de Clientes (Customer Churn)
Enquadramento

Este projeto dedica-se à análise de informação proveniente de uma empresa de telecomunicações com o intuito de perceber os motivos que levam os clientes a cessar os seus contratos. Através da exploração de dados, aplicação de técnicas estatísticas e recurso a representações gráficas, pretende-se identificar os fatores que influenciam a decisão de cancelamento.

Base de Dados

O ficheiro TelecomX_Data.json reúne dados detalhados relativos aos clientes da empresa, incluindo características demográficas, serviços subscritos, elementos de faturação e a indicação de permanência ou saída (Churn).

Propósito

Detetar padrões e atributos que diferenciem clientes que cancelaram dos que permaneceram ativos, permitindo delinear estratégias eficazes de fidelização.

Fases do Processo Analítico
1. Importação e Tratamento Inicial

O ficheiro TelecomX_Data.json foi importado para um DataFrame em pandas.

As estruturas aninhadas (customer, phone, internet, account) foram desagregadas para simplificar a análise.

A variável account_Charges.Total foi convertida para formato numérico, preenchendo valores em falta com 0.

A coluna Churn foi uniformizada para conter exclusivamente as categorias “Yes” e “No”.

2. Análise Exploratória

Visualização das primeiras entradas do DataFrame para validação preliminar.

Verificação dos tipos de dados e resumo estrutural com df.info().

Cálculo de estatísticas descritivas para variáveis numéricas e categóricas, oferecendo uma visão global da distribuição dos dados.

3. Avaliação da Variável Churn

A análise da distribuição revelou que 25,72% dos clientes cancelaram o serviço, enquanto 74,28% se mantiveram.

Comparação de indicadores como customer_tenure, account_Charges.Monthly e account_Charges.Total entre os dois grupos, identificando diferenças relevantes.

Estudo da relação entre variáveis categóricas relevantes e o estado de cancelamento.

4. Representação Gráfica dos Fatores Principais

Utilização de gráficos de densidade (KDE) para comparar a permanência (customer_tenure) e o valor mensal (account_Charges.Monthly) entre clientes que cancelaram e os que continuaram.

Construção de gráficos de barras para analisar a taxa de churn consoante variáveis como tipo de contrato, serviço de internet, segurança online e método de pagamento.

Resultados de Destaque

Tempo de permanência: Clientes que cancelaram apresentavam, em média, 18 meses de contrato, enquanto os restantes tinham cerca de 37 meses.

Encargos mensais: O valor médio mensal era superior no grupo que abandonou (74,44$) face ao grupo que permaneceu (61,35$).

Modalidade contratual: 88,55% dos cancelamentos ocorreram em contratos mensais (Month-to-month), evidenciando maior vulnerabilidade neste formato.

Internet por fibra ótica: 69,40% dos clientes que cancelaram utilizavam este serviço, sugerindo possível insatisfação.

Serviços adicionais de internet: A inexistência de funcionalidades como Segurança Online, Backup Online, Proteção de Equipamento e Suporte Técnico revelou forte associação ao churn (por exemplo, 78,17% dos clientes que saíram não possuíam Segurança Online).

Forma de pagamento: O uso de Electronic check apresentou maior incidência de cancelamento (57,30%).

Faturação eletrónica: 74,91% dos clientes que desistiram optaram por faturação sem papel.

Perfil demográfico: Clientes sem parceiro ou dependentes demonstraram maior tendência para abandonar o serviço.

Recomendações e Próximas Etapas

Estratégias de retenção direcionadas: Concentrar esforços em clientes com menor antiguidade, contratos mensais, utilizadores de fibra ótica e aqueles que utilizam cheque eletrónico como método de pagamento.

Análise da satisfação do serviço: Realizar estudos complementares ou inquéritos para compreender a elevada taxa de saída entre utilizadores de fibra ótica e clientes sem serviços de segurança online.

Modelos preditivos: Desenvolver modelos de Machine Learning capazes de estimar a probabilidade de churn, permitindo intervenções antecipadas.

Avaliação financeira: Medir o impacto económico da perda de clientes e analisar o retorno potencial das diferentes iniciativas de retenção.
