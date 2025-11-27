
````markdown
# Breast Cancer Wisconsin (Diagnostic) - Projeto de Classificação

**Trabalho Acadêmico**
**Disciplina:** Aprendizado de Máquina
**Aluna:** Bianca Couto Araujo

---

## Dataset

**Dataset Utilizado:** Breast Cancer Wisconsin (Diagnostic)

* **Fonte:** Biblioteca pública do scikit-learn (`sklearn.datasets`)
* **Documentação oficial:** [https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html)
* **Tipo de problema:** Classificação binária
* **Atributo Target:**
    * `0`: Tumor maligno
    * `1`: Tumor benigno

O dataset contém **569 instâncias** e **30 atributos numéricos**, derivados de medições extraídas de imagens digitalizadas de biópsias de mama.

---

## Estrutura do Repositório

Este repositório contém todos os arquivos gerados durante o projeto.

```text
projeto_breast_cancer/
│
├── data/
│   └── breast_cancer_original.csv
│
├── notebooks/
│   ├── 01_exploracao_preprocessamento.ipynb
│   └── 02_modelagem_resultados.ipynb
│
├── models/
│   ├── logisticregression_model.joblib
│   ├── randomforest_model.joblib
│   └── gradientboosting_model.joblib
│
├── results/
│   ├── target_distribution.png
│   ├── histograms.png
│   ├── correlation_matrix.png
│   ├── confusion_matrix_logisticregression.png
│   ├── confusion_matrix_randomforest.png
│   ├── confusion_matrix_gradientboosting.png
│   └── metrics_table.csv
│
└── report/
    └── Relatorio_Final.pdf
````

## Objetivo do Projeto

O projeto tem como finalidade:

  * **Explorar e caracterizar o dataset.**
  * Implementar e avaliar três modelos de classificação.
  * Comparar métricas e tempo de processamento.
  * Identificar o modelo com melhor desempenho.
  * Discutir o comportamento das classes do atributo *target*.

-----

## Pré-processamento Realizado

Foram adotados os seguintes procedimentos:

1.  **Padronização** dos atributos numéricos com `StandardScaler`.
2.  **Imputação** de valores ausentes com `SimpleImputer(strategy='mean')` (mantido para robustez do *pipeline*, apesar de o *dataset* não conter valores faltantes).
3.  **Separação treino/teste** com proporção **70/30** utilizando `stratify`.
4.  Construção de *pipelines* completos por modelo.
5.  **Validação cruzada** estratificada em **5 *folds***.

*Obs: O atributo target já estava em formato binário e não precisou ser modificado.*

-----

## Modelos Avaliados

Os algoritmos utilizados foram:

  * Logistic Regression
  * Random Forest Classifier
  * Gradient Boosting Classifier

As métricas avaliadas foram:

  * Acurácia
  * Precisão Macro
  * Recall Macro
  * F1-score Macro
  * Tempo de treino
  * Tempo de predição

Todas as métricas finais estão registradas em: `results/metrics_table.csv`

-----

## Resumo dos Resultados

**Melhor modelo:** Logistic Regression

  * Acurácia: **0.9883**
  * Precisão Macro: **0.9875**
  * Recall Macro: **0.9875**
  * F1-score Macro: **0.9875**

**Pior modelo:** Random Forest (embora tenha apresentado desempenho satisfatório no teste).

-----

## Como Executar

**1. Abrir os *notebooks* no Jupyter:**

  * `notebooks/01_exploracao_preprocessamento.ipynb`
  * `notebooks/02_modelagem_resultados.ipynb`

*Cada notebook contém células organizadas na ordem correta para execução.*

**2. Geração de Resultados:**

  * Os arquivos `.joblib` dos modelos serão salvos na pasta `models/`.
  * Os gráficos serão salvos na pasta `results/`.
  * A matriz de métricas será salva em `results/metrics_table.csv`.

-----

## Relatório

A versão final do trabalho acadêmico em PDF encontra-se em:

`report/Breast Cancer Wisconsin - Bianca Couto Araujo.pdf`

```
```
