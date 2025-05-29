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

flowchart TD
    subgraph Dados
        A[Coleta de Dados]
        B[Pré-processamento]
    end

    subgraph Analise
        C[Análise Exploratória - EDA]
    end

    subgraph Modelagem
        D[Modelagem SARIMA]
        E[Modelagem SARIMAX com variável exógena]
    end

    subgraph Validacao
        F[Validação e Métricas]
    end

    subgraph Resultados
        G[Previsão de Internações]
        H[Discussão e Melhorias Finais]
    end

    A --> B
    B --> C
    C --> D
    C --> E
    D --> F
    E --> F
    F --> G
    G --> H

    style Dados fill:#f9f,stroke:#333,stroke-width:2px
    style Analise fill:#bbf,stroke:#333,stroke-width:2px
    style Modelagem fill:#bfb,stroke:#333,stroke-width:2px
    style Validacao fill:#ffb,stroke:#333,stroke-width:2px
    style Resultados fill:#fbf,stroke:#333,stroke-width:2px
```

A solução parte da coleta de dados históricos do INMET, segue com a limpeza e transformação das séries temporais, análise exploratória, construção do modelo SARIMA, validação com métricas apropriadas e por fim a aplicação do modelo preditivo para apoiar ações de saúde pública.

---



## **EDA e Pré-processamento dos Dados**

- Dados climáticos do INMET e de internações do DATASUS.
- Pré-processamento em Python: tratamento de datas, padronização, remoção de ruídos e merge com alinhamento temporal mensal.
- Gráficos e boxplots mostraram forte **sazonalidade nas internações**, com picos entre maio e agosto.
- Teste ADF indicou:
  - Temperatura: **não estacionária** (p > 0.05)
  - Internações: **estacionária** (p < 0.05)
- Correlação de Pearson: **-0.2192** (fraca e negativa)
- CCF revelou lags significativos: **0, 1, 4–7, 11–12, 16–18, 22–23**

📊 **Acesse os gráficos no [Google Colab](https://colab.research.google.com/drive/1xSnP0P4HXhj4JVlNM2B4KQoY_PdbUTP-)**

---

## **Modelos**

- **Modelos avaliados:**
  - SARIMA (modelo base)
  - SARIMAX com temperatura como variável exógena
- **Melhor desempenho:** SARIMAX(2,1,2)x(0,1,[1],12)
- **Ferramentas utilizadas:**
  - Python (`pmdarima`, `statsmodels`)
  - Grid Search para seleção dos hiperparâmetros

---

## **Resultados**

- **RMSE no conjunto de teste (2023):** 94.69
- **Coeficiente da temperatura:** 9.2091 (p = 0.038) → **significativo**
- **Diagnóstico de resíduos:**
  - Sem autocorrelação (teste de Ljung-Box)
  - Não normalidade (Jarque-Bera)
  - Heterocedasticidade presente

---

## **Discussão e Conclusão**

O modelo SARIMAX se mostrou promissor, capturando tendências sazonais e revelando um impacto significativo da temperatura nas internações. Contudo, limitações foram observadas:

- Não normalidade e variância instável dos resíduos  
- Coeficientes não significativos  
- Sinal positivo inesperado no coeficiente da temperatura, exigindo análise mais profunda das defasagens

**Melhorias futuras:**

- Aplicar transformações (log, Box-Cox)
- Considerar modelos SARIMAX-GARCH para tratar heterocedasticidade
- Incluir novas variáveis explicativas (ex: umidade, poluentes)
- Usar validação cruzada temporal (time series cross-validation)
- Comparar com modelos alternativos (GAM, XGBoost, LSTM, etc.)

---

## **Apresentação**

📽️ *Link do vídeo será inserido aqui posteriormente*

---

## **Referências**

- BEZERRA, D. C. B.; LUSTOSA, A. L. (2024). *Os efeitos do clima e da poluição do ar sobre as doenças respiratórias: uma revisão sistemática*. Revista CEREUS.  
- HYNDMAN, R. J.; ATHANASOPOULOS, G. (2021). *Forecasting: Principles and Practice*. OTexts.  
- INMET. *Dados históricos de temperatura*. https://portal.inmet.gov.br/  
- DATASUS. *TabNet*. http://www2.datasus.gov.br/  
- SILVA, T. S. et al. (2023). *Climate seasonality and lower respiratory tract diseases*. Revista de Saúde Pública.  
- SOUZA, M. L. et al. (2010). *Statistical analysis aiming at predicting respiratory tract disease hospital admissions*. Cadernos de Saúde Pública.  
