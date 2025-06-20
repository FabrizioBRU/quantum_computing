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

## 🔹 Apêndice C – Esta Etapa
Este README corresponde à documentação da Etapa 1:
- Origem dos dados.
- Processo de limpeza e padronização.
- Normalização das séries (Min-Max).
- Scripts comentados para reprodutibilidade.

## ✉️ Contato
Fabrizio Bruzetti  
Email: fbruzetti@gmail.com  
LinkedIn: [linkedin.com/in/fbruzetti](https://linkedin.com/in/fbruzetti)

---
© 2025 - Mestrado FGV EAESP | Todos os direitos reservados.
