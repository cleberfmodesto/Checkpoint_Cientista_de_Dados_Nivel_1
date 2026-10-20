# ☕ Health&Life Analytics: Análise do Consumo de Café e Qualidade do Sono

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-1.5%2B-150458?style=for-the-badge&logo=pandas)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.0%2B-F7931E?style=for-the-badge&logo=scikit-learn)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12%2B-3776AB?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

---

## 📌 Visão Geral do Projeto

Este projeto foi desenvolvido para a empresa fictícia **Health&Life Analytics** como parte da Formação em Data Science da **Alura**. O objetivo principal é investigar como o consumo diário de café e os níveis de estresse influenciam as horas e a qualidade do sono dos clientes, culminando no desenvolvimento de um modelo de Machine Learning capaz de prever a **Qualidade do Sono (`Sleep_Quality`)**.

---

## 📊 Estrutura do Projeto & Entregas

O projeto foi estruturado em três etapas principais:

### 1. Análise Exploratória de Dados (EDA)
- **Diagnóstico da Base:** Avaliação de 10.000 registros e 16 variáveis. Validação de ausência de nulos e duplicatas.
- **Multicolinearidade:** Identificação de correlação perfeita ($r = 1,0$) entre `Coffee_Intake` e `Caffeine_mg`, levando à remoção da variável redundante.
- **Distribuições:** Análise de histogramas com KDE e boxplots para identificação de outliers e simetria de variáveis numéricas.

### 2. Visualização e Insights de Negócio
- **Diferenças de Sono por Gênero:** Média de sono homogênea entre gêneros (~6,5 horas/noite).
- **Consumo por Faixa Etária e Estresse:** Adultos (31–45 anos) com nível de estresse `High` apresentaram as maiores taxas de consumo diário de café.
- **Matriz de Impacto:** Clientes com consumo elevado de café ($\ge 7$ xícaras/dia) dormem em média **1,8 horas a menos** por noite em comparação com consumidores leves ($\le 2$ xícaras/dia).
- **Potencializador de Estresse:** O nível de estresse `High` quadruplica a ocorrência de diagnósticos de sono na categoria `Poor`.

### 3. Engenharia de Recursos e Machine Learning
- **Feature Engineering:**
  - `Coffee_per_Sleep_Hour`: Razão entre xícaras consumidas e horas de sono.
  - `Coffee_Stress_Interaction`: Índice de interação entre consumo de café e nível de estresse.
  - `Age_Group`: Categorização por faixas etárias.
- **Modelagem Preditiva:** Comparação entre **Regressão Logística** e **Random Forest Classifier**.
- **Performance:** O modelo **Random Forest** alcançou a melhor performance (~88–90% de acurácia) com generalização consistente sem overfitting (`max_depth=10`).

---

## 💡 Principais Recomendações de Negócio

1. **Limite Recomendado de Cafeína:** Orientar clientes a manter o consumo em no máximo **4 xícaras de café ao dia**.
2. **Direcionamento por Estresse:** Para indivíduos com estresse elevado (`High`), restringir o consumo para até **2 xícaras/dia** e evitar o uso após as 14h.
3. **Score Preditivo de Sono:** Integração do modelo treinado (`best_sleep_quality_model.pkl`) no aplicativo da empresa para simulação interativa de hábitos de consumo.

---

## 📁 Estrutura do Repositório

```text
├── data/
│   └── synthetic_coffee_health_10000(in).csv   # Dataset original
├── models/
│   ├── best_sleep_quality_model.pkl            # Modelo Random Forest treinado
│   └── scaler_model.pkl                       # Normalizador StandardScaler
├── processed/
│   └── processed_coffee_sleep_health.csv       # Dataset pré-processado final
├── Projeto_Data_Science_Alura_Final.ipynb     # Jupyter Notebook unificado
├── README.md                                   # Documentação do repositório
└── requirements.txt                            # Dependências do projeto
