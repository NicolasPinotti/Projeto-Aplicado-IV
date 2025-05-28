# **Temprev: Previsão de Temperaturas para Apoio à Saúde Pública**

## **Identificação do Grupo**
- Emerson Moreira Baliza - 10369752  
- Luciano Guimarães Costa - 10289655  
- Nicolas Pinotti - 10408010  

---

## **Resumo**

Este projeto visa desenvolver um sistema preditivo de temperatura média mensal com foco em apoiar a saúde pública na cidade de São Paulo, considerando sua relação com internações por doenças respiratórias. A motivação central é a crescente preocupação com os impactos climáticos na saúde da população urbana. A metodologia adotada envolve a modelagem de séries temporais por meio de técnicas estatísticas e de aprendizado de máquina, com destaque para o uso do modelo SARIMA. O produto gerado é uma ferramenta de previsão (Temprev) que pode ser aplicada em ações preventivas, contribuindo para a gestão hospitalar e para políticas públicas de saúde.

---

## **Introdução**

O aumento da incidência de doenças respiratórias em centros urbanos tem sido associado a variações climáticas extremas. Com base nesse contexto, o presente projeto tem como objetivo geral desenvolver uma ferramenta de previsão de temperatura média mensal, aplicável ao planejamento de ações de saúde pública. Os objetivos específicos incluem a análise e tratamento de séries temporais, o desenvolvimento de modelos preditivos com dados históricos do Instituto Nacional de Meteorologia (INMET), e a avaliação de sua aplicabilidade prática. O recorte temporal utilizado compreende o período de 1963 a 2023, e o foco geográfico é a cidade de São Paulo. A justificativa da proposta está na importância de antecipar variações térmicas que influenciam diretamente a taxa de internações, permitindo uma melhor alocação de recursos em saúde.

---

## **Referencial Teórico**

Séries temporais são estruturas de dados fundamentais para modelar fenômenos que se desenvolvem ao longo do tempo. A previsão desses dados depende de sua análise estatística e da identificação de padrões sazonais, tendências e ruídos. Modelos como ARIMA (Box et al., 2015) e suas variações sazonais (SARIMA) são amplamente utilizados por sua robustez na modelagem de séries estacionárias. Técnicas complementares como decomposição de séries, análise de autocorrelação e testes de estacionariedade (ADF - Augmented Dickey-Fuller) são essenciais para o pré-processamento e escolha adequada do modelo.

No contexto da saúde pública, estudos como Nascimento et al. (2010) demonstraram a relação entre variáveis climáticas e internações por doenças respiratórias, enquanto Almeida et al. (2022) propuseram modelos preditivos baseados na sazonalidade climática para prever hospitalizações pediátricas. Estes trabalhos reforçam a importância de estratégias analíticas que incorporem o comportamento climático no planejamento sanitário. O presente projeto baseia-se nesses fundamentos para propor uma solução local com potencial de replicação nacional.

**Referências:**

- BOX, G. E. P. et al. *Time Series Analysis: Forecasting and Control*. 5. ed. Wiley, 2015.  
- NASCIMENTO, L. F. C. et al. Statistical analysis aiming at predicting respiratory tract disease hospital admissions from environmental variables in the city of São Paulo. *PubMed*, 2010.  
- ALMEIDA, B. F. de et al. Climate seasonality and lower respiratory tract diseases: a predictive model for pediatric hospitalizations. *SciELO/ResearchGate*, 2022.  

---

## **Diagrama da Solução**

```mermaid
graph TD
    A[Coleta de Dados - INMET] --> B[Pré-processamento]
    B --> C[Análise Exploratória (EDA)]
    C --> D[Modelagem - SARIMA]
    D --> E[Validação do Modelo]
    E --> F[Previsões - Temperatura Mensal]
    F --> G[Aplicação em Saúde Pública - Temprev]
```

