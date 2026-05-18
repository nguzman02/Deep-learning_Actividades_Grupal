
### ACTIVIDAD PRESENTADA POR 

* NUBIA GUZMAN 
* JOHAN AVILA 
* DEISY MURCIA
* RUMI TORRES

## Actividad 13: Implementación de un Autoencoder en una Red Denoising usando el dataset MNIST en Google


En esta actividad, las y los creadores de oportunidades implementarán un modelo básico de Autoencoder Denoising utilizando el dataset MNIST en un entorno de práctica guiada (Google Colab). El propósito es comprender cómo las redes neuronales pueden aprender representaciones comprimidas de los datos y reconstruir imágenes afectadas por ruido, fortaleciendo así conceptos relacionados con aprendizaje no supervisado y redes generativas.

La actividad busca evidenciar la capacidad de diseñar y entrenar una arquitectura encoder–decoder, aplicar procesos de reconstrucción de imágenes y analizar el desempeño del modelo mediante la comparación entre imágenes originales, imágenes con ruido e imágenes reconstruidas. Asimismo, se espera que el/la creador(a) de oportunidades documente resultados y presente conclusiones técnicas breves a partir del comportamiento observado durante el entrenamiento.

1. Configure un entorno de trabajo en Google Colab para el desarrollo de la actividad.
2. Cargue y prepare el dataset MNIST para el entrenamiento del modelo.
3. Aplique ruido artificial a las imágenes del dataset con el fin de construir un escenario de reconstrucción.
4. Diseñe e implemente un modelo Autoencoder Denoising utilizando TensorFlow/Keras o PyTorch.
5. Entrene el modelo utilizando las imágenes con ruido como entrada y las imágenes originales como referencia de salida.
6. Evalúe el desempeño del modelo observando la capacidad de reconstrucción de las imágenes.
7. Genere visualizaciones comparativas entre:
- Imagen original
- Imagen con ruido
- Imagen reconstruida
8. Incluya conclusiones técnicas breves sobre:
- comportamiento del modelo
- calidad de reconstrucción
- posibles aplicaciones reales de los autoencoders
9. Entregue como evidencia:
- Notebook de Google Colab
- Código funcional y ejecutable
- Resultados visibles del entrenamiento y reconstrucción
- Comentarios y conclusiones dentro del notebook
10. La entrega debe realizarse en formato PDF con enlace funcional al notebook de Google Colab o mediante archivo .ipynb correctamente organizado.


## El objetivo es que el modelo aprenda a:
- Comprimir imágenes (encoder)
- Reconstruir imágenes limpias a partir de imágenes con ruido (decoder)

---

## Objetivos
- Comprender el aprendizaje no supervisado
- Diseñar arquitectura encoder–decoder
- Aplicar ruido artificial a imágenes
- Evaluar la calidad de reconstrucción

---

## Dataset
Se utilizó el dataset **MNIST**, que contiene:
- 60,000 imágenes de entrenamiento  
- 10,000 imágenes de prueba  
- Imágenes en escala de grises de tamaño 28x28 píxeles  

---

## Metodología

### 1. Preparación de datos
- Normalización de imágenes (0–1)
- Transformación a formato (28,28,1)

### 2. Generación de ruido
Se aplica ruido gaussiano a las imágenes para simular datos corruptos.

### 3. Modelo Autoencoder
Se implementa un modelo CNN con:
- Encoder: Conv2D + MaxPooling  
- Decoder: Conv2DTranspose  

### 4. Entrenamiento
- Entrada: imágenes con ruido  
- Salida esperada: imágenes originales  

---

## Resultados

### Comparación de imágenes
Se analizan tres tipos de imágenes:
- Imagen original  
- Imagen con ruido  
- Imagen reconstruida  

El modelo logra eliminar gran parte del ruido y recuperar la estructura del dígito.

---

## Evaluación
- Métrica utilizada: Loss (binary crossentropy)
- Se observa reducción progresiva del error durante el entrenamiento

---
## Conclusiones técnicas breves (para pegar en Markdown)
Pega esto en una celda Markdown y ajústalo a lo que observes en tus gráficas:
Conclusiones técnicas:

1) Comportamiento del modelo durante el entrenamiento

La pérdida (loss) disminuye de forma progresiva, indicando que el autoencoder aprende una representación interna que preserva la estructura del dígito y reduce el error de reconstrucción. [keras.io]
Si la val_loss se estabiliza o deja de mejorar, suele indicar que el modelo ha llegado a un punto de convergencia (o que hace falta ajustar capacidad/épocas/ruido).

2) Calidad de reconstrucción

Las imágenes reconstruidas suelen recuperar bordes y trazos principales del dígito, eliminando buena parte del ruido gaussiano. [keras.io]
Las diferencias típicas aparecen en zonas de detalle fino (píxeles débiles), donde el modelo tiende a “suavizar” la imagen.

3) Posibles aplicaciones reales de autoencoders

Reducción de ruido en imágenes médicas (rayos X, resonancias), digitalización de documentos o cámaras en baja luz.
Compresión y representación latente para almacenamiento eficiente.
Detección de anomalías: si el autoencoder aprende “lo normal”, fallará al reconstruir patrones raros; ese error puede usarse como señal de anomalía. (Este uso se menciona como ejemplo típico en tutoriales introductorios de autoencoders).


---------------
## Estructura del repositorio
Week12/
├── week12_Actividad12.ipynb └── README.md

Cómo ejecutar el notebook

Abrir Google Colab
Ejecutar las celdas en orden -> Entorno de Ejecución --> Ejecutar todas
Las gráficas de comparación y la matriz de confusión se generarán automáticamente al final.
