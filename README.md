# Previsão de Churn Empresarial – Projeto Integrador 1º Trimestre  
**Programa Avançado em Data Science e Decisão – Insper**  
**Autores:** Ilana Garcia, Izabelle Silva, Júlia Borges, Lívia Bertoni  
**Data:** Setembro de 2025  

---

## 🧠 Introdução

Quando falamos em **churn** (rotatividade), normalmente pensamos em clientes que cancelam serviços ou deixam de consumir produtos. No entanto, o mesmo conceito pode ser aplicado ao **mundo empresarial**: empresas também podem encerrar suas atividades permanentemente — um fenômeno com grande impacto financeiro para bancos, fornecedores, investidores e consultores.

O objetivo deste projeto é **desenvolver modelos de aprendizado de máquina capazes de prever se uma empresa encerrará suas operações nos dois anos seguintes**, utilizando dados reais da **Bisnode**, que reúne informações de empresas europeias.  

A análise concentra-se no **snapshot de 2012**, contendo dados financeiros, demográficos e indicadores de risco de fechamento empresarial.

---

## 📊 Base de Dados

A base utilizada é o **Bisnode Dataset (2012)**, derivado de uma série temporal de 2005 a 2016.  
O conjunto foi previamente limpo em **Python** e importado para **R**, já com variáveis tratadas e indicadores de imputação.

Principais características da base:
- **Unidade de análise:** empresa  
- **Variável resposta:** `churn_in_2y_int`  
  - `0` = empresa ativa  
  - `1` = empresa encerrada em até 2 anos  
- **Número de observações:** milhares de empresas europeias  
- **Tipo de variáveis:** indicadores financeiros, flags de imputação, dados demográficos e histórico de vendas  

---

## ⚙️ Metodologia

### 1. Preparação dos dados
- Tratamento de dados ausentes e padronização com o pacote **`recipes`** (tidymodels)  
- Separação em conjuntos de **treino (80%)** e **teste (20%)**  
- Balanceamento da variável resposta  
- Seleção e transformação das variáveis numéricas e categóricas  

### 2. Modelagem
Foram testados três modelos principais:
- Regressão Logística
- Ridge Regression
- LASSO
- Árvore de Decisão
- Random Forest
- XGBoost

### 3. Avaliação
O desempenho foi comparado usando as seguintes métricas:
- **AUC (Área sob a Curva ROC)**  
- **Acurácia**  
- **Precisão**  
- **Recall (Sensibilidade)**  
- **F1-score**  
- **Brier Score**  

Essas métricas foram calculadas a partir do conjunto de teste, permitindo comparar o desempenho dos modelos e identificar aquele com melhor poder preditivo.

---

## 📈 Resultados e Discussão

- O **modelo LASSO** apresentou melhor equilíbrio entre **interpretação e desempenho**, sendo mais parcimonioso e eficiente.  
- O **Random Forest** mostrou alta acurácia, mas menor interpretabilidade.  
- O **GLM** simples teve bom desempenho geral, com resultados estáveis e facilmente comunicáveis.  

De modo geral, as variáveis relacionadas a **vendas (sales_log1p)** e **idade da empresa (age_years)** tiveram peso significativo na predição do churn.

---

## 🧩 Ferramentas Utilizadas

- **R** (versão 4.3+)  
  - Principais pacotes:  
    `tidyverse`, `tidymodels`, `themis`, `ggplot2`, `randomForest`, `glmnet`, `yardstick`
- **Python (pré-processamento inicial)**
- **R Markdown / knitr** para relatórios reprodutíveis  
- **GitHub** para versionamento  

---

## 📁 Estrutura do Repositório

```text
projeto_integrador_1tri/
├── projeto_integrador_ilana_izabelle_julia_livia.Rmd   # Código-fonte principal em R
├── projeto_integrador_ilana_izabelle_julia_livia.html  # Relatório renderizado
├── cs_bisnode_panel.csv                                # Base de dados original
├── dataset_modelagem_final.csv                         # Base tratada para modelagem
├── bisnode_variable_names.xls                          # Dicionário de variáveis
└── README.md                                           # Este arquivo
```

---

## 💡 Como Reproduzir

1. **Clone este repositório:**
   ```bash
   git clone https://github.com/silvaizabelle/projeto_integrador_1tri.git
   cd projeto_integrador_1tri
   ```

2. **Abra o R Markdown:**
   ```r
   rmarkdown::render("projeto_integrador_ilana_izabelle_julia_livia.Rmd")
   ```

3. **Instale os pacotes necessários:**
   ```r
   install.packages(c(
     "tidyverse", "tidymodels", "themis", "randomForest",
     "glmnet", "ggplot2", "yardstick"
   ))
   ```

---

## 👩‍🔬 Equipe

- **Ilana Garcia**  
- **Izabelle Silva**  
- **Júlia Borges**  
- **Lívia Bertoni**

---

## 📚 Licença

Projeto desenvolvido para fins **acadêmicos** no **Insper**.  
Pode ser reutilizado e adaptado com a devida citação da fonte.
