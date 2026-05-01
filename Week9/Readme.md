# Actividad 9: Implementación de Data Augmentation y Transfer Learning en Imágenes

Este proyecto presenta una comparativa avanzada entre dos estrategias fundamentales para optimizar modelos de Deep Learning: el Aumento de Datos (Data Augmentation) para mejorar la robustez y el Aprendizaje por Transferencia (Transfer Learning) para maximizar la eficiencia

## Objetivo
Implementar técnicas para mejorar el desempeño y la generalización de modelos:

El Data Augmentation permite aumentar artificialmente la cantidad y diversidad de datos.
El Transfer Learning permite reutilizar modelos preentrenados para resolver problemas con mayor eficiencia

# Dataset
*  Dataset: CIFAR-10,  Compuesto por 60,000 imágenes a color distribuidas en 10 clases de objetos (32x32 píxeles).
*  Resolución: 32x32 píxeles.
*  Preprocesamiento:Normalización de valores de píxeles al rango **[0, 1]** y aplicación de transformaciones aleatorias en     tiempo de ejecución.
  
## Implementación Técnica

### 1. Técnica de Data Augmentation
*   **Transformaciones:**  Rotación aleatoria (10%), zoom (10%), traslación horizontal/vertical y volteo horizontal. 
*   **Propósito:** Mitigar el overfitting al evitar que la red memorice imágenes específicas, obligándola a reconocer patrones generales del objeto.

### 2. Implementación de Transfer Learning (MobileNetV2)
Se reutilizó la arquitectura MobileNetV2, destacada por su eficiencia en dispositivos con recursos limitados.

*   **Modelo Base:** MobileNetV2 preentrenado con el dataset ImageNet.
*   **Técnica:** Congelación de capas base (trainable = False) para conservar la extracción de características genéricas y entrenamiento exclusivo de una nueva         cabeza clasificadora (GlobalAveragePooling2D + Dense).

## Resultados Principales
Tras un entrenamiento de 10 épocas, se extrajeron las siguientes observaciones:

*   **Modelo Base vs. Aumentado:**  El modelo con Data Augmentation muestra una curva de aprendizaje más orgánica. Aunque su precisión inicial es menor (~55% en validación), demuestra una capacidad de generalización superior al reducir el sobreajuste (overfitting) que presentaba el modelo base, el cual tendía a memorizar el ruido del dataset.

*   **Impacto de Transfer Learning:** El uso de pesos preentrenados permitió alcanzar una estabilidad inmediata en la pérdida (loss), pero con una precisión limitada (~32%). Esta diferencia respecto a los modelos anteriores se debe a que MobileNetV2 está optimizado para imágenes de 224x224; al trabajar con la resolución nativa de CIFAR-10 (32x32), se produce una pérdida significativa de información espacial en las capas iniciales del modelo.

##  Conclusiones Técnicas
*   **Eficacia del Aumento de Datos:** Se confirma como la mejor estrategia para este dataset, logrando un balance óptimo entre precisión y robustez.

*   **Limitaciones del Transfer Learning:** Aunque es eficiente en tiempo, la arquitectura MobileNetV2 requiere un reescalado de imágenes (upsampling) para ser competitiva en datasets de baja resolución como CIFAR-10.

*   **Generalización:** El modelo aumentado es el más confiable para entornos reales, ya que aprendió características invariantes a la rotación y traslación.


 ## Estructura del repositorio

```
Week9/
├── Actividad_9_Data_Augmentation.ipynb
├── Actividad_9_Transfer_Learning.ipynb
└── README.md
```
##  Cómo ejecutar
1.  Descarga el archivo .ipynb de este repositorio.
2.  Ábrelo en Google Colab.
3.  Ejecuta las celdas en orden: Entorno de Ejecución > Ejecutar todas.


