# Predicción de abandono de clientes

> Modelo que predice qué clientes de una compañía telefónica se van a dar de baja, para actuar antes de perderlos.

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/techwithjesus/proyectos-machine-learning/blob/main/prediccion-abandono-clientes/customer_churn.ipynb)

| | |
|---|---|
| **Origen** | Proyecto guiado de Coursera |
| **Dataset** | Versión del curso del [Telco Customer Churn de IBM](https://www.kaggle.com/datasets/blastchar/telco-customer-churn), con 21 columnas: tipo de contrato, servicios, cargos mensuales y si el cliente se fue |
| **Modelo** | Árbol de decisión |
| **Herramientas** | PySpark · pandas · Plotly · Matplotlib |
| **Resultado** | AUC de 0.80 en datos de prueba |

## Qué hace

1. **Explora los datos** con histogramas, matriz de correlación y conteo de valores por categoría.
2. **Limpia los datos:** rellena los valores faltantes de `TotalCharges` con el promedio y quita un registro con una antigüedad imposible (más de 100 meses).
3. **Prepara las variables:** convierte las columnas de texto en números (`StringIndexer`), escala las numéricas (`StandardScaler`) y junta todo en un solo vector (`VectorAssembler`).
4. **Entrena un árbol de decisión** con 70% de los datos y lo evalúa con el 30% restante.
5. **Busca la mejor profundidad** del árbol probando de 2 a 20 niveles.
6. **Explica el modelo:** qué variables pesan más y cómo cambia el abandono según el tipo de contrato.

## Resultados

- **AUC de 0.797 en prueba** y 0.798 en entrenamiento, con profundidad 6. Que los dos números sean casi iguales indica que el modelo generaliza bien.
- **Sobreajuste visible:** con profundidad 20 el modelo llega a 0.99 en entrenamiento pero baja a 0.69 en prueba. Memoriza los datos en lugar de aprender patrones, por eso la profundidad 6 es la mejor opción.
- **El tipo de contrato es clave:** los clientes con contrato mes a mes son los que más se van.

## Lo que mejoraría

- Probar modelos más robustos, como Random Forest o Gradient Boosting, y compararlos con el árbol.
- Usar validación cruzada para elegir la profundidad.
- Las gráficas de Plotly no se ven en la vista previa de GitHub. Ábrelo en Colab para verlas.

## Cómo correrlo

El curso usó una versión modificada del dataset, con valores faltantes y datos atípicos agregados para practicar la limpieza. Descarga el [dataset original de Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn), súbelo a Colab con el nombre `dataset.csv` y corre todas las celdas. Los resultados pueden variar un poco.
