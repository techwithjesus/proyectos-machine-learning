# Descripción de imágenes con Gradio

> Dos apps web que analizan imágenes: una describe lo que ve con una frase y la otra identifica qué objeto o animal aparece.

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/techwithjesus/proyectos-machine-learning/blob/main/descripcion-de-imagenes-gradio/image_captioning_gradio.ipynb)

| | |
|---|---|
| **Origen** | Proyecto guiado de Coursera |
| **Modelos** | [BLIP](https://huggingface.co/Salesforce/blip-image-captioning-base) de Salesforce y ResNet-18 de PyTorch |
| **Herramientas** | Python · Hugging Face Transformers · PyTorch · Gradio |
| **Resultado** | Dos demos interactivas que corren en el navegador |

## Qué hace

1. **Describe imágenes:** subes una foto y el modelo BLIP genera una frase que describe lo que hay en ella (por ejemplo, "a dog sitting on the grass").
2. **Clasifica imágenes:** el modelo ResNet-18, entrenado con ImageNet, dice qué es lo que aparece en la foto y muestra las 3 opciones más probables con su porcentaje de confianza.
3. **Las convierte en apps web:** Gradio crea la interfaz para subir imágenes y ver los resultados sin escribir nada de código web.

## Lo que aprendí

- Usar modelos preentrenados de Hugging Face y PyTorch sin entrenar nada desde cero.
- Convertir un modelo en una demo que cualquiera puede probar desde el navegador.

## Cómo correrlo

1. Ábrelo en Colab con el botón de arriba.
2. Corre las celdas. La primera vez tarda unos minutos porque descarga el modelo BLIP, que pesa casi 1 GB.
3. Gradio te da un link para abrir la app.

La demo de clasificación usa dos imágenes de ejemplo (`lion.jpg` y `cheetah.jpg`). Súbelas a Colab o cambia esa línea por tus propias imágenes.
