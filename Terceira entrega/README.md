# Etapa 3 – Projeto Aplicado IV: Previsão de Temperaturas e Impactos em Saúde Pública

Este repositório contém os códigos, dados e análises da Etapa 3 do Projeto Aplicado IV – que visa modelar a relação entre a temperatura média mensal e internações por doenças respiratórias no Brasil, com foco em saúde pública.

---

## 📊 Análise Exploratória dos Dados (EDA)

### 🔄 Correlação Cruzada entre Temperatura e Internações

![image](https://github.com/user-attachments/assets/9a33cd8d-f5f0-4185-a6fe-944448271377)



A Função de Correlação Cruzada (CCF) entre a temperatura média mensal e as internações por doenças respiratórias revelou correlações estatisticamente significativas em defasagens de 5 a 7 meses e novamente entre 15 e 18 meses. Esse padrão indica uma possível relação de antecipação sazonal, onde períodos de menor temperatura podem preceder aumentos nas internações com alguns meses de diferença.

---

### 📦 Boxplot: Sazonalidade das Internações

![image](https://github.com/user-attachments/assets/34724dc7-aad1-4744-bdd5-508cfa52e988)


O boxplot da sazonalidade das internações evidencia uma concentração de valores mais altos nos meses entre abril e julho, compatível com o aumento de doenças respiratórias durante os períodos mais frios.

---

### 🌡️ Boxplot: Temperatura Média Mensal

![image](https://github.com/user-attachments/assets/010f71df-a624-4734-87a9-1d8415237d35)


A distribuição mensal das temperaturas confirma a sazonalidade esperada da região Sudeste, com picos de temperatura entre dezembro e março, e os menores valores entre junho e agosto.

---

### 🕓 Séries Temporais: Temperatura vs Internações

![image](https://github.com/user-attachments/assets/ed26dd7b-4386-4535-815f-e6226990981a)


A análise conjunta das séries temporais entre 2010 e 2023 demonstra que os picos de internações geralmente coincidem com os períodos de temperatura média mais baixa, sugerindo uma relação inversa entre as variáveis.

---

### 📈 Série Temporal: Internações por Doenças Respiratórias

![image](https://github.com/user-attachments/assets/ee59df52-7561-4ce1-be2b-c5d66fdbe84e)


A série de internações revela padrões cíclicos ao longo dos anos, com destaque para o pico atípico de 2020-2021, coerente com a pandemia de COVID-19.

---

## 📁 Estrutura do Projeto

```
├── ProjetoAplicado/
│   ├── dados_A701_M_2010-01-01_2023-12-30.csv
│   └── A091020192_29_142_186.csv
├── notebooks/
│   ├── AP3.ipynb
│   └── modelos_preditivos.ipynb
├── imagens/
│   └── *.png
├── README.md
└── requirements.txt
```

---

## ⚙️ Tecnologias Utilizadas

- Python 3.10
- Pandas, NumPy
- Matplotlib, Seaborn
- Statsmodels
- Scikit-learn

---

## 📌 Objetivo da Etapa 3

Nesta etapa, buscamos:

- Realizar uma análise exploratória integrada das séries temporais;
- Identificar padrões sazonais, tendências e correlações;
- Avaliar o impacto da temperatura nas internações por doenças respiratórias;
- Preparar os dados para modelagem preditiva.



