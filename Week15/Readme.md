
### ACTIVIDAD PRESENTADA POR 

* NUBIA GUZMAN 
* JOHAN AVILA 
* DEISY MURCIA
* RUMI TORRES

## Actividad 15: Trabajo Cooperativo sobre Data Journey, Acceso y Manipulación de Datos, Monitoreo y Logging, y Model Serving con Weights & Biases 
**Descripción del Data Journey:** 
los datos utilizados provienen de un dataset publico denominadoa Breast Cancer Wisconsin que contienen diferentes variables como se evidenia en la imagen anexada, ademas estos estan incluidos dentro de una libreria denominda Scikitlearn; los datos se acceden mediante la función load_breast_cancer(), que permite cargar automáticamente el dataset dentro del entorno de trabajo sin necesidad de descargar archivos externos; se preparan mediante la conversion de la base de datos en un DataFrame como se visualiza en la siguiente linea df = pd.DataFrame(data.data, columns=data.feature_names) y se usan dentro del modelo para las variables de entrada y salida permitiendo entrenar el modelo y posteriormente ser evaluado.
<img width="918" height="574" alt="image" src="https://github.com/user-attachments/assets/df41bcd4-b68e-4f6c-97ef-8fca3df27ada" />
<img width="1013" height="298" alt="image" src="https://github.com/user-attachments/assets/76896221-50c3-4025-a51a-b4bcd8e5213a" />


**Acceso y manipulación de datos:**
El dataset fue cargado desde una fuente pública utilizando la función load_breast_cancer() de Scikit-learn. Luego, los datos se organizaron en un DataFrame con Pandas para facilitar su manipulación. Posteriormente, se realizó la separación de variables de entrada (X) y variable objetivo (y), además de dividir los datos en entrenamiento y prueba utilizando train_test_split(). Finalmente, se aplicó un escalamiento con StandardScaler() para mejorar el rendimiento del modelo de Machine Learning.
<img width="748" height="469" alt="image" src="https://github.com/user-attachments/assets/92623f72-fa3d-44e1-8572-e3830c3f8f65" />


**Implementación o reutilización de un modelo:**
Se utilizo el modelo de Regresión Logística se empleó para clasificar datos relacionados con cáncer de mama, permitiendo identificar la categoría correspondiente según las características médicas del dataset. Para implementar el modelo, primero se prepararon y transformaron los datos mediante procesos de limpieza, separación de variables y escalamiento. Posteriormente, el algoritmo fue entrenado utilizando los datos de entrenamiento, donde aprendió patrones y relaciones presentes en la información. Después del entrenamiento, el modelo realizó predicciones utilizando los datos de prueba y su rendimiento fue evaluado mediante métricas como Accuracy, Precision, Recall y F1-score.
<img width="759" height="562" alt="image" src="https://github.com/user-attachments/assets/79974a3b-099a-4918-a4d7-5791c9190c68" />
<img width="774" height="134" alt="image" src="https://github.com/user-attachments/assets/b08c17d5-7099-48a5-abb0-27e45667a468" />

**Monitoreo y logging:**
 Se utilizo Weights & Biases para realizar el monitoreo y registro de métricas del entrenamiento del modelo. Esta plataforma permitió almacenar y visualizar de forma organizada métricas importantes como Accuracy, Precision, Recall y F1-score, facilitando el seguimiento del rendimiento del algoritmo durante el proceso.
 <img width="716" height="470" alt="image" src="https://github.com/user-attachments/assets/41281ebf-1385-4fe4-b8bf-fb82cc84127e" />

 
**Análisis de métricas:** 
Las métricas como Accuracy, Precision, Recall y F1-score permitieron evaluar el rendimiento del modelo durante las predicciones realizadas sobre los datos de prueba. Gracias a estas métricas se pudo identificar qué tan preciso fue el algoritmo al clasificar los casos correctamente y qué tan eficiente fue reduciendo errores en las predicciones. Cuando estos valores son altos, significa que el modelo tiene una buena capacidad para reconocer patrones y generar resultados más confiables.
Además, la matriz de confusión ayudó a analizar con mayor detalle el comportamiento del modelo, mostrando cuántos casos fueron clasificados correctamente y cuántos presentaron errores. Esto permitió identificar los verdaderos positivos, verdaderos negativos, falsos positivos y falsos negativos teniendo un resultados de 41 casos negativos y 70 casos positivos, lo que evidencia una alta capacidad para identificar correctamente ambas clases. Además, solamente se presentaron 2 falsos positivos y 1 falso negativo, indicando que el modelo cometió muy pocos errores durante las predicciones.
<img width="454" height="233" alt="image" src="https://github.com/user-attachments/assets/c95aa6c5-dfe1-4811-9381-617da008867e" />

**Aproximación a Model Serving:**
Una alternativapara utilizar el modelo creado es mediante la creacion de una aplicación web, donde los usuarios ingresen información desde una interfaz gráfica y el sistema genere predicciones automáticamente, teniendo en cuenta los datos de entrenamiento y prueba del modelo.

**Conclusiones técnicas:**
<img width="741" height="513" alt="image" src="https://github.com/user-attachments/assets/c09ae538-89c0-47a0-aa5a-2e0680c018fc" />

Teniendo en cuenta la gráfica, se puede visualizar que las métricas como Accuracy, Precision, Recall y F1-score reflejaron valores bastante altos, cercanos a 1, lo que permitió confirmar la eficiencia y el buen rendimiento del modelo durante el proceso de evaluación. Esto demuestra que el algoritmo logró clasificar correctamente la mayoría de los datos y reducir significativamente los errores en las predicciones. Además, la gran cantidad y calidad de los datos del dataset permitió que el modelo identificara patrones importantes dentro de la información, facilitando una mejor clasificación y generando resultados más precisos y confiables. La gráfica también evidencia que el Recall obtuvo uno de los valores más altos, indicando que el modelo tuvo una excelente capacidad para detectar correctamente los casos positivos analizados.


