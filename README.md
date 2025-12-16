# Avaliação de Riscos em Operações Financeiras com Cartão de Crédito

![Status do Projeto](https://img.shields.io/badge/Status-Em_Desenvolvimento-yellow)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)

## 📌 Visão Geral do Projeto
Este projeto aplica técnicas de **Data Science** e **Machine Learning** para a detecção de fraudes em transações de cartão de crédito. O objetivo é desenvolver um modelo classificador capaz de distinguir entre transações legítimas e fraudulentas com alta precisão, minimizando prejuízos financeiros.

O projeto foi desenvolvido como requisito para a pós-graduação em Data Science, utilizando dados reais anonimizados.

## 💼 Contexto de Negócio
Fraudes em cartões de crédito representam perdas bilionárias anualmente. O desafio principal neste cenário é o **desbalanceamento dos dados**: as fraudes são eventos raros (menos de 0,2% das transações), o que torna métricas tradicionais como "Acurácia" enganosas.

**Objetivo:** Maximizar a detecção de fraudes (Recall) mantendo um número aceitável de falsos positivos (Precision).

## 📂 Fonte de Dados
Os dados utilizados foram obtidos no Kaggle: [Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud).
* **Total de Transações:** 284.807
* **Features:** V1 a V28 (resultado de transformação PCA para anonimização), 'Time' e 'Amount'.
* **Target:** 'Class' (0 = Normal, 1 = Fraude).

## 🛠️ Tecnologias e Bibliotecas Utilizadas
A análise e modelagem foram realizadas inteiramente em **Python**, utilizando as seguintes bibliotecas principais:

### Manipulação de Dados
* `pandas`: Carregamento, limpeza e manipulação de DataFrames.
* `numpy`: Operações matemáticas e vetoriais.

### Visualização de Dados (Data Visualization)
* `matplotlib.pyplot`: Criação de gráficos base.
* `seaborn`: Visualizações estatísticas avançadas (Heatmaps, Countplots, Boxplots).

### Machine Learning
* `scikit-learn`:
    * Pré-processamento (`StandardScaler`, `train_test_split`).
    * Modelos (`LogisticRegression`, `RandomForestClassifier`).
    * Métricas (`confusion_matrix`, `classification_report`, `roc_auc_score`).
* `imbalanced-learn`:
    * Técnica de balanceamento (`SMOTE`) para tratamento da classe minoritária.

## 📊 Análise Exploratória e Visualizações Chave
Nesta etapa, focamos em entender o comportamento dos dados:

1.  **Distribuição de Classes:** Gráfico de barras (`sns.countplot`) evidenciando o desequilíbrio severo entre transações normais e fraudes.
2.  **Matriz de Correlação:** Mapa de calor (`sns.heatmap`) para identificar quais variáveis (V1-V28) têm maior correlação positiva ou negativa com a variável alvo ('Class').
3.  **Análise de Valores (Amount):** Boxplots comparativos para verificar se fraudes tendem a ter tickets médios diferentes de transações normais.

## ⚙️ Metodologia
1.  **Coleta e Limpeza:** Importação do dataset e verificação de valores nulos.
2.  **EDA (Análise Exploratória):** Geração de insights visuais.
3.  **Pré-processamento:**
    * Normalização da coluna 'Amount' usando `StandardScaler`.
    * Divisão em treino e teste.
    * Aplicação de **SMOTE** nos dados de treino para balancear as classes sinteticamente.
4.  **Modelagem:** Treinamento de algoritmos de Classificação (Regressão Logística e Random Forest).
5.  **Avaliação:** Análise comparativa focada em **F1-Score** e **Matriz de Confusão**.

## 📈 Resultados Obtidos
*[Espaço reservado para inserir a imagem da Matriz de Confusão final]*

* **Acurácia Global:** [Inserir valor]% (Métrica de referência, não decisória).
* **Recall (Fraudes):** [Inserir valor]% - Capacidade do modelo de encontrar as fraudes reais.
* **F1-Score:** [Inserir valor]% - Balanço entre precisão e recall.

## 🚀 Como Executar
1. Clone este repositório.
2. Instale as dependências:
   ```bash
   pip install pandas numpy seaborn matplotlib scikit-learn imbalanced-learn