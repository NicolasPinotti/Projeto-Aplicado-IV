# 📌 Previsão de Temperatura Mensal com Séries Temporais

## SISTEMA DE PREVISÃO DE TEMPERATURA LOCAL TEMPREV

**EMERSON MOREIRA BALIZA** - 10369752  
**LUCIANO GUIMARAES COSTA** - 10289655  
**NICOLAS PINOTTI** - 10408010

# 📖 Referencial Teórico  

A previsão de variáveis climáticas, como a temperatura, tem sido amplamente estudada devido à sua relevância para áreas como a saúde pública e a gestão de riscos ambientais. Modelos de séries temporais são ferramentas essenciais para identificar padrões históricos e realizar previsões confiáveis.  

## 🔍 Trabalhos Correlacionados  

Estudos demonstram que modelos estatísticos como **ARIMA (AutoRegressive Integrated Moving Average)** e **SARIMA (Seasonal ARIMA)** são eficazes na previsão de séries temporais com padrões sazonais bem definidos (**HYNDMAN; ATHANASOPOULOS, 2018**). No entanto, tais modelos podem apresentar limitações ao lidar com séries que possuem múltiplas sazonalidades ou tendências complexas.  

Outra abordagem amplamente utilizada é o modelo **Prophet**, desenvolvido pelo Facebook, que se destaca por sua facilidade de ajuste e robustez ao lidar com tendências e sazonalidades de longo prazo (**TAYLOR; LETHAM, 2018**). O Prophet permite a inclusão de variáveis externas e pode ser mais flexível em determinados cenários.  

Além dos modelos estatísticos, técnicas baseadas em aprendizado profundo, como **Redes Neurais Recorrentes (RNN)** e **Long Short-Term Memory (LSTM)**, apresentam bons resultados para séries temporais não lineares e de alta complexidade. Estudos sugerem que esses modelos podem capturar relações temporais complexas com maior precisão (**SCHMIDHUBER, 2015**), embora demandem mais recursos computacionais.  

## 🛠️ Alternativas de Solução  

| Modelo | Vantagens | Desvantagens |
|--------|----------|-------------|
| **ARIMA/SARIMA** | Eficiente para padrões sazonais e dados estacionários | Exige pré-processamento rigoroso e pode não lidar bem com mudanças abruptas |
| **Prophet** | Fácil ajuste e bom desempenho para sazonalidade e tendência | Menos eficiente para séries altamente voláteis |
| **LSTM** | Capaz de modelar padrões não lineares e múltiplas sazonalidades | Alto custo computacional e necessidade de grande volume de dados |

Neste projeto, os modelos **ARIMA e Prophet** foram selecionados por oferecerem um equilíbrio entre interpretabilidade, facilidade de implementação e precisão nas previsões.  

## 🔑 Conceitos Principais  

- **Séries Temporais:** Conjunto de observações organizadas cronologicamente.  
- **Tendência:** Direção geral dos dados ao longo do tempo (crescente, decrescente, estável).  
- **Sazonalidade:** Padrões recorrentes em períodos fixos (mensal, anual etc.).  
- **Modelos ARIMA e SARIMA:** Baseados em relações estatísticas entre valores passados para prever valores futuros.  
- **Prophet:** Modelo baseado em decomposição de tendência e sazonalidade, permitindo ajustes flexíveis.  

---

# 🔄 Pipeline da Solução  

O pipeline proposto para a previsão de temperaturas segue cinco etapas principais:  

1️⃣ **Coleta de Dados:** Dados mensais de temperatura obtidos do portal do **Instituto Nacional de Meteorologia (INMET)** desde 1963.  
2️⃣ **Pré-processamento:** Tratamento de valores ausentes, padronização das datas e normalização dos dados.  
3️⃣ **Análise Exploratória (EDA):** Identificação de tendências e padrões sazonais para fundamentar a modelagem.  
4️⃣ **Modelagem Preditiva:** Ajuste dos modelos **ARIMA e Prophet**, seguido de avaliação do desempenho com métricas como **RMSE (Root Mean Squared Error)** e **MAE (Mean Absolute Error)**.  
5️⃣ **Validação e Interpretação dos Resultados:** Comparação dos modelos e análise da aplicabilidade das previsões no contexto da saúde pública.  

Fluxo do pipeline:  
📥 **Coleta de Dados** → 🧹 **Pré-processamento** → 📊 **Análise Exploratória** → 📈 **Modelagem** → ✅ **Validação e Interpretação**  

---

# 📅 Cronograma do Projeto  

| 📌 **Atividade** | 📋 **Descrição** | ⏳ **Prazo** |
|-----------------|----------------|-------------|
| **Definição do Projeto e Equipe** | Escopo e organização da equipe | **28/02/2025** |
| **Levantamento de Dados** | Coleta e organização dos dados históricos | **10/03/2025** |
| **Análise Exploratória (EDA)** | Identificação de padrões e tendências | **20/03/2025** |
| **Referencial Teórico e Cronograma** | Estruturação e entrega da segunda etapa | **28/03/2025** |
| **Desenvolvimento do Pipeline** | Implementação inicial do pipeline | **10/04/2025** |
| **Implementação Parcial** | Desenvolvimento dos modelos preditivos | **25/04/2025** |
| **Ajustes e Validação** | Comparação de modelos e avaliação de métricas | **10/05/2025** |
| **Documentação Final** | Redação do relatório técnico | **25/05/2025** |
| **Implementação e Entrega Final** | Finalização e entrega do projeto | **30/05/2025** |

---

📄 **Licença**  
Este projeto é disponibilizado sob a licença MIT. Sinta-se à vontade para contribuir e explorar!

