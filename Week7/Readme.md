# Semana 7 — Convolución 2D con Padding y Stride

## Objetivo
Implementar la operación de convolución 2D desde cero con NumPy, demostrar con evidencia práctica cómo el **padding** y el **stride** modifican las dimensiones y la información preservada en los mapas de características, y aplicar dichos mapas en un clasificador binario orientado a Contact Center.

---

## ¿Qué se comparó?

Se mantuvo el mismo kernel (**Sobel horizontal**) en todas las pruebas, cambiando **una sola variable a la vez**:

| Experimento | Padding | Stride | Dimensión salida (entrada 8×8) |
|:-----------:|:-------:|:------:|:------------------------------:|
| A           | 0       | 1      | 6×6                            |
| B           | 1       | 1      | 8×8                            |
| C           | 1       | 2      | 4×4                            |

- **A vs B** → efecto aislado del padding (solo cambia padding)
- **B vs C** → efecto aislado del stride (solo cambia stride)

---

## Evidencia principal

- `padding=1` preserva las dimensiones originales (8×8 → 8×8) y retiene información de bordes; `padding=0` las reduce (8×8 → 6×6).
- `stride=2` reduce la resolución del mapa a la mitad (8×8 → 4×4) respecto a `stride=1`, con el mismo kernel y padding.
- Clasificador con features convolucionadas: **Accuracy = 87.78%** | **Recall crítico = 88.84%** | **FNR = 11.16%** (≈1 de cada 9 críticos no detectado).

---

## Estructura del repositorio

```
week7/
├── week7_convolucion_padding_stride_CM_contactcenter.ipynb
└── README.md
```

---

## Cómo ejecutar

1. Abrir [Google Colab](https://colab.research.google.com)
2. `Archivo` → `Subir notebook` → seleccionar el archivo `.ipynb`
3. `Entorno de ejecución` → `Ejecutar todo`
4. No requiere instalaciones adicionales — solo librerías estándar de Colab (`numpy`, `matplotlib`, `scikit-learn`)

