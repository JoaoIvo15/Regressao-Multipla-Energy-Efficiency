# Regressão Múltipla — Energy Efficiency

Projeto desenvolvido para a disciplina de **Modelagem Estatística**, com aplicação de técnicas de **Regressão Linear Múltipla (MRLM)** ao conjunto de dados **Energy Efficiency**. O trabalho investiga a relação entre características construtivas de edificações e suas demandas de aquecimento (*Heating Load*, `Y1`) e resfriamento (*Cooling Load*, `Y2`).

O projeto está organizado em três notebooks, que documentam a preparação dos dados, a análise exploratória, a seleção dos modelos, os diagnósticos e a avaliação de especificações alternativas.

---

## Objetivo

Avaliar modelos de Regressão Linear Múltipla para explicar as demandas de aquecimento e resfriamento de edificações simuladas, considerando qualidade do ajuste, parcimônia, multicolinearidade e comportamento dos resíduos.

Os objetivos específicos são:

- verificar a integridade e caracterizar as variáveis do conjunto de dados;
- explorar associações entre preditores e respostas;
- investigar dependências lineares entre variáveis explicativas;
- construir e comparar especificações de regressão;
- avaliar os resíduos e identificar observações potencialmente influentes;
- investigar transformações das respostas e uma especificação com interação entre preditores;
- documentar os resultados e as limitações dos modelos avaliados.

---

## Dataset

O projeto utiliza o conjunto **Energy Efficiency**, disponibilizado pelo **UCI Machine Learning Repository**. A base reúne 768 observações, oito variáveis explicativas (`X1` a `X8`) e duas respostas contínuas:

- **Heating Load (`Y1`)** — demanda de aquecimento;
- **Cooling Load (`Y2`)** — demanda de resfriamento.

Os dados representam diferentes configurações de edificações simuladas. Na análise exploratória, não foram identificados valores ausentes, linhas duplicadas ou valores infinitos. Também foi identificada uma relação linear exata entre `X2`, `X3` e `X4`, aspecto considerado na construção dos modelos para evitar dependência linear perfeita entre os preditores.

**Fonte:** [UCI Machine Learning Repository — Energy Efficiency](https://archive.ics.uci.edu/dataset/242/energy+efficiency).

A base original utilizada está disponível em `data/raw/ENB2012_data.xlsx`.

---

## Metodologia

O trabalho está documentado em três etapas.

### 1. Preparação e análise exploratória

Foram avaliadas a estrutura e a integridade da base, as estatísticas descritivas, as distribuições das respostas e dos preditores, as associações entre variáveis e a presença de observações potencialmente atípicas. A análise identificou a relação determinística `X2 = X3 + 2 X4`, que exige cuidado na especificação dos modelos.

### 2. Modelagem e seleção de modelos

Foram estimados modelos por Mínimos Quadrados Ordinários e comparadas diferentes especificações. A seleção considerou medidas como `R²` ajustado, AIC, BIC, RMSE, testes parciais e fator de inflação da variância (VIF). As variáveis categóricas foram representadas por variáveis indicadoras.

Os modelos de referência utilizados na etapa de diagnóstico foram:

- **Modelo 122 para `Y1`:** `X3`, `X5`, `X7` e `X8`;
- **Modelo 17 para `Y2`:** `X1`, `X5` e `X7`.

### 3. Diagnóstico e avaliação de especificações alternativas

Os modelos de referência foram avaliados por meio de gráficos e testes de diagnóstico dos resíduos, incluindo Breusch–Pagan, Jarque–Bera e Ramsey RESET. Também foram investigados leverage, resíduos studentizados externamente, distância de Cook, DFBETAS e padrões residuais por configuração geométrica.

As transformações Box–Cox e Yeo–Johnson foram avaliadas, mas não eliminaram conjuntamente os problemas identificados. Por fim, foram comparados modelos aditivos e especificações com interação entre `X1` e `X3`.

---

## Principais resultados

- A análise exploratória identificou dependência linear perfeita entre `X2`, `X3` e `X4`, exigindo que essas variáveis não fossem incluídas simultaneamente na mesma matriz de preditores.
- Os modelos de referência apresentaram bom ajuste amostral, mas os diagnósticos indicaram heterocedasticidade, desvios da normalidade e possível inadequação funcional.
- A investigação das observações potencialmente influentes não encontrou evidências concretas de erro nos registros que justificassem sua exclusão; por isso, as observações foram mantidas.
- As transformações Box–Cox e Yeo–Johnson produziram melhorias limitadas e não resolveram conjuntamente os problemas dos resíduos.
- A inclusão da interação `X1 × X3` melhorou as medidas de ajuste nas duas respostas. Em relação às alternativas aditivas, o `R²` ajustado passou de `0,9202` para `0,9272` em `Y1` e de `0,8836` para `0,8938` em `Y2`. O RMSE amostral diminuiu de `2,8310` para `2,7022` em `Y1` e de `3,2346` para `3,0879` em `Y2`.
- Apesar da melhora de ajuste, o VIF máximo aumentou para aproximadamente `12,683`, e os diagnósticos continuaram apontando problemas residuais.

Os resultados devem ser interpretados como desempenho **na amostra utilizada**. Como não foi realizada validação independente, as métricas obtidas não comprovam, por si só, capacidade de generalização para novos dados. O projeto reconhece as limitações dos modelos, em vez de afirmar que todos os pressupostos foram satisfeitos.

---

## Estrutura do projeto

```text
Regressao-Multipla-Energy-Efficiency/
│
├── data/
│   └── raw/
│       └── ENB2012_data.xlsx
│
├── notebooks/
│   ├── 01_preparacao_e_AED.ipynb
│   ├── 02_modelagem_MRLM.ipynb
│   └── 03_diagnostico_e_selecao_final.ipynb
│
├── article/
│   └── Relatório técnico do projeto
│
├── slides/
│   └── Material da apresentação
│
├── README.md
├── requirements.txt
├── LICENSE
└── .gitignore
