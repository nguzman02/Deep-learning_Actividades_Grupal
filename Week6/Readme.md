
# Actividad 6: Comparación Modelos con Regularización VS Modelo Base

# Objetivo
Aplicar métodos de regularización para mejorar la generalización de una red neuronal, comparando un modelo base (sin regularización) frente a un modelo regularizado.

# Configuración Base
Para este algoritmo se agregaron dos entradas X1, X2, cincuenta capas ocultas H1, H2, H3, H4 ... H50 y una salida. Los datos de entrada y etiquetas se generan una unica vez desde un dataset de numpy.
Este modelo emplea la funcion de activación ReLu, el optimizador Gradiante SGD y los mismos datos de entrada para cada regularización para asi poder realizar una comparacion valida. Para la comparación de entrenamiento de modelos con regularización se eligio L2, Dropout y Early Stopping.

**Esquema para L2:**
Dataset ──► Forward Pass ──► Predicción ──► Cálculo de error (regularización L2) ──► Backpropagation (regularización L2 en gradiantes) ──► Ajuste de pesos con Optimizadores (SGD) ──► Repetir 3000 veces ──► Modelo entrenado

**Esquema para Dropout:**
Dataset ──► Forward Pass (regularización Dropout al 30%) ──► Predicción ──► Cálculo de error ──► Backpropagation (mascara Dropout) ──► Ajuste de pesos con Optimizadores (SGD) ──► Repetir 3000 veces ──► Modelo entrenado

**Esquema para Early Stopping:**
Dataset ──► Forward Pass ──► Predicción ──► Cálculo de error ──► Backpropagation ──► Ajuste de pesos con Optimizadores (SGD) ──► Validar cada 200 epocas si no hay mejoria de perdida (regularización Early Stopping) ──►  Repetir hasta que el entrenamiento mejore ──► Modelo entrenado

# Resultado Principal
De acuerdo a esto y realizando un analisis de comparación se puede concluir que:
- El **modelo base** genera un buen proceso de entrenamiento gracias al optimizador que hace todo lo posible por llevar el error de entreno a cero, pero permite que los pesos de las capas ocultas crezcan libremente corrompiendo la salida final basándose en reglas muy frágiles, asumiendo que el futuro será exactamente igual al pasado memorizado.
- El **uso de regularización L2** reduce el overfitting y hace el entrenamiento más estable, limitando el crecimiento de los pesos y mejorando la capacidad de generalización del modelo. Es ideal cuando se desea todas las variables de entrada aportean un poco de información sin descartar nada. El parámetro λ en la regularización L2 controla la intensidad de la penalización sobre los pesos del modelo. En este codigo se probaron diferentes valores (por ejemplo 0.1, 0.001 y 1) concluyendo que valores excesivos pueden provocar underfitting.
- El **uso de regularización Dropout** permite el "apagado" o "silenciado temporal" del 30% de las capas ocultas en cada iteración de entrenamiento.Esto evita la co-adaptación de neuronas compañeras para arreglar sus errores, forzando a que cada una aprenda por sí misma de manera independiente. En pocas palabras, el modelo es mas redundante y resistente a la pérdida de información.
- El **uso de regularización Early Stopping** no toca los pesos ni apaga neuronas. Permite el proceso de aprendizaje fluya pero observando, cuando se detecta el Overfitting está a punto de comenzar se detiene el proceso de entreno. Esto evita el sesgo comience a convertirse en varianza y que se restaure los pesos de la mejor época pasada. Su mayor ventaja, además de evitar el sobreajuste, es el enorme ahorro de tiempo y recursos computacionales.

***Nota:** Para ajustar a gusto el valor de λ en el codigo verifique la variable "lambda_L2". Y para ajustar el valor de apagado verifique la variable "dropout_rate".*


# Cómo ejecutar el notebook
1. Abrir [Google Colab](https://colab.research.google.com)
2. Ejecutar las celdas en orden -> Entorno de Ejecución --> Ejecutar todas
3. Las gráficas de comparación y la matriz de confusión se generarán automáticamente al final.
