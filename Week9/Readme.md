# Actividad 9: Implementación de Data Augmentation y Transfer Learning en Imágenes

Este proyecto presenta dos estrategias fundamentales para optimizar modelos de Deep Learning: el Aumento de Datos (Data Augmentation) para mejorar la robustez y el Aprendizaje por Transferencia (Transfer Learning) para maximizar la eficiencia

## Objetivo
Implementar técnicas para mejorar el desempeño y la generalización de modelos: 

* El Data Augmentation permite aumentar artificialmente la cantidad y diversidad de datos.
* El Transfer Learning permite reutilizar modelos preentrenados para resolver problemas con mayor eficiencia

# Dataset
*  Dataset: CIFAR-10,  Compuesto por 60,000 imágenes a color distribuidas en 10 clases de objetos (32x32 píxeles).
*  Resolución: 32x32 píxeles.
*  Preprocesamiento: Normalización inicial al rango [0, 1] y validación cruzada mediante una división  de entrenamiento (50k) y prueba (10k).

  
## Implementación Técnica

 **Modelo Base (Baseline):** Arquitectura CNN simple de una capa Conv2D (32 filtros) entrenada desde cero con datos estáticos para establecer el rendimiento de control.
 
**Modelo con Data Augmentation:** Inserción de un bloque secuencial de transformaciones aleatorias (Volteo horizontal, Rotación 10%, Zoom 10% y Traslación 10%) activo exclusivamente durante el flujo de entrenamiento.

**Transfer Learning (MobileNetV2):** Reutilización del extractor de características preentrenado en ImageNet. Se integró una capa de upsampling a 96x96 píxeles para satisfacer los requisitos de la arquitectura, congelando la base convolucional (trainable = False) y entrenando únicamente la cabeza de clasificación densa.

## Resultados Principales
Al finalizar el entrenamiento, el resumen final de métricas en el conjunto de validación mostro el siguiente comportamiento:

**Modelo Base (Val Accuracy: 64.16% | Val Loss: 1.0494):** Consigue una convergencia rápida y un desempeño intermedio. Sin embargo, muestra una tendencia al estancamiento debido a la naturaleza estática de los datos de entrada.

**Modelo con Data Augmentation (Val Accuracy: 56.07% | Val Loss: 1.2948):** Registró el rendimiento numérico más bajo en la ventana analizada. Las constantes transformaciones geométricas actuaron como una fuerte penalización de regularización, dificultando la convergencia del optimizador en un límite corto de 10 épocas. Requiere un presupuesto mayor de iteraciones para estabilizar su costo y superar la línea base.

**Modelo Transfer Learning (Val Accuracy: 85.15% | Val Loss: 0.4347):** Dominó de forma absoluta todos los escenarios desde la primera época (78.96% de precisión inicial). La capa de reescalado a 96x96 evitó el colapso espacial de la información, permitiendo que los filtros abstractos preentrenados clasificaran las imágenes con una eficiencia computacional masiva y nulo sobreajuste.

##  Conclusiones Técnicas
 **Eficacia del Aprendizaje por Transferencia:** Se consolidó como la técnica más competitiva y eficiente, demostrando que la reutilización de pesos de ImageNet es notablemente superior al entrenamiento desde cero en imágenes complejas, siempre que se mitigue la restricción dimensional mediante técnicas de upsampling.
 
**Límites de la Regularización:** El aumento de datos reduce el rendimiento a corto plazo al destruir los patrones estáticos que un optimizador básico asimila rápido. Su uso es mandatorio para robustez a largo plazo, pero ineficiente en ventanas de entrenamiento reducidas.


 ## Estructura del repositorio

```
Week9/
├── Actividad_9_Técnicas_de_Data_Augmentation_y_Transfer_Learning_en_imagenes.ipynb
└── README.md
```
##  Cómo ejecutar
1.  Descarga el archivo .ipynb de este repositorio.
2.  Ábrelo en Google Colab.
3.  Ejecuta las celdas en orden: Entorno de Ejecución > Ejecutar todas.
