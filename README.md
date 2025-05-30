# 🌡️ TEMPREV: Sistema de Previsão de Temperatura Mensal com Séries Temporais

**Autores:**  
Emerson Moreira Baliza - 10369752  
Luciano Guimarães Costa - 10289655  
Nicolas Pinotti - 10408010  

---

## 📌 Objetivo

A previsão de variáveis climáticas, como a temperatura, é essencial para antecipar impactos adversos na saúde pública, como o aumento de doenças respiratórias e a proliferação de doenças transmitidas por vetores.  
Este estudo desenvolve um modelo preditivo para estimar temperaturas mensais usando séries temporais, auxiliando no planejamento de ações preventivas em saúde pública.

---

## 📖 1. Introdução

Avanços tecnológicos e a crescente disponibilidade de dados ambientais transformaram a forma como compreendemos a relação entre clima e saúde.  
Estudos indicam que variações de temperatura podem estar associadas a um aumento de internações por doenças respiratórias, cardiovasculares e infecciosas (como a dengue).

Neste contexto, este projeto propõe um modelo preditivo para estimar temperaturas mensais com base em dados do INMET, incorporando também registros de internações hospitalares (DATASUS) por doenças sensíveis à temperatura.

Nosso objetivo é desenvolver uma ferramenta analítica que integre dados climáticos e de saúde, contribuindo com ações preventivas e políticas públicas mais eficazes.

---

## 📚 2. Referencial Teórico

Diversas abordagens têm sido utilizadas na previsão climática:

- **Modelos Estatísticos**  
  ARIMA e SARIMA: eficazes para capturar padrões sazonais e tendências.  
  Referência: *Hyndman & Athanasopoulos, 2018*.

- **Machine Learning**  
  Prophet: desenvolvido pelo Facebook, ideal para séries temporais irregulares.  
  Referência: *Taylor & Letham, 2018*.

- **Deep Learning**  
  Redes LSTM: úteis para fenômenos não lineares com alta variabilidade.  
  Referência: *Schmidhuber, 2015*.

No campo da saúde pública, estudos mostram que modelos preditivos baseados em dados climáticos podem antecipar surtos de doenças respiratórias e vetoriais (Patel et al., 2021).

---

## 🛠️ 3. Metodologia

### 📌 Coleta de Dados
- Dados de temperatura mensal: INMET.
- Dados de internações hospitalares por doenças respiratórias: DATASUS.

### 📌 Pré-processamento
- Tratamento de valores ausentes.
- Agregação mensal dos dados.
- Junção das bases por **ano-mês**.

### 📌 Modelagem e Treinamento
- Modelos estatísticos: ARIMA, SARIMA.
- Modelos de machine learning: Prophet.
- Futuro: LSTM (Deep Learning).
- Avaliação por métricas: **RMSE**, **MAE**.

### 📌 Validação
- Análise Exploratória (EDA).
- Correlação entre temperatura e internações.
- Teste de Estacionariedade (ADF).
- Correlação Cruzada (CCF).

---

## 📅 4. Cronograma

| Etapa     | Descrição                                 | Entrega   |
|-----------|-------------------------------------------|-----------|
| Etapa 1   | Definição do projeto e equipe             | 28/02     |
| Etapa 2   | Referencial teórico e cronograma          | 28/03     |
| Etapa 3   | Implementação parcial dos modelos         | 25/04     |
| Etapa 4   | Implementação final e entrega             | 30/05     |

---

## 📊 5. Resultados da Etapa 3

### ✅ Análise Exploratória (EDA)
- Sazonalidade clara nas séries de temperatura.
- Variações mensais nas internações.

### ✅ Correlação de Pearson
- Correlação linear de **-0.43** entre temperatura e internações.
- Relação inversa: temperaturas mais baixas → mais internações.

### ✅ Teste de Estacionariedade (ADF)
- **Temperatura**: não estacionária (p = 0.1284).
- **Internações**: estacionária (p < 0.01).

### ✅ Correlação Cruzada (CCF)
- Correlação significativa entre temperatura e internações com **defasagem de 3 a 6 meses**.
- Sugere efeito retardado do frio sobre o aumento de internações.

> 🔍 **Interpretação:**  
> Quedas de temperatura antecedem picos de internações respiratórias, com um atraso de até 6 meses — dado essencial para modelos preditivos multivariados (como SARIMAX).

---

## 🔮 6. Próximos Passos

- Modelagem com **ARIMA/SARIMA** para séries univariadas.
- Avaliação de **SARIMAX** e **Prophet com variável exógena (internações)**.
- Implementação futura com **LSTM**.

---

## 📑 7. Referências Bibliográficas

- HYNDMAN, R. J.; ATHANASOPOULOS, G. *Forecasting: Principles and Practice*. OTexts, 2018.  
- MINISTÉRIO DA SAÚDE. *Impactos das mudanças climáticas na saúde pública*, 2022.  
- PATEL, A. et al. *Machine learning approaches for forecasting dengue outbreaks based on climate data*. IJERPH, 2021.  
- SCHMIDHUBER, J. *Deep learning in neural networks: An overview*. Neural Networks, 2015.  
- TAYLOR, S. J.; LETHAM, B. *Forecasting at scale*. The American Statistician, 2018.  
- WHO. *Climate change and health*. World Health Organization, 2023.

---



## 🎥 Apresentações

- 🎬 [Apresentação do Projeto - YouTube](https://youtu.be/aiEZHtMJwdg)  
