# Predição de Hipertireoidismo com Machine Learning

Projeto de conclusão do curso de Cientista de Dados da Ebac.

## 🎯 Objetivo
Desenvolver modelos de Machine Learning para identificar pacientes com hipertireoidismo a partir de características clínicas e exames laboratoriais.

## 📊 Dados
Base `Base_M43_Pratique_Hypothyroid.csv`, com 3.772 registros e variáveis como idade, sexo, uso de medicação antitireoidiana, histórico clínico (gravidez, cirurgia de tireoide, tumor, etc.) e exames laboratoriais (`TSH`, `T3`, `TT4`, `T4U`, `FTI`). Variável alvo: `binaryClass` (com/sem hipertireoidismo).

## 🔬 Metodologia
O projeto inclui:

- **Limpeza de dados**: tratamento de valores ausentes (`?`) coluna a coluna, correção de um valor de idade inconsistente (455 anos), remoção de colunas sem variabilidade (`TBG`, `TBG measured`), e imputação por mediana — mantendo outliers em exames laboratoriais (TSH, TT4, T4U, FTI) por serem clinicamente relevantes para o diagnóstico.
- **Codificação de variáveis categóricas** (`referral source` via one-hot, `binaryClass` mapeada para 0/1).
- **Análise univariada e bivariada**: distribuição de idade (bimodal), gênero (~70% mulheres), relação entre uso de medicação antitireoidiana e diagnóstico, matriz de correlação (maior correlação do alvo com `TSH`, `FTI`, `TT4` e `T3`).
- **Padronização** (`StandardScaler`) e **balanceamento de classes** com `SMOTE` (aplicados via `Pipeline` para evitar vazamento de dados durante a validação cruzada).
- Treinamento e comparação de **SVM** e **XGBoost**, com e sem otimização de hiperparâmetros via `GridSearchCV`.

Os modelos foram avaliados por meio de **Accuracy, Precision, Recall, F1-score e Matriz de Confusão**, com atenção especial à redução de falsos negativos.

## 📊 Resultados
O **SVM** sem otimização alcançou 96% de acurácia; otimizado, alcançou:
- Accuracy: **97%**
- F1-score macro: **0,92**

O **XGBoost** sem otimização já alcançou 99% de acurácia; otimizado, manteve:
- Accuracy: **99%**
- F1-score macro: **0,98**
- Apenas **1 falso negativo** no conjunto de teste (classe 0).

## 🏆 Conclusão
O XGBoost otimizado foi o modelo de melhor desempenho, apresentando alta capacidade de classificação e baixo número de falsos negativos.

## Tecnologias
- Python, pandas, numpy
- scikit-learn (SVM, GridSearchCV, StandardScaler, Pipeline)
- XGBoost
- imbalanced-learn (SMOTE)
- matplotlib, seaborn

## Como executar
1. Instale as dependências: `pip install pandas numpy scikit-learn xgboost imbalanced-learn matplotlib seaborn scipy`.
2. Coloque `Base_M43_Pratique_Hypothyroid.csv` no mesmo diretório do notebook.
3. Execute `Projeto_Final.ipynb` em ordem.
