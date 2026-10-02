# Regressão Múltipla — Energy Efficiency

Projeto desenvolvido para a disciplina de **Modelagem Estatística**, com o objetivo de aplicar técnicas de **Regressão Linear Múltipla (MRLM)** ao dataset **Energy Efficiency**.

O trabalho contempla desde a preparação e análise exploratória dos dados até a construção, seleção, avaliação e diagnóstico de modelos de regressão.

---

## Objetivo

Investigar a relação entre as características dos edifícios presentes no dataset **Energy Efficiency** e seu respectivo consumo energético, utilizando modelos de Regressão Linear Múltipla.

A análise será conduzida de forma exploratória e inferencial, buscando:

* compreender as características e relações presentes nos dados;
* identificar variáveis relevantes para a explicação das respostas;
* construir modelos de regressão linear múltipla;
* comparar diferentes especificações de modelo;
* verificar as hipóteses e condições necessárias para a utilização dos modelos;
* interpretar estatisticamente os resultados obtidos.

---

## Dataset

O projeto utiliza o dataset **Energy Efficiency**, disponibilizado pelo **UCI Machine Learning Repository**.

A base contém informações relacionadas às características de edifícios e duas variáveis de interesse associadas à demanda energética:

* **Heating Load**
* **Cooling Load**

A base original será mantida no repositório para garantir a rastreabilidade dos dados utilizados na análise.

**Fonte:** [UCI Machine Learning Repository — Energy Efficiency](https://archive.ics.uci.edu/dataset/242/energy+efficiency)

---

## Metodologia

O desenvolvimento do projeto será organizado em etapas:

### 1. Preparação e Análise Exploratória

Inicialmente serão verificadas as características da base, incluindo:

* dimensões e tipos das variáveis;
* valores ausentes;
* duplicidades;
* estatísticas descritivas;
* distribuição das variáveis;
* relações entre variáveis explicativas e respostas;
* correlações e possíveis indícios de multicolinearidade.

### 2. Modelagem por Regressão Linear Múltipla

Será construído inicialmente um modelo contendo as variáveis explicativas disponíveis, seguido da análise de:

* estimativas dos coeficientes;
* erros-padrão;
* testes de significância;
* intervalos de confiança;
* análise de variância (ANOVA);
* teste F global;
* coeficiente de determinação (R²);
* R² ajustado.

### 3. Seleção e Comparação de Modelos

A partir do modelo inicial, serão avaliadas diferentes especificações de Regressão Linear Múltipla com o objetivo de obter uma representação adequada da variável resposta, buscando equilibrar qualidade do ajuste, parcimônia e interpretabilidade.

Serão considerados procedimentos de **seleção de variáveis**, incluindo a avaliação individual dos preditores e métodos sistemáticos de seleção, como **seleção para frente (forward)**, **eliminação para trás (backward)** e **seleção stepwise**, quando aplicáveis. A comparação entre os modelos poderá utilizar critérios como **R² ajustado**, **AIC (Akaike Information Criterion)** e **BIC (Bayesian Information Criterion)**, além da significância dos coeficientes e da coerência estatística das especificações.

### 4. Diagnóstico do Modelo

O modelo final será avaliado por meio da análise de resíduos e de possíveis observações influentes, verificando aspectos como:

* linearidade;
* normalidade dos resíduos;
* homocedasticidade;
* pontos discrepantes;
* leverage;
* influência das observações.

Os procedimentos e decisões adotados serão documentados nos notebooks.

---

## Estrutura do Projeto

```text
Regressao-Multipla-Energy-Efficiency/
│
├── data/
│   ├── raw/
│   │   └── ENB2012_data.xlsx
│   └── processed/
│
├── notebooks/
│   ├── 01_preparacao_e_AED.ipynb
│   ├── 02_modelagem_MRLM.ipynb
│   ├── 03_selecao_e_comparacao.ipynb
│   └── 04_diagnostico_modelo_final.ipynb
│
├── figures/
│   ├── exploracao/
│   ├── modelos/
│   └── diagnostico/
│
├── article/
│
├── slides/
│
├── README.md
├── requirements.txt
├── LICENSE
└── .gitignore
```

### Organização dos diretórios

**`data/raw/`**
Armazena os dados originais utilizados no projeto, preservados sem alterações.

**`data/processed/`**
Armazena os dados após as etapas de processamento e preparação para a análise.

**`notebooks/`**
Contém os notebooks utilizados para análise, modelagem e diagnóstico.

**`figures/`**
Armazena as principais visualizações produzidas durante o projeto, organizadas por etapa.

**`article/`**
Contém o relatório técnico elaborado com base nos resultados obtidos no projeto.

**`slides/`**
Contém os materiais utilizados na apresentação do trabalho.

---

## Notebooks

| Notebook                            | Conteúdo                                                     |
| ----------------------------------- | ------------------------------------------------------------ |
| `01_preparacao_e_AED.ipynb`         | Preparação da base e análise exploratória dos dados          |
| `02_modelagem_MRLM.ipynb`           | Construção e interpretação dos modelos de regressão múltipla |
| `03_selecao_e_comparacao.ipynb`     | Seleção, comparação e avaliação de diferentes modelos        |
| `04_diagnostico_modelo_final.ipynb` | Diagnóstico e avaliação do modelo escolhido                  |

Os notebooks serão desenvolvidos no **Google Colab**, utilizando o ambiente Jupyter.

---

## Reprodutibilidade

A análise será desenvolvida de forma a permitir a reprodução dos resultados a partir dos dados e códigos disponíveis neste repositório.

O projeto utilizará Python e bibliotecas voltadas à análise de dados, estatística e visualização. As dependências utilizadas serão registradas em `requirements.txt`.

---

## Resultados

> **Em desenvolvimento.**

Esta seção será atualizada após a conclusão das etapas de análise exploratória, modelagem, seleção e diagnóstico dos modelos.

---

## Autores

* **João Ivo Rocha Alves**
* **Juan Bryan Araújo Lima**
* **Kaleb Soares Souza**

---

## Licença

Este projeto está disponível sob a licença **MIT**.

Consulte o arquivo [`LICENSE`](LICENSE) para mais informações.
