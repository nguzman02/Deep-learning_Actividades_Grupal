# Actividad 10: Redes neuronales siamesas - Reconocimiento facial

Este proyecto permite la comparación de dos imagenes (rostros) para determinar si se trata de la misma persona o es diferente. Para esto, se ha entrenado una red neuronal siamesa para realizar reconocimiento facial.

## Objetivo
Implementar una red neuronal siamesa orientada al reconocimiento de similitud entre imágenes, aplicada a un caso de reconocimiento facial.

# Dataset
Descarga miles de pares de fotos reales del dataset LFW (Labeled Faces in the Wild).
Estas imagenes vienen en tamaños diferentes, el código las transforma en un escala de grises y a un tamaño exacto de 62x47). Luego, separa el 80% de los pares para que el modelo estudie (Entrenamiento) y el otro 20% de pares es para test (Prueba).
  
## Implementación Técnica

- **Redes Gemelas (Pesos Compartidos):** Definimos una *red_base* a la que se le proporciona una *imagen_A* e *imagen_B* por ella. Matemáticamente, no hay dos redes distintas; es una sola red que procesa primero la foto A y luego la foto B. Al usar la misma red se garantiza que ambas fotos se midan exactamente igual.

- **Espacio Latente (Embeddings):** La red no etiqueta las imagenes. La capa *Flatten* y la capa *Dense(256)* transforma los píxeles de la imagen en un vector matemático de 256 números (previamente la imagen a sido convertida en escala de grises). Un escaneo completo de pixeles.

- **Métrica de Similitud:** Una vez se tiene el escaneo, la capa *distancia_euclidiana* calcula qué tan lejos están esos puntos en un plano matemático de 256 dimensiones.

- **Resultado:** Si la distancia de pixeles es corta (cercano al 0), la capa final *Sigmoid* empuja la probabilidad hacia el 100% (Resultado: Es la misma persona). Si la distancia es grande, la empuja hacia el 0% (Resultado: Son personas diferentes).

## Análisis de desempeño frente a distintos Tipos de Pares
Para este analisis se emplea una matriz de confusión para evaluar los resultados de comparación con un umbral del 52.5% para decidir si hay coincidencia de entradas o no la hay.

 - Los ***Verdaderos Positivos*** y ***Verdaderos Negativos*** presentan numeros ideales para el modelo.
- Sin embargo, los ***Falsos Positivos*** para el umbral escogido tambien presenta un numero considerable. Puede ser dudoso la predicción del modelo, pero si se aumenta el umbral el modelo se vuelve muy exigente y no permitiria coincidencias.

##  Conclusiones 
- Una Red Siamesa no es un clasificador tradicional, es un modelo de entrenamiento para "medir distancias matemáticas" entre rostros (extrayendo características geométricas) en lugar de memorizar identidades.
- Gracias a las capas de Dropout y al Data Augmentation (rotaciones y zoom), se logra evitar el sobreajuste (Overfitting). Esto determina como el modelo se enfrenta a condiciones de iluminación o gestos que nunca vio durante el entrenamiento.
- Un gran dataset es crucial para garantizar una buena comparación de pares, pero el entrenamiento dependera de como se optimice la arquitectura siamesa.
- Para lograr el mejor reconocimiento posible, no se necesita un resolución HD en las entradas de imagenes. Pero sí las imagenes deben tener enfoque, buena iluminación, recorte tipo retrato y sin fondo.


 ## Estructura del repositorio

```
Week10/
├── Actividad10.ipynb
├── rostro_1.png
├── rostro_2.png
├── rostro_3.png
├── rostro_4.png
├── rostro_5.png
├── rostro_6.png
├── rostro_7.png
├── rostro_8.png
├── rostro_9.png
└── README.md
```
##  Cómo ejecutar
1.  Descarga el archivo .ipynb de este repositorio.
2.  Ábrelo en Google Colab.
3.  Ejecuta las celdas en orden: Entorno de Ejecución > Ejecutar todas.


