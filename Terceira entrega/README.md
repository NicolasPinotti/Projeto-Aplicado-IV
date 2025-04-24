# 📊 Projeto Aplicado IV - Etapa 3  
## Previsão de Temperatura Mensal e Impacto nas Internações por Doenças Respiratórias

### 🔎 Objetivo
Analisar a relação entre a temperatura média mensal e o número de internações por doenças respiratórias no Brasil, com foco em prever padrões de internação a partir de séries temporais climáticas e de saúde pública.

---

## 1. 🔍 Análise Exploratória (EDA)

Foram analisadas duas séries temporais:
- **Temperatura Média Mensal (°C)**: Dados do INMET (Instituto Nacional de Meteorologia).
- **Internações por Doenças Respiratórias**: Dados extraídos do DATASUS.

### 1.1 Evolução Temporal

- A série de **temperatura média** apresenta clara **sazonalidade anual**, com oscilações previsíveis entre meses mais frios e mais quentes.
- A série de **internações** também revela um padrão sazonal, com **aumento significativo durante os meses mais frios**.

![image](https://github.com/user-attachments/assets/3e71f6a4-e82c-4109-9a6c-c9ebd963c9b6)


![image](https://github.com/user-attachments/assets/c8bbce5f-8ec7-4395-b297-c41cb60fec98)


---

## 2. 📈 Correlação entre Temperatura e Internações

### 2.1 Correlação de Pearson

| Correlação | Valor |
|-----------|-------|
| Temperatura Média × Internações | -0.572 |

![image](https://github.com/user-attachments/assets/e5264226-8ac0-4605-bd60-f8c74d8de72a)


📌 **Interpretação:**  
A correlação negativa sugere que, em geral, **quanto mais baixa a temperatura, maior o número de internações**. Isso é consistente com o impacto do frio sobre doenças respiratórias.

---

## 3. ⚙️ Transformações e Sazonalidade

### 3.1 Sazonalidade

Foram identificadas **componentes sazonais fortes** em ambas as séries com decomposição aditiva.

![image](https://github.com/user-attachments/assets/e9e8972c-bd03-4389-9a56-46db7f306600)


![image](https://github.com/user-attachments/assets/cc8d41d2-d3a2-4930-8dc0-fb87a7f52103)


### 3.2 Transformações

- Aplicada **diferença de primeira ordem** para remover tendência.
- Aplicada **média móvel de 12 meses** para suavizar a sazonalidade.

---

## 4. 🧪 Teste de Estacionariedade (ADF)

Aplicado o Teste Dickey-Fuller Aumentado (ADF):

| Série               | Estatística ADF | Valor-p | Conclusão             |
|---------------------|------------------|---------|------------------------|
| Temperatura Média   | -2.4489          | 0.1284  | Não estacionária       |
| Internações         | -5.7593          | 0.0000  | Estacionária           |

📌 **Interpretação:**  
A série de **Internações** já é estacionária, enquanto a **Temperatura Média** necessita de diferenciação antes da modelagem.

---

## 5. 🔄 Correlação Cruzada (CCF)

Analisada a correlação entre a Temperatura Média com lags (defasagens) e as Internações:

![image](https://github.com/user-attachments/assets/345aaba1-ea3d-4df2-955b-24ebe8b39693)


### Resultados

- **Lag 0**: Correlação = -0.5723
- **Maior correlação (absoluta)**:  
  Lag 1 (Temperatura com 1 mês de defasagem) → Correlação = -0.6037

📌 **Interpretação:**  
A temperatura com **1 mês de antecedência** tem correlação mais forte com o número de internações. Isso sugere que **quedas de temperatura afetam as internações no mês seguinte**, o que pode ser relevante para sistemas de saúde se anteciparem a picos de internações.

---

## ✅ Conclusões Parciais da Etapa 3

- Existe **relação estatisticamente significativa** entre temperatura e internações por doenças respiratórias.
- A série de **internações é estacionária**, e a de **temperatura requer transformação**.
- A **análise de CCF** indicou que os efeitos da temperatura nas internações podem ser percebidos com **defasagem de um mês**, o que será útil na modelagem preditiva.

---

## 🧠 Próximos Passos

- **Modelagem com séries temporais**, utilizando ARIMA, SARIMA ou modelos híbridos (ex: Prophet + Regressão).
- Avaliação de desempenho com métricas como RMSE, MAE, AIC/BIC.
- Validação cruzada temporal e construção de **modelo preditivo final**.

---

