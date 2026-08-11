# Predição de Hipertireoidismo com Machine Learning

## 🎯 Objetivo
Desenvolver modelos de Machine Learning para identificar pacientes com hipertireoidismo a partir de características clínicas e exames laboratoriais.

## 🔬 Metodologia
O projeto inclui análise exploratória dos dados, pré-processamento, balanceamento das classes com SMOTE e treinamento de modelos de classificação.

Foram implementados e comparados os modelos **SVM** e **XGBoost**, com otimização de hiperparâmetros utilizando `GridSearchCV`.

Os modelos foram avaliados por meio de **Accuracy, Precision, Recall, F1-score e Matriz de Confusão**, com atenção especial à redução de falsos negativos.

## 📊 Resultados
O **SVM otimizado** alcançou:
- Accuracy: **97%**
- F1-score macro: **0,92**

O **XGBoost otimizado** apresentou o melhor desempenho:
- Accuracy: **99%**
- F1-score macro: **0,98**
- Apenas **1 falso negativo** no conjunto de teste.

## 🏆 Conclusão
O XGBoost otimizado foi o modelo de melhor desempenho, apresentando alta capacidade de classificação e baixo número de falsos negativos.
