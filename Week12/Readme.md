# Semana 12 – Actividad 12: Implementación del Mecanismo de Atención para Series de Tiempo y un Transformer Básico en Google Colab 
---
# 1. Descripción de la actividad
En esta actividad se implementa un mecanismo de atención y una arquitectura tipo Transformer simplificada, aplicadas al análisis de datos secuenciales (series temporales).
El propósito es comprender cómo los mecanismos de atención permiten al modelo asignar diferentes niveles de importancia a los elementos de una secuencia, superando las limitaciones de las redes recurrentes tradicionales en el manejo de dependencias de largo plazo.
La actividad se desarrolla en Google Colab y se presenta como evidencia reproducible en GitHub.
---
# 2. Objetivo de la actividad
Implementar y evaluar modelos basados en atención y Transformer para datos secuenciales, comparando su desempeño con un modelo recurrente tradicional.

# 3. Dataset utilizado
Se utiliza el dataset Jena Climate, correspondiente a una serie temporal multivariante de mediciones meteorológicas reales.

Tipo de problema: Regresión
Variable objetivo: Temperatura del aire (T (degC))
Conjunto de datos secuencial, continuo y de largo plazo

El dataset se descarga automáticamente desde una fuente pública, garantizando reproducibilidad.

# 4. Preparación de los datos
El procesamiento de datos incluye:

Conversión y ordenamiento temporal de la variable de fecha.
Normalización de las variables usando únicamente el conjunto de entrenamiento.
Construcción de ventanas temporales (sliding windows):

Ventanas de entrada con múltiples pasos temporales.
Predicción de un valor futuro de la variable objetivo.

Este enfoque permite transformar la serie temporal en un problema supervisado.

# 5. Modelos implementados
---
5.1 Modelo base – LSTM
Se implementa un modelo LSTM como referencia, utilizando únicamente el estado oculto final de la secuencia para realizar la predicción.
Este modelo sirve como baseline para evaluar el impacto del uso de atención y arquitectura Transformer.

5.2 Modelo LSTM con mecanismo de atención
Se incorpora un mecanismo de atención temporal sobre la salida secuencial del LSTM, permitiendo:

Asignar pesos a cada paso temporal.
Construir un vector de contexto ponderado.
Analizar qué partes de la secuencia influyen más en la predicción.

Este modelo agrega capacidad de interpretación al proceso predictivo.

5.3 Modelo Transformer simplificado
Se implementa una arquitectura tipo Transformer Encoder, compuesta por:

Codificación posicional.
Capas de auto-atención (self-attention).
Redes feed-forward y normalización.
Agregación temporal mediante pooling.

El Transformer permite modelar relaciones entre todos los pasos temporales sin procesamiento secuencial.

# 6. Entrenamiento y evaluación
Todos los modelos se entrenan bajo el mismo esquema de datos y se evalúan sobre un conjunto de prueba independiente.
Métricas utilizadas:

MAE (Mean Absolute Error)
RMSE (Root Mean Squared Error)

Estas métricas permiten una comparación objetiva del desempeño predictivo.

# 7. Interpretación del mecanismo de atención
Para el modelo LSTM con atención se extraen y visualizan los pesos de atención asociados a cada paso temporal.
Esto permite:

Identificar qué momentos de la secuencia son más relevantes.
Analizar la contribución de dependencias recientes y lejanas.
Aportar explicabilidad al modelo.


# 8. Análisis de dependencias de corto y largo plazo
Se evalúa el comportamiento del modelo Transformer utilizando diferentes longitudes de ventana temporal.
Este análisis permite observar:

La estabilidad del modelo ante secuencias largas.
La capacidad de capturar patrones de largo plazo.
La diferencia conceptual frente a redes recurrentes tradicionales.


# 9. Conclusiones
----
El uso de mecanismos de atención mejora el desempeño conceptual del modelo al permitir que la red identifique explícitamente los pasos temporales más relevantes de una secuencia.


El modelo LSTM con atención supera las limitaciones del LSTM tradicional al no depender exclusivamente del estado oculto final, reduciendo la pérdida de información histórica.


La arquitectura Transformer demuestra una mayor capacidad para modelar dependencias de largo plazo, gracias al uso de auto-atención, lo que resulta especialmente útil en series temporales extensas.


Los pesos de atención aportan interpretabilidad al modelo, permitiendo comprender y justificar el proceso de predicción.


Aunque los modelos basados en atención y Transformer presentan mayor complejidad computacional, ofrecen ventajas claras en escenarios con secuencias largas y patrones temporales complejos.

----


10. Evidencia
La implementación completa se encuentra en el notebook:
Actividad_12_Atencion_Transformer_TimeSeries.ipynb
Ejecutable en Google Colab y versionado en GitHub.
