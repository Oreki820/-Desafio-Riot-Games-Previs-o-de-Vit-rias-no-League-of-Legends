# 🎮 Desafio Riot Games — Previsão de Vitórias no League of Legends

## 🧭 Visão Geral do Projeto

Este projeto foi desenvolvido como parte de um **desafio de Ciência de Dados** inspirado na **Riot Games (League of Legends)**, com o objetivo de **prever qual time (azul ou vermelho)** vence uma partida usando **apenas informações pós-início de jogo** — como *First Blood*, *torres destruídas*, *dragões abatidos*, *ouro acumulado* e *experiência total*.

A proposta reproduz um **pipeline completo de Machine Learning**, desde a exploração dos dados até a modelagem e interpretação dos resultados, trazendo também uma leitura estratégica do que mais influencia as vitórias no LoL competitivo.

---

## 📊 Acesse o Dashboard Interativo
[![Ver no Looker Studio](https://img.shields.io/badge/LoL%20Dashboard%20-%20Abrir%20Painel-blueviolet?style=for-the-badge&logo=googledatastudio)]([[https://lookerstudio.google.com/reporting/68d538d5-b85f-47f7-aaf4-4367a07555c1])

---

## ⚙️ Objetivos

- 📊 Desenvolver um **modelo de classificação** capaz de prever o vencedor da partida.
- 🧼 Criar um **pipeline de dados limpo e reproduzível**, com padronização e validação cruzada.
- 🧠 Analisar **quais fatores mais influenciam nas vitórias** (ouro, dragões, experiência, visão, etc).
- 🚀 Implementar **modelos otimizados (ensembles)** e comparar com modelos básicos.
- 📈 Gerar **insights de negócio** aplicáveis ao cenário competitivo de eSports.

---

## 🧩 Estrutura do Projeto

| Etapa | Descrição |
|:--|:--|
| **1️⃣ Importação e Carregamento** | Leitura e visualização inicial do dataset (CSV com dados de partidas). |
| **2️⃣ Limpeza e Pré-processamento** | Tratamento de valores ausentes, remoção de colunas irrelevantes e padronização. |
| **3️⃣ Análise Exploratória (EDA)** | Gráficos e correlações para entender padrões entre vitórias e métricas. |
| **4️⃣ Divisão dos Dados** | Separação entre treino e teste (`train_test_split` e `StandardScaler`). |
| **5️⃣ Modelagem Inicial** | Teste com **Logistic Regression**, **Naive Bayes** e **Decision Tree**. |
| **6️⃣ Validação Cruzada** | Uso de `KFold` para medir estabilidade dos modelos. |
| **7️⃣ Interpretação** | Importância das variáveis via Árvore de Decisão. |
| **8️⃣ Otimização** | Modelos **RandomForest** e **GradientBoosting** como benchmarks. |

---

## 🧠 Modelos Utilizados

| Categoria | Modelo | Accuracy | ROC AUC | Observações |
|:--|:--|:--:|:--:|:--|
| 🔹 Básico | Logistic Regression | 0.715 | **0.805** | Melhor modelo linear e interpretável |
| 🔹 Básico | Gaussian Naive Bayes | 0.718 | 0.798 | Simples e rápido, ótimo benchmark |
| 🔹 Interpretação | Decision Tree | 0.645 | 0.645 | Mais fraco, mas útil para feature importance |
| 🔸 Otimizado | Random Forest | **0.722** | **0.802** | Melhor equilíbrio entre performance e estabilidade |
| 🔸 Otimizado | Gradient Boosting | 0.719 | 0.801 | Alternativa leve e eficiente |

📊 **Melhor modelo:** `RandomForestClassifier`  
🎯 **AUC ≈ 0.80** — boa separação entre vitórias e derrotas.  
🔁 **Validação cruzada:** média de 0.73 ± 0.009 (alta estabilidade).

---

## 🔍 Principais Insights

### 💰 Vantagem Econômica e de Experiência
- A **diferença de ouro (`GoldDiff`)** foi o fator mais importante para prever vitórias.  
- A **diferença de experiência (`ExperienceDiff`)** também se mostrou fortemente correlacionada (r ≈ 0.49).  
- Times com **mais ouro e XP** venceram mais de **70%** das partidas.

### 🧠 Controle de Mapa
- **Wards colocadas e destruídas** indicam controle de visão — quanto maior o domínio, maior a taxa de vitória.  
- **Farm da selva e minions** também aparecem entre os fatores relevantes.

### 🐉 Objetivos Neutros
- A captura de **Dragões e Heralds** aumenta gradualmente a probabilidade de vitória.  
- Contudo, seu impacto é **indireto**, pois reforçam a vantagem econômica já existente.

### ⚔️ Eventos Iniciais
- *First Blood* e *Primeira Torre* têm influência moderada (10–20%),  
  mas são **menos relevantes que o acúmulo de ouro e experiência** ao longo da partida.

---

## 📈 Curvas ROC — Comparativo

Ambos os ensembles (**RandomForest e GradientBoosting**) mantêm **AUC acima de 0.80**, confirmando excelente poder de separação.

---

## 🧮 Tecnologias e Ferramentas

| Categoria | Ferramenta |
|:--|:--|
| 🐍 Linguagem | Python 3.10 |
| 📚 Bibliotecas | pandas, numpy, matplotlib, seaborn, scikit-learn |
| 🔬 Ambiente | Google Colab |
| 📊 Visualização | matplotlib, seaborn, plotly |
| 🧠 Modelagem | LogisticRegression, GaussianNB, DecisionTree, RandomForest, GradientBoosting |
| 🧪 Validação | KFold, cross_val_score |
| 🗂️ Dataset | Fornecido pela Riot Games (dados simulados de partidas LoL) |

---

## 💡 Conclusões Gerais

- A vitória no LoL é fortemente determinada por **vantagens econômicas e de experiência**, não por eventos isolados.  
- Modelos lineares e ensemble atingiram **AUC ≈ 0.80**, demonstrando **boa capacidade preditiva**.  
- O pipeline mostrou-se **robusto, estável e replicável**, ideal para aplicações em **eSports Analytics**.

> 🧩 “No League of Legends, vencer é consequência de controlar o ouro, a experiência e o mapa — e a Ciência de Dados provou isso.”

---

## 🧑‍💻 Autor

**👤 Lucas Gabriel Ferreira Gomes**  
📍 Santana do Livramento, RS – Brasil  
🎓 Cientista de Dados
🌐 [LinkedIn](www.linkedin.com/in/lucas-gabriel-dados) | [GitHub](https://github.com/Oreki820)

---

## 🏷️ Licença

Este projeto é de uso **educacional e demonstrativo**.  
Sinta-se à vontade para **clonar, adaptar e evoluir** este pipeline.  
© 2025 – Projeto educacional baseado em dados públicos de *League of Legends*.
