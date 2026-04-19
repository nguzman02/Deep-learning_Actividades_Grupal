**Semana 5: -Cambio de hiperparámetros**


**Objetivo**
Evidenciar el comportamiento que se tiene en cuenta al cambiar los hiperparámetros en las tecnicas de optimización en las redes neuronales.

**Comparaciones**
Modificaciones en loss:
1. loss="binary_crossentropy"
<img width="776" height="547" alt="image" src="https://github.com/user-attachments/assets/64180c06-a440-44d5-8ba2-60861fa75634" />

2. loss="mean_squared_error"
<img width="725" height="539" alt="image" src="https://github.com/user-attachments/assets/a76cc44f-9c31-4afd-bb7a-ae2e38ac1429" />
**Conclusiones**
Se puede evidenciar que en la función de error la mas efectiva es la mean_squared_error debido a que inicia con una tasa de error menor a 0.2 en la etapa de entrenamiento y en la de validación con un valor de  menor a 0.127 en cambio de la otra función inicia con una tasa de error de 0.7 para la etapa de entrenamiento y un 0.58 para la etapa de validación.

Modificaciones en metricas:
1. metrics=["accuracy"]
<img width="734" height="565" alt="image" src="https://github.com/user-attachments/assets/7ae77af1-3f73-453b-be66-5eac4ee6d931" />
2. metrics=["accuracy",keras.metrics.Precision()]
<img width="818" height="543" alt="image" src="https://github.com/user-attachments/assets/ffe77f83-6c2f-465f-a5fc-462b0f52fc72" />
3.metrics=["accuracy",keras.metrics.Recall()]
   <img width="392" height="308" alt="image" src="https://github.com/user-attachments/assets/bb563f8d-c162-461e-84de-e9c1af7d9bb9" />
4.metrics=["accuracy",keras.metrics.Precision(), keras.metrics.Recall()])
<img width="741" height="549" alt="image" src="https://github.com/user-attachments/assets/b235a18b-a158-4e0d-8912-5cf8d12c45f4" />

**Conclusiones**
La función en donde se evidencia mayor acercabilidad a la presición de prendizaje es la de keras.metrics.Precision debido a que el valor de inicio para la etapa de entrenamiento inicia 0.84 y la de de validación 0.91 en cambio las otras funciones tienen un rango de 0.4 hasta el 0.81 tasa de aprendizaje.

**Resultado principal**
Según los resultados anteriores se puede evidenciar que una de las funciones mas efectivas para el error mean_squared_error y para las metricas keras.metrics.Precision es bueno utilizarlos debido a que permite evaluar un mejor desempeño del modelo y disminuye el indice la tasa de error y es mas efectivo la tasa de aprendizaje.

**Pasos para ejecutar el notebook**
1. Descargar el archivo .ipynb en Github.
2. Abrir [Google Colab](https://colab.research.google.com)
3. seleeciona al opción de archivos, enseguida la opción  de subir un nuevo cuaderno, posteriormente cic en subir selecciona el arcivo y deja que cargue.
4. selecciona la opcion ejecutar todas espera que cargue.
