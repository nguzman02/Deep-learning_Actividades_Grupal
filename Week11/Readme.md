Semana 11 – Actividad 11: Implementación de una Red Neuronal Recurrente (RNN) para la Predicción de Series de Tiempo en Google Colab 

1. Descripción de la actividad
En esta actividad se desarrollo e implementación de una red neuronal recurrente (RNN) aplicada a la predicción de series de tiempo, con el propósito de analizar cómo los modelos de aprendizaje profundo pueden capturar dependencias temporales en los datos. A partir de un conjunto de datos secuencial, se aborda el proceso completo que incluye la preparación de la información, la construcción de secuencias temporales y el entrenamiento del modelo La actividad se desarrolla en Google Colab y se presenta como evidencia reproducible en GitHub.

2. Objetivo de la actividad
Comprender cómo los modelos recurrentes permiten capturar dependencias temporales en los datos, utilizando información pasada para predecir valores futuros


3. Desarrollo
   
3.1 Selección de un conjunto de datos: 
Se fija una semilla para garantizar que los resultados sean siempre reproducibles. A continuación, se genera una colección de datos donde los valores van desde 0 hasta 99 con incrementos de 0.1, creando así una secuencia continua. Sobre estos datos se aplica la función seno (np.sin) para simular un comportamiento ondulatorio, al cual se le añade un pequeño ruido aleatorio con el fin de hacerlo más realista. Posteriormente, se crea una gráfica con los datos iniciales para evidenciar visualmente el comportamiento de la serie generada. Finalmente, esta colección de datos se organiza en forma de tabla, estructurada en una sola columna para facilitar su análisis y procesamiento

3.2 Preparación de los datos
Se implementa una función que transforma la colección de datos en conjuntos de entrada y salida para el modelo. Para ello, se definen los arreglos correspondientes y se utiliza un ciclo que recorre toda la base de datos. En cada iteración, se almacena una secuencia de datos como variables de entrada y, a partir de estas, se asigna el valor siguiente como variable de salida, estableciendo que cada 2 datos se toma el valor a predecir.

3.3 División del dataset: 
Se establece una partición del conjunto de datos en un 80% para entrenamiento y un 20% para evaluación, definiendo explícitamente los índices de corte que delimitan los subconjuntos y garantizan una correcta separación para el entrenamiento y la validación del modelo.

3.4 Modelos implementado
Se importan las herramientas necesarias para construir la red neuronal y utilizar el modelo LSTM. Posteriormente, se define el modelo con una capa de 50 neuronas, empleando la función de activación tanh y considerando las variables de entrada correspondientes a los valores a predecir, para finalmente generar una única salida como resultado de la predicción
3.5 Entrenamiento y evaluación
Se realiza el proceso de entrenamiento del modelo mediante la optimización iterativa de los pesos, minimizando una función de pérdida para cuantificar el error, y se presenta la arquitectura de la red neuronal como parte del análisis del modelo.
El modelo ejecuta un proceso iterativo en el que, a partir de los valores de entrada y salida, realiza predicciones, calcula el error y ajusta los pesos de la red para mejorar su desempeño. Este entrenamiento se lleva a cabo durante 20 iteraciones (épocas), optimizando progresivamente el aprendizaje sobre los datos
Se importa la métrica de evaluación mean squared error (MSE) desde sklearn.metrics, se generan las predicciones del modelo utilizando los datos de prueba (X_test) y posteriormente se calcula el error comparando estas predicciones con los valores reales (y_test). Finalmente, se imprime el valor del error, el cual indica la diferencia promedio entre los valores predichos y los reales, permitiendo evaluar el desempeño del modelo con una margen de error de :
<img width="798" height="393" alt="image" src="https://github.com/user-attachments/assets/6790e99c-f096-4676-8be4-5d36dfe8db67" />

3.6 Análisis del comportamiento del modelo frente a la serie de tiempo
<img width="1058" height="583" alt="image" src="https://github.com/user-attachments/assets/e79c03fb-1b94-4405-befe-d2389e24634f" />
Teniendo en cuenta lo anterior se puede mostrar que logra capturar adecuadamente la tendencia general de la serie, lo que indica que ha aprendido los patrones principales presentes en los datos. Sin embargo, su desempeño puede verse afectado en presencia de cambios bruscos, donde las predicciones tienden a desviarse de los valores reales. Esto se debe a que, aunque las redes LSTM están diseñadas para retener información relevante del pasado y aprovechar las dependencias temporales, pueden tener dificultades para adaptarse rápidamente a variaciones repentinas no recurrentes. Aun así, su capacidad de memoria las convierte en una herramienta efectiva para modelar comportamientos secuenciales y realizar predicciones en series de tiempo.

4. Conclusiones

las redes neuronales recurrentes, especialmente los modelos LSTM, se destacan como una herramienta poderosa para el análisis de datos secuenciales, ya que permiten capturar y modelar dependencias temporales de manera eficiente. Su capacidad para identificar patrones complejos las posiciona por encima de muchos modelos tradicionales en tareas de predicción. No obstante, su desempeño depende en gran medida de un ajuste adecuado de los hiperparámetros, lo que requiere un proceso cuidadoso de configuración y validación para obtener resultados óptimos.


5 Estructura del repositorio
Week11/
├── semana11.ipynb └── README.md

Cómo ejecutar el notebook
1. Descargar el archivo .ipynb en Github.
2. Abrir Google Colab
3. selecciona al opción de archivos, enseguida la opción de subir un nuevo cuaderno, posteriormente clic en subir selecciona el arcivo y deja que cargue.
4. selecciona la opcion ejecutar todas espera que cargue.
