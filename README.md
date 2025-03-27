# Previsão de Temperatura Mensal com Séries Temporais

SISTEMA DE PREVISÃO DE TEMPERATURA LOCAL TEMPREV 

EMERSON MOREIRA BALIZA - 10369752

LUCIANO GUIMARAES COSTA - 10289655

NICOLAS PINOTTI - 10408010



 ## Introdução


1.1 Introdução 

Nos últimos anos, o avanço tecnológico e a crescente disponibilidade de dados ambientais têm transformado a forma como compreendemos a relação entre as condições climáticas e a saúde pública. A previsão de variáveis climáticas, em especial a temperatura, é fundamental para antecipar e mitigar os impactos na saúde, como o aumento de doenças respiratórias durante ondas de frio ou a proliferação de doenças transmitidas por vetores em períodos de calor intenso. 

A relevância desta pesquisa está na integração de um referencial teórico sólido com práticas analíticas inovadoras que, em conjunto, possibilitam a criação de ferramentas para a prevenção de agravos à saúde. Assim, ao prever as temperaturas mensais, pretende-se validar a eficácia de técnicas de séries temporais e demonstrar sua aplicação em contextos reais, contribuindo para o desenvolvimento de políticas públicas voltadas à saúde e ao bem-estar da população. 

1.2 Motivações e Justificativa 

A previsão precisa de temperaturas é essencial para a saúde pública, permitindo antever períodos de risco elevado e implementar estratégias preventivas. Estudos demonstram que variações térmicas impactam diretamente a incidência de doenças respiratórias, cardiovasculares e infecciosas. A utilização de modelos preditivos baseados em séries temporais oferece uma abordagem robusta para monitoramento e resposta a esses desafios. 

Com a intensificação do uso de sensores climáticos e a disponibilidade de bases históricas detalhadas, torna-se viável aplicar essas técnicas para antecipar condições ambientais que afetam a saúde. Este projeto utiliza uma base de dados com registros mensais de temperatura desde 1963, permitindo a identificação de padrões sazonais e tendências que informam decisões em saúde pública. 

1.3 Objetivo 

Este estudo tem como objetivo desenvolver e validar um modelo preditivo de temperaturas mensais utilizando técnicas de séries temporais, com ênfase em sua aplicação na saúde pública. A proposta é contribuir para a compreensão dos impactos climáticos na saúde, fornecendo informações para a formulação de políticas públicas mais eficazes e para a implementação de medidas preventivas em regiões vulneráveis. 

Ademais, busca-se validar a eficácia das metodologias estatísticas aplicadas, explorando suas potencialidades na previsão de condições climáticas que afetam a saúde coletiva. 

1.4 Descrição da Base de Dados 

A base de dados utilizada neste projeto contém registros mensais de temperatura, com dois atributos principais: a data, correspondente ao primeiro dia de cada mês, e a temperatura média registrada. Os dados abrangem o período de janeiro de 1963 até o presente e estão organizados em formato tabular, facilitando a aplicação de métodos estatísticos. 

A fonte dos dados é o Instituto Nacional de Meteorologia (INMET), uma instituição oficial de monitoramento climático do Brasil. O conjunto de dados inclui aproximadamente 744 observações, cobrindo um período de mais de 60 anos de medições mensais. Cada registro é composto por dois atributos: (i) a data em formato 'AAAA-MM-DD' e (ii) a temperatura média em graus Celsius, representada como um valor numérico de ponto flutuante.

Essa base histórica é fundamental para validar os modelos preditivos, permitindo a análise de padrões climáticos e sua correlação com indicadores de saúde.

2. Referencial Teórico 

WORLD HEALTH ORGANIZATION (WHO). Climate change and health. 2023. Disponível em: https://www.who.int/news-room/fact-sheets/detail/climate-change-and-health. 

MINISTÉRIO DA SAÚDE. Impactos das mudanças climáticas na saúde pública. 2022. Disponível em: https://www.gov.br/saude/pt-br/assuntos/saude-ambiental/mudancas-climaticas-e-saude

## REFERENCIAL TEÓRICO

A previsão de variáveis climáticas, como a temperatura, é um tema bastante estudado devido à sua importância em áreas como a saúde pública. Modelos de séries temporais são ferramentas eficazes para identificar padrões e fazer previsões com base em dados do passado.

## Trabalhos Correlacionados:

