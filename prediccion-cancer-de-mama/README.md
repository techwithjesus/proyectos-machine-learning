# Predicción de cáncer de mama

> Modelo que clasifica tumores como benignos o malignos a partir de mediciones de sus células.

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/techwithjesus/proyectos-machine-learning/blob/main/prediccion-cancer-de-mama/breast_cancer_prediction.ipynb)

| | |
|---|---|
| **Origen** | Proyecto guiado de Coursera |
| **Dataset** | [Breast Cancer Wisconsin (Diagnostic)](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data), 569 casos con 30 mediciones cada uno |
| **Modelo** | Regresión logística |
| **Herramientas** | Python · pandas · scikit-learn · seaborn |
| **Resultado** | 95.1% de exactitud en datos de prueba |

## Qué hace

1. Descarga el dataset desde Kaggle con su API.
2. Limpia los datos: quita la columna vacía y convierte el diagnóstico (M = maligno, B = benigno) en números.
3. Separa los datos en entrenamiento (75%) y prueba (25%) y los escala con `StandardScaler`.
4. Entrena una regresión logística y la evalúa con la matriz de confusión y la exactitud.

## Resultados

De 143 casos de prueba, el modelo acertó 136:

| | Predijo benigno | Predijo maligno |
|---|---|---|
| **Era benigno** | 83 | 5 |
| **Era maligno** | 2 | 53 |

**Exactitud: 95.1%.** Solo 2 tumores malignos se clasificaron como benignos. En un diagnóstico médico ese es el error más importante de evitar.

## Lo que mejoraría

- **Escalado:** el notebook ajusta el escalador de nuevo con los datos de prueba (`fit_transform`). Lo correcto es usar solo `transform` para que el modelo no "vea" información de prueba.
- **Resultados repetibles:** agregar `random_state` a la división de datos para obtener siempre el mismo resultado.
- **Más métricas:** reportar *recall* y *precision*, que en medicina dicen más que la exactitud.

## Cómo correrlo

1. Crea un token en Kaggle: tu perfil → **Settings** → **API** → **Create New Token**.
2. En Colab, abre el ícono de la llave 🔑 (**Secrets**) y agrega `KAGGLE_USERNAME` y `KAGGLE_KEY`.
3. Corre todas las celdas.

Nunca escribas tus llaves directamente en un notebook.