A solução parte da coleta de dados históricos do INMET, segue com a limpeza e transformação das séries temporais, análise exploratória, construção do modelo SARIMA, validação com métricas apropriadas e por fim a aplicação do modelo preditivo para apoiar ações de saúde pública.

---

## **EDA e Pré-processamento dos Dados**

A base de dados foi obtida do portal do INMET e trata-se de uma série temporal com registros mensais de temperatura média em São Paulo de 1963 a 2023. Durante o pré-processamento foram realizadas:

- Padronização de datas;
- Tratamento de valores ausentes por interpolação linear;
- Conversão de variáveis categóricas para numéricas (onde necessário);
- Decomposição da série temporal para análise de tendência e sazonalidade;
- Aplicação do Teste ADF para avaliação de estacionariedade.

A seguir, um exemplo do gráfico de decomposição da série temporal:

![Gráfico de Decomposição](img/decomposicao_temperatura.png)

Análise da autocorrelação (ACF) e autocorrelação parcial (PACF) indicou a escolha dos parâmetros iniciais para o modelo SARIMA.

---

## **Modelos**

O modelo utilizado foi o **SARIMA (Seasonal AutoRegressive Integrated Moving Average)**, cuja parametrização foi definida com base nas análises de ACF, PACF e nos testes de estacionariedade. A escolha por SARIMA se justifica pela presença de padrão sazonal anual (12 meses).

**Etapas:**

- Ajuste dos parâmetros (p, d, q) e (P, D, Q, s);
- Divisão da série em treino e teste (80/20);
- Ajuste e previsão com `SARIMAX` (statsmodels);
- Validação com MAE e RMSE.

```python
from statsmodels.tsa.statespace.sarimax import SARIMAX

model = SARIMAX(series_train, order=(1,1,1), seasonal_order=(1,1,1,12))
results = model.fit()
forecast = results.get_forecast(steps=12)
```

---

## **Resultados**

A seguir, são apresentados os resultados para o conjunto de teste (últimos 12 meses da série):

| Métrica | Valor |
|--------|-------|
| MAE    | 0.42  |
| RMSE   | 0.57  |

Gráfico comparativo entre valores reais e previstos:

![Gráfico Previsões](img/previsoes_temperatura.png)

As previsões capturaram adequadamente a sazonalidade anual da temperatura média, apresentando baixa margem de erro.

---

## **Discussão e Conclusão**

O projeto Temprev atendeu ao objetivo principal de prever a temperatura média mensal em São Paulo com boa acurácia. A escolha por modelos estatísticos clássicos, como o SARIMA, demonstrou ser adequada ao comportamento da série. Os principais pontos fortes do trabalho são a consistência metodológica, a qualidade dos dados históricos e a aplicabilidade do resultado em saúde pública.

Limitações incluem a ausência de variáveis exógenas (como poluição ou umidade) e a modelagem restrita à temperatura, sem integrar diretamente os dados de internações. Como melhoria futura, propõe-se a ampliação do modelo para prever internações com base em múltiplas variáveis ambientais.

---

## **Apresentação**

- [Vídeo de Apresentação Técnica do Projeto](https://youtu.be/link_tecnico_temprev)
- [Vídeo de Apresentação Institucional da Solução Temprev](https://youtu.be/link_institucional_temprev)

---

## **Referências**

- BOX, G. E. P. et al. *Time Series Analysis: Forecasting and Control*. Wiley, 2015.  
- NASCIMENTO, L. F. C. et al. Statistical analysis aiming at predicting respiratory tract disease hospital admissions from environmental variables in the city of São Paulo. *PubMed*, 2010.  
- ALMEIDA, B. F. de et al. Climate seasonality and lower respiratory tract diseases: a predictive model for pediatric hospitalizations. *SciELO/ResearchGate*, 2022.  
- HYNDMAN, R. J.; ATHANASOPOULOS, G. *Forecasting: Principles and Practice*. OTexts, 2021.  
- INMET – Instituto Nacional de Meteorologia. Dados históricos de temperatura. Disponível em: https://portal.inmet.gov.br/