Estudos recentes mostram que modelos como ARIMA (AutoRegressive Integrated Moving Average) e suas variações, como o SARIMA (Seasonal ARIMA), são amplamente usados para prever séries temporais sazonais (HYNDMAN; ATHANASOPOULOS, 2018). Outra abordagem bastante utilizada é o modelo Prophet, desenvolvido pelo Facebook, que se destaca por lidar bem com tendências e sazonalidades de longo prazo de forma simples e eficiente (TAYLOR; LETHAM, 2018).

Enquanto modelos estatísticos, como o ARIMA, são eficazes para padrões lineares, técnicas mais avançadas como as redes neurais recorrentes (RNN) e o modelo LSTM (Long Short-Term Memory) conseguem capturar relações mais complexas e não-lineares (SCHMIDHUBER, 2015).

## Alternativas de Solução:

ARIMA e SARIMA: São modelos tradicionais que funcionam bem para séries com padrões regulares, mas exigem que os dados sejam ajustados para atender a certas condições.

Prophet: Mais fácil de ajustar e capaz de capturar sazonalidades e tendências de longo prazo, com menos esforço de configuração.

LSTM: Mais avançado, consegue lidar com padrões complexos, mas exige mais poder computacional e maior tempo de treinamento.

Neste projeto, serão utilizados os modelos ARIMA e Prophet, pois oferecem um equilíbrio entre precisão, facilidade de implementação e interpretação dos resultados.

Conceitos Principais:

Séries Temporais: Sequência de dados coletados em intervalos de tempo regulares.

Tendência: Padrão de crescimento ou queda ao longo do tempo.

Sazonalidade: Repetição de padrões em períodos regulares (mensal, anual, etc.).

Modelos ARIMA e SARIMA: Utilizam relações entre os valores passados para prever valores futuros.

Prophet: Modelo flexível que combina tendência e sazonalidade de forma intuitiva.

Referências:

HYNDMAN, R. J.; ATHANASOPOULOS, G. Forecasting: Principles and Practice. OTexts, 2018.

TAYLOR, S. J.; LETHAM, B. Forecasting at scale. PeerJ Preprints, 2018.

SCHMIDHUBER, J. Deep Learning in Neural Networks: An Overview. Neural Networks, 2015.

## PIPELINE DA SOLUÇÃO

O pipeline da solução proposto está dividido em cinco etapas principais:

Coleta de Dados: Os dados são obtidos do portal do Instituto Nacional de Meteorologia (INMET) e incluem registros mensais de temperatura desde 1963.

Pré-processamento: Limpeza dos dados, padronização das datas e tratamento de valores ausentes ou inconsistentes.

Análise Exploratória (EDA): Exploração dos dados para identificar tendências, sazonalidades e padrões relevantes.

Modelagem Preditiva:

Ajuste dos modelos ARIMA e Prophet para fazer previsões de temperatura.

Avaliação do desempenho dos modelos com métricas como RMSE (Erro Quadrático Médio) e MAE (Erro Médio Absoluto).

Validação e Interpretação dos Resultados: Comparação da precisão dos modelos e análise dos impactos das previsões na saúde pública, com recomendações para ações futuras.

Fluxo do Pipeline:

Coleta de Dados → Pré-processamento → Análise Exploratória → Modelagem → Validação e Interpretação

 CRONOGRAMA

Atividade

Descrição

Prazo

Definição do Projeto e Equipe

Definir escopo do projeto e equipe de trabalho

28/02/2025

Levantamento de Dados

Coleta e organização dos dados históricos de temperatura

10/03/2025

Análise Exploratória (EDA)

Identificação de padrões, sazonalidade e tendências

20/03/2025

Referencial Teórico e Cronograma

Entrega do referencial teórico e planejamento do projeto

28/03/2025

Desenvolvimento do Pipeline

Implementação inicial do pipeline de dados e pré-processamento

10/04/2025

Implementação Parcial

Desenvolvimento inicial dos modelos preditivos

25/04/2025

Ajustes e Validação

Comparação de modelos e avaliação de métricas de desempenho

10/05/2025

Documentação Final

Redação do relatório técnico e conclusões

25/05/2025

Implementação e Entrega Final

Finalização do projeto e entrega do relatório

30/05/2025



📄 Licença
Este projeto é disponibilizado sob a licença MIT. Sinta-se à vontade para contribuir e explorar!


