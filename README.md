# Projeto Integrador – 1º Trimestre  
**Programa Avançado em Data Science e Decisão – Insper**  
**Autores:** Ilana Garcia, Izabelle Silva, Júlia Borges, Lívia Bertoni  

---

## 🧠 Contexto do Projeto

Este projeto foi desenvolvido como parte da disciplina **Projeto Integrador** do 1º trimestre do Programa Avançado em Data Science e Decisão do **Insper**.  
O objetivo é aplicar conceitos de **ciência de dados**, **estatística** e **aprendizado de máquina** em um problema real, explorando todas as etapas do ciclo de análise de dados: da limpeza e tratamento até a modelagem e avaliação dos resultados.

---

## 📊 Base de Dados

A base utilizada é o **Bisnode dataset (snapshot de 2012)**, que contém informações sobre empresas europeias, incluindo dados financeiros, demográficos e de sobrevivência no mercado.  
O foco da análise é compreender **fatores que influenciam a sobrevivência e o churn** de empresas.

**Arquivos incluídos no repositório:**
- `cs_bisnode_panel.csv` — base de dados original  
- `bisnode_variable_names.xls` — dicionário de variáveis  
- `dataset_modelagem_final.csv` — base tratada e preparada para modelagem  

---

## ⚙️ Metodologia

### 1. Preparação dos dados
- Seleção das variáveis contínuas (exames e sinais vitais financeiros)  
- Tratamento de dados ausentes e padronização com o pacote **`recipes`** do **tidymodels**  
- Análise exploratória e identificação de padrões  
- Redução de dimensionalidade e agrupamento com **K-Means**

### 2. Determinação dos clusters
- Utilização dos métodos do **cotovelo** e do **índice de silhueta** para identificar o número ótimo de grupos

### 3. Visualização
- Aplicação de **PCA (Análise de Componentes Principais)** para projeção dos grupos em 2D e visualização das relações entre variáveis e clusters

### 4. Modelagem preditiva
- Divisão treino/teste (80/20)  
- Ajuste e comparação de três modelos:  
  - Regressão Logística  
  - Random Forest  
  - XGBoost  
- Avaliação com as métricas:  
  - AUC  
  - Acurácia  
  - Sensibilidade  
  - Especificidade  

---

## 🧩 Ferramentas Utilizadas

- **R (versão 4.3+)**  
  Pacotes principais:  
  `tidyverse`, `tidymodels`, `ggplot2`, `factoextra`, `cluster`, `xgboost`, `randomForest`, `yardstick`  
- **R Markdown / knitr** para reprodutibilidade e formatação do relatório  
- **GitHub** para versionamento e colaboração  

---

## 📈 Resultados Esperados

- Identificação de **perfis de empresas** com maior risco de churn  
- Avaliação comparativa dos algoritmos de classificação  
- Interpretação dos clusters obtidos e de suas características distintivas  
- Geração de **insights** para a tomada de decisão baseada em dados  

---

## 📁 Estrutura do Repositório

```text
projeto_integrador_1tri/
├── Insper-DS-Projeto-Integrador-2025.pdf           # Relatório final
├── projeto_integrador_ilana_izabelle_julia_livia.Rmd  # Código fonte em R
├── projeto_integrador_ilana_izabelle_julia_livia.html # Relatório HTML gerado
├── cs_bisnode_panel.csv                            # Base de dados original
├── bisnode_variable_names.xls                      # Dicionário de variáveis
├── dataset_modelagem_final.csv                     # Base final tratada
└── README.md                                       # Este arquivo
```

---

## 💡 Como Reproduzir

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/silvaizabelle/projeto_integrador_1tri.git
   cd projeto_integrador_1tri
   ```

2. **Abra o arquivo R Markdown:**

   ```r
   rmarkdown::render("projeto_integrador_ilana_izabelle_julia_livia.Rmd")
   ```

3. **Instale os pacotes necessários:**

   ```r
   install.packages(c(
     "tidyverse", "tidymodels", "factoextra",
     "cluster", "xgboost", "randomForest", "yardstick"
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

Este projeto é de uso acadêmico e segue os princípios de **reprodutibilidade e transparência científica**.  
Sinta-se à vontade para explorar e adaptar, mencionando a fonte.
