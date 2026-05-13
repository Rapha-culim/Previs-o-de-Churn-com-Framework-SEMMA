# Previsão de Churn com Framework SEMMA

Este repositório contém um projeto de Machine Learning desenvolvido para prever o "Churn" (evasão/cancelamento) de clientes, utilizando o framework analítico **SEMMA** (Sample, Explore, Modify, Model, Assess).

## 🚀 Objetivo
O objetivo principal é identificar usuários com alta probabilidade de cancelamento, permitindo que a empresa tome ações preventivas de retenção de forma eficiente e baseada em dados.

## 📊 Framework SEMMA

### 1. S - Sample (Amostragem)
* **Base de Dados:** Utilizada a Analytical Base Table (ABT) Churn Journey.
* **Estabilidade Temporal:** Uma safra "Out-of-Time" (OOT) do último mês foi isolada para validação final.
* **Split:** Divisão de 80% para treino e 20% para teste, com estratificação para manter a proporção da variável alvo.

### 2. E - Explore (Exploração)
* **Análise de Qualidade:** Verificação de valores nulos e integridade dos dados.
* **Feature Importance Inicial:** Uso de uma Árvore de Decisão para identificar os principais drivers de Churn.
* **Insight:** A variável `qtdeDiasD14` (atividade nos últimos 14 dias) mostrou-se o principal preditor.

### 3. M - Modify (Modificação)
* **Pipeline de Dados:** Automatização do tratamento de dados.
* **Transformações:** Imputação de valores nulos pela mediana, escalonamento de variáveis numéricas e One-Hot Encoding para variáveis categóricas.

### 4. M - Model (Modelagem)
* **Algoritmo:** Random Forest Classifier.
* **Otimização:** Uso de `GridSearchCV` com validação cruzada (CV) para ajuste de hiperparâmetros (profundidade, número de estimadores).

### 5. A - Assess (Avaliação)
* **Performance Técnica:** O modelo apresentou alta estabilidade com **ROC AUC de ~0.84** em todas as bases (Treino, Teste e OOT).
* **Impacto de Negócio:**
    * Abordando os **top 10%** de maior risco, capturamos **18.48%** dos churners.
    * Abordando os **top 30%**, capturamos **48.87%** dos churners.

## 🛠️ Tecnologias Utilizadas
* Python
* Pandas / Numpy
* Scikit-Learn (Pipelines, GridSearchCV)
* Matplotlib / Seaborn

## 📂 Como Usar
1.  Clone o repositório.
2.  Instale as dependências: `pip install -r requirements.txt`.
3.  Execute o notebook em `notebooks/previsao_churn.ipynb`.

---
*Projeto desenvolvido como exercício prático de Data Science do Prof. Dr Julio Cesar Lemos.*
