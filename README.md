# 📈 Previsão de Preços de Ações — AAPL (LSTM)

**Resumo do projeto**  
Este projeto aplica uma **rede neural LSTM** para prever o preço de fechamento diário da ação **Apple (AAPL)**. O objetivo é demonstrar como modelos de séries temporais (LSTM) conseguem aprender padrões históricos e prever movimentos de curto prazo no mercado.

---

## 🔍 Descrição
- **Ticker:** AAPL (Apple Inc.)  
- **Período:** 2015-01-01 até 2025-12-31 (dados obtidos via `yfinance`)  
- **Entrada do modelo:** janelas de 60 dias de preços de fechamento  
- **Modelo:** Rede LSTM com duas camadas LSTM e uma camada densa de saída  
- **Objetivo:** prever o preço de fechamento do próximo dia

---

## 🗂️ Amostra do dataset

| Date       | Close       |
|------------|-------------|
| 2015-01-02 | 24.261047   |
| 2015-01-05 | 23.577576   |
| 2015-01-06 | 23.579790   |
| 2015-01-07 | 23.910435   |
| 2015-01-08 | 24.829130   |

> Dados baixados com `yfinance` (`yf.download(ticker, start="2015-01-01", end="2025-12-31")`).

---

## 🧠 Arquitetura do modelo
- `LSTM(50, return_sequences=True)`  
- `LSTM(50)`  
- `Dense(1)`  

Total de parâmetros treináveis: **30.651**

---

## 📈 Resultados e métricas

- **Mean Squared Error (MSE):** `42.59`  
- **R² Score:** `0.92`

Essas métricas indicam que o modelo capturou bem a variação dos preços no conjunto de teste (R²~=0.92). O MSE absoluto depende da escala dos preços (USD).

---

## 🖼️ Visualizações

> **Importante:** salve os gráficos gerados no Colab/Notebook dentro da pasta `images/` do repositório com os nomes abaixo, para que apareçam no README:

<img width="1005" height="548" alt="image" src="https://github.com/user-attachments/assets/c7a5a505-b0a5-4733-86ef-fd50e99b04fb" />
 — gráfico de **Fechamento diário**  

 
 <img width="1008" height="547" alt="image" src="https://github.com/user-attachments/assets/e7c41a63-9944-4cca-8027-d287875507c9" />
— gráfico de **Preço Real x Preço Previsto**
