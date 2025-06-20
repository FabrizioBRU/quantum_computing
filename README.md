# quantum_computing

# README – Projeto: Antecedentes da Adoção da Computação Quântica

Este repositório documenta as etapas técnicas do Trabalho Aplicado "Antecedentes da Adoção da Computação Quântica", elaborado por Fabrizio Bruzetti como parte do Mestrado Profissional em Gestão para a Competitividade. 

O objetivo do estudo é investigar como vetores antecedentes — Interesse Público, Inovação Formal (Patentes) e Produção Científica — podem sinalizar a trajetória de maturação de tecnologias emergentes, com foco na Computação Quântica.

## 📚 Estrutura do Repositório

### 1. `dados/`
Contém os arquivos de entrada utilizados nas análises:
- `interesse_publico.csv`
- `patentes_series.csv`
- `producao_cientifica.csv`

### 2. `scripts/`
Scripts em R utilizados para tratamento, normalização, modelagem e visualização:
- `01_limpeza_normalizacao.R`
- `02_modelo_bass.R`
- `03_modelos_gompertz_logistico.R`
- `04_grafo_ccf_loess.R`

### 3. `resultados/`
Saídas gráficas e tabelas produzidas:
- Gráficos comparativos dos modelos.
- Tabelas com parâmetros estimados.

### 4. `apendices/`
Contém versões PDF ou Markdown dos apêndices técnicos documentados no TA.

## 🔧 Reprodução das Análises
Para reproduzir as análises:
1. Tenha R ≥ 4.3 instalado com os pacotes: `tidyverse`, `minpack.lm`, `ggplot2`, `lubridate`, `scales`, `igraph`, `ggraph`.
2. Execute o script `01_limpeza_normalizacao.R` para importar e preparar os dados.
3. Siga com os scripts `02_`, `03_` e `04_` para rodar os modelos e gerar os gráficos.

## 🔹 Apêndice C – Etapa 1: Origem, Limpeza e Normalização dos Dados

### 📥 Origem dos Dados
Os dados foram obtidos de três fontes secundárias confiáveis:

- **Interesse Público:** índice anual do Google Trends para o termo “Quantum Computing” (2015–2024).
- **Inovação Formal:** contagem de patentes extraídas da base do Google Trends.
- **Produção Científica:** artigos publicados extraídos da WoS - Web of Sciense com filtros por palavra-chave e área.

### 🧹 Etapas de Limpeza e Padronização
1. Tratamento de valores ausentes (NA) por imputação linear.
2. Harmonização dos nomes das colunas.
3. Conversão para formato “tidy” (long data).
4. Inspeção visual por `ggplot2` para detectar outliers.

### 📏 Normalização

Cada vetor foi normalizado individualmente utilizando a técnica **Min-Max Scaling**:
```r
normalize <- function(x) {(x - min(x)) / (max(x) - min(x))}
df$normalizado <- normalize(df$valor_original)
```

Essa transformação possibilita comparar séries com escalas distintas no mesmo eixo.

### 📄 Script de Referência: `01_limpeza_normalizacao.R`

```r
# Carregar bibliotecas
library(tidyverse)
library(lubridate)

# Importar dados
interesse <- read.csv("dados/interesse_publico.csv")
interesse <- interesse %>%
  mutate(ano = as.integer(ano)) %>%
  drop_na(valor)

# Normalizar
normalize <- function(x) {(x - min(x)) / (max(x) - min(x))}
interesse$valor_norm <- normalize(interesse$valor)

# Exportar
write.csv(interesse, "dados/interesse_publico_normalizado.csv", row.names = FALSE)
```

---

## ✉️ Contato
Fabrizio Bruzetti  
Email: fbruzetti@gmail.com  
LinkedIn: [linkedin.com/in/fbruzetti](https://linkedin.com/in/fbruzetti)

---
© 2025 - Mestrado FGV EAESP | Todos os direitos reservados.
LinkedIn: [linkedin.com/in/fbruzetti](https://linkedin.com/in/fbruzetti)

---
© 2025 - Mestrado FGV EAESP | Todos os direitos reservados.
