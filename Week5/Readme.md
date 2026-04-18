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
Se puede evidenciar que en la función de error la mas efectiva es la mean_squared_error debido a que inicia con una tasa de error menor a 

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


**Resultado principal**


**Pasos para ejecutar el notebook**
