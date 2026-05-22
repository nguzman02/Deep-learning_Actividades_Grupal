
### ACTIVIDAD PRESENTADA POR 

* NUBIA GUZMAN 
* JHOAN AVILA 
* DEISY MURCIA
* RUMI TORRES
---
## Actividad 14: Aplicación de los Conceptos de GANs en Google Colab

El siguiente código implementa una arquitectura GANs con un generador y un discriminador para generar imágenes falsas que se asemejan a los dígitos del conjunto de datos MNIST. El generador aprende a crear imágenes de aspecto realista, mientras que el discriminador aprende a distinguir entre imágenes reales y falsas. Durante el entrenamiento, tanto la red del generador como la del discriminador se actualizan iterativamente (7 epocas) hasta que el generador produce imágenes convincentes.

## Objetivo
El objetivo de este proyecto es comprender la lógica de funcionamiento de una GAN a partir de sus dos componentes principales: el generador y el discriminador, así como el proceso de entrenamiento adversarial entre ambos modelos.
  
## Implementación Técnica

**1. Preparación de Datos (Dataset de imagenes)**

Conjunto de datos MNIST para generar imágenes falsas que sean similares a los dígitos.

**2. Ejecución de modelo Generador**

El modelo generador consta de una serie de capas densas y capas convolucionales transpuestas, el cual transforma la entrada de ruido en una imagen de 7x7 con 256 canales, luego aumenta la resolución de esta imagen hasta alcanzar un tamaño de 28x28, que es el tamaño de las imágenes MNIST.

**3. Ejecución de modelo Discriminador**

El modelo discriminador procesa las imágenes de entrada y las submuestrea gradualmente mediante capas convolucionales. La salida es un único valor que representa la probabilidad de que la entrada sea una imagen real (1) o falsa (0).

**4. Entrenamiento adversarial**

Se emplean funciones de pérdida para entrenar tanto al generador como al discriminador. La función de pérdida ayuda a ajustar los pesos de estos modelos durante el entrenamiento para optimizar su rendimiento, esto representa la naturaleza adversaria del entrenamiento de GAN.

**5. Ejecución de entrenamiento**

Se genera ruido aleatorio que se procesa mediante un generador para producir imágenes falsas. El discriminador evalúa tanto las imágenes reales como las falsas generadas por el generador. Se calculan los gradientes del generador y del discriminador en función de sus pérdidas, y sus parámetros se actualizan mediante el optimizador Adam.

**6. Visualización de epocas**

Se llama para cada lote de imágenes reales del conjunto de datos, durante un número específico de épocas. Al finalizar el cargue se imprimen los digitos generados.

##  Conclusiones 

- Al ejecutar 7 épocas, las imágenes pasan de ser simple ruido a manchas grises con formas redondeadas que insinúan la anatomía de los dígitos, aunque aún borrosos e imperfectos.
- El mayor desafío al entrenar GANs es que ambos modelos deben aprender a un ritmo similar. Si el discriminador se vuelve demasiado preciso muy rápido, la función de pérdida devuelve un gradiente cercano a cero, y el generador deja de aprender.
- El generador es ciego a los datos originales. Nunca ve un dígito de MNIST. Toda la información de cómo estructurar los píxeles le llega indirectamente porel proceso de backpropagation, guiado por la probabilidad de error que comete el discriminador.
- En la época 5, el discriminador aún es un clasificador muy rudimentario. Todavía no sabe que un número debe tener bordes nítidos o trazos continuos.
- A medida que avanzan las épocas, el discriminador se vuelve un experto reconociendo bordes, forzando al generador a abandonar promedios borrosos y a comprometerse con trazados definidos y seguros para un solo dígito.


 ## Estructura del repositorio

```
Week14/
├── Actividad14.ipynb
└── README.md
```
##  Cómo ejecutar
1.  Descarga el archivo .ipynb de este repositorio.
2.  Ábrelo en Google Colab.
3.  Ejecuta las celdas en orden: Entorno de Ejecución > Ejecutar todas.
