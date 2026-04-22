# Actividad 8: Implementación de un Modelo Popular de CNN en TensorFlow + Keras y/o PyTorch en Google Colab

Este proyecto presenta una comparativa entre dos estrategias de Deep Learning para la clasificación de imágenes: una arquitectura **CNN personalizada** y una aproximación mediante **Transfer Learning**.

## Objetivo
Implementación de un modelo de CNN, carga y preprocesamiento de datos, definición de arquitectura, entrenamiento y evaluación de métricas. Se busca demostrar la eficiencia de reutilizar modelos preentrenados frente a arquitecturas diseñadas desde cero.

## Implementación Técnica

### 1. CNN desde cero (Arquitectura Base)
*   **Capas:** Dos bloques de Conv2D (32 y 64 filtros) seguidos de `MaxPooling2D`.
*   **Propósito:** Comprender la extracción jerárquica de patrones (bordes, texturas y formas).

### 2. Transfer Learning (MobileNetV2)
*   **Modelo Base:** MobileNetV2 preentrenado con ImageNet.
*   **Adaptación:** Uso de UpSampling2D para redimensionar las imágenes de 32x32 a 96x96 píxeles.
*   **Regularización:** Inclusión de una capa `Dropout(0.3)` para mitigar el sobreajuste.

## Resultados Principales
Basado en el entrenamiento de 6 épocas con el dataset CIFAR-10:

*   **CNN Base:** Mostró una mejora constante pero lenta, alcanzando aproximadamente un **66% de precisión** en validación.
*   **Modelo Transfer Learning:** Logró una convergencia mucho más estable y veloz, superando el **75% de precisión** desde la primera época y finalizando cerca del **80%**.

 <img width="1133" height="812" alt="image" src="https://github.com/user-attachments/assets/7e931651-1252-4766-a8a8-cf96b685118c" />


##  Conclusiones Técnicas

*   **Convolución (Conv):** Es el proceso donde los filtros recorren la imagen detectando rasgos como bordes y texturas. Al incrementar de 32 a 64 filtros, la red logra combinar rasgos simples para entender conceptos visuales más complejos.
*   **Padding ('same'):** Técnica que añade bordes para mantener el tamaño original de la imagen (32x32). Esto es crucial para no perder información en los bordes y esquinas de la imagen.
*   **Stride (Zancada):** Se mantuvo en 1. Un salto pequeño garantiza un análisis exhaustivo de cada píxel, algo vital en imágenes pequeñas de 32x32 como las de CIFAR-10.
*   **Hallazgo:** La comparación evidencia que usar un modelo preentrenado (MobileNetV2) es mucho más eficiente. Al contar con 'conocimiento previo' de ImageNet, el modelo logra una convergencia más estable y una precisión superior en menos tiempo que la CNN básica. Como evidencia, la CNN Base necesitó 6 épocas para llegar apenas al 66% de precisión, mientras que el Transfer Learning superó el 75% desde la primera época. Esto refuerza el argumento de que 'no hay que reinventar la rueda.
 
##  Cómo ejecutar
1.  Descarga el archivo .ipynb de este repositorio.
2.  Ábrelo en Google Colab.
3.  Ejecuta las celdas en orden: Entorno de Ejecución > Ejecutar todas.
