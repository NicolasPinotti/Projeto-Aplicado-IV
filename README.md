# 📌 Previsão de Temperatura Mensal com Séries Temporais

## SISTEMA DE PREVISÃO DE TEMPERATURA LOCAL TEMPREV

**EMERSON MOREIRA BALIZA** - 10369752  
**LUCIANO GUIMARAES COSTA** - 10289655  
**NICOLAS PINOTTI** - 10408010

---

# 📌 Previsão de Temperatura para Saúde Pública  

A previsão de variáveis climáticas, como a temperatura, é essencial para antecipar impactos adversos na saúde pública, como o aumento de doenças respiratórias e a proliferação de doenças transmitidas por vetores. Este estudo desenvolve um modelo preditivo para estimar temperaturas mensais usando séries temporais, auxiliando no planejamento de ações preventivas.  

---

## 📖 1. Introdução  

Avanços tecnológicos e a crescente disponibilidade de dados ambientais transformaram a forma como compreendemos a relação entre as condições climáticas e a saúde pública. Estudos mostram que variações de temperatura podem estar associadas a um aumento de internações por doenças respiratórias e cardiovasculares, além de influenciar a incidência de doenças infecciosas como a dengue (**WHO, 2023; MINISTÉRIO DA SAÚDE, 2022**).  

Neste contexto, este estudo propõe o desenvolvimento de um modelo preditivo para estimar temperaturas mensais utilizando técnicas de séries temporais. Além dos dados climáticos do INMET, será incorporada uma base de internações hospitalares relacionadas a doenças sensíveis à variação da temperatura.  

O objetivo é integrar modelos matemáticos e estatísticos que possibilitem a antecipação de cenários climáticos, auxiliando na implementação de estratégias de saúde pública mais eficazes.  

---

## 📚 2. Referencial Teórico  

A previsão de variáveis climáticas é amplamente estudada, com diferentes abordagens metodológicas:  

- **Modelos estatísticos:** ARIMA e SARIMA são eficazes para capturar padrões sazonais e tendências em séries temporais (**HYNDMAN; ATHANASOPOULOS, 2018**).  
- **Modelos baseados em machine learning:** Prophet, do Facebook, apresenta bons resultados na previsão de séries temporais irregulares (**TAYLOR; LETHAM, 2018**).  
- **Modelos de deep learning:** Redes neurais recorrentes (RNN) e modelos LSTM são utilizados para fenômenos não lineares e alta variabilidade (**SCHMIDHUBER, 2015**).  

No contexto da saúde pública, estudos indicam que modelos preditivos podem prever a incidência de doenças relacionadas ao clima, auxiliando políticas preventivas (**PATEL et al., 2021**).  

---

## 🛠 3. Metodologia  

### 📌 Coleta de Dados  
- Base de temperatura do INMET.  
- Base de internações hospitalares relacionadas a doenças respiratórias.  

### 📌 Pré-processamento dos Dados  
- Tratamento de valores ausentes.  
- Normalização dos dados e junção das bases.  

### 📌 Modelagem e Treinamento  
- Modelos estatísticos: **ARIMA, SARIMA**.  
- Modelos de machine learning: **Prophet, LSTM**.  
- Avaliação do desempenho (**RMSE, MAE**).  

### 📌 Validação e Análise dos Resultados  
- Comparação dos modelos preditivos.  
- Análise da correlação entre variações climáticas e indicadores de saúde.  

---

## 📅 4. Cronograma  

| Etapa | Descrição | Data de Entrega |
|-------|-----------|----------------|
| **Etapa 1** | Definição do projeto e equipe | 🗓 28/02 |
| **Etapa 2** | Referencial teórico e cronograma | 🗓 28/03 |
| **Etapa 3** | Implementação parcial dos modelos | 🗓 25/04 |
| **Etapa 4** | Implementação final e entrega | 🗓 30/05 |

---

## 📑 5. Referências Bibliográficas  

- **HYNDMAN, R. J.; ATHANASOPOULOS, G.** *Forecasting: Principles and Practice.* OTexts, 2018.  
- **MINISTÉRIO DA SAÚDE.** *Impactos das mudanças climáticas na saúde pública.* 2022.  
- **PATEL, A. et al.** *Machine learning approaches for forecasting dengue outbreaks based on climate data.* International Journal of Environmental Research and Public Health, 2021.  
- **SCHMIDHUBER, J.** *Deep learning in neural networks: An overview.* Neural Networks, 2015.  
- **TAYLOR, S. J.; LETHAM, B.** *Forecasting at scale.* The American Statistician, 2018.  
- **WHO – World Health Organization.** *Climate change and health.* 2023.  

---





