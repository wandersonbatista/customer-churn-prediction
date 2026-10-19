## Previsão de Churn de Clientes (Telco)

Este projeto foca em resolver um dos maiores desafios de empresas com modelos de assinatura: a evasão de clientes (Churn). Utilizando dados de uma empresa de telecomunicações, foi desenvolvido um modelo de Machine Learning capaz de identificar clientes com alto risco de cancelamento, permitindo ações proativas de retenção.

## Problema de Negócio:
Reter um cliente atual é significativamente mais barato do que adquirir um novo. O objetivo deste projeto não é apenas classificar quem sai e quem fica, mas sim **atribuir uma probabilidade de risco** a cada cliente. Isso permite que a equipe de negócios direcione campanhas (como descontos ou upgrades) de forma otimizada para quem realmente precisa de incentivo para ficar.

## Ferramentas Utilizadas:
* **Linguagem:** Python
* **Manipulação de Dados:** Pandas, NumPy
* **Visualização (EDA):** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn, Random Forest
* **Tratamento de Desbalanceamento:** SMOTE (Imbalanced-learn)

## Etapas de análise:

O projeto foi construído em 5 etapas principais:

1.  **Análise Exploratória (EDA):** Identificação de padrões visuais. Por exemplo, notamos que clientes com contratos mensais ("Month-to-Month") apresentam uma taxa de churn muito superior aos de contratos anuais.
2.  **Limpeza e Pré-processamento:** Tratamento de valores nulos ocultos (na coluna de cobranças totais) e conversão de variáveis categóricas usando One-Hot Encoding e Label Encoding.
3.  **Balanceamento de Classes (O Diferencial):** Como a maioria dos clientes não cancela o serviço, os dados eram desbalanceados. Foi aplicada a técnica **SMOTE** apenas no conjunto de treinamento para garantir que o modelo aprendesse a identificar a classe minoritária sem enviesamento.
4.  **Modelagem e Avaliação:** Treinamento de um classificador `RandomForest`. A métrica de sucesso priorizada não foi a acurácia, mas o **Recall (Sensibilidade)**, pois, no contexto de churn, falhar em identificar um cliente que vai sair (Falso Negativo) custa mais caro do que oferecer um desconto a alguém que não iria sair (Falso Positivo).
5.  **Exportação para Dataviz:** Geração do arquivo `resultados_churn_tableau.csv` contendo a probabilidade exata de evasão de cada cliente (`predict_proba`), preparando os dados para consumo em um dashboard executivo.

## Como Executar

1. Clone o repositório:
2. Instale as dependências:
4. Baixe o dataset WA_Fn-UseC_-Telco-Customer-Churn.csv do Kaggle e coloque na mesma pasta do projeto.

4. Execute o Jupyter Notebook churn.ipynb  para gerar as análises e exportar os resultados.

## Próximos Passos

    [ ] Construir um Dashboard Executivo Interativo no Tableau, conectando-se à base de dados enriquecida com as probabilidades de churn.

    [ ] Testar algoritmos baseados em Gradient Boosting (como o XGBoost) para comparar o desempenho com o Random Forest.