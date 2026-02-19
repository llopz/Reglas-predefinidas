# Visión por Computadora

## 1. ¿Qué es la Visión por Computadora?

La visión por computadora es una rama de la Inteligencia Artificial que
permite a los sistemas interpretar y comprender información visual
proveniente de imágenes o videos.

Su objetivo es que una máquina pueda:

-   Detectar objetos
-   Reconocer patrones
-   Identificar movimientos
-   Extraer información relevante de una escena
-   Tomar decisiones basadas en lo que "ve"

En este proyecto, la visión por computadora es el componente que permite
que el bot interprete el estado del videojuego a partir de capturas de
pantalla, sin acceder directamente al motor interno del juego (enfoque
black-box).

------------------------------------------------------------------------

## 2. Rol dentro del proyecto

En el proyecto "Bot autónomo para videojuego usando Visión por
Computador", la visión por computadora cumple el papel de:

1.  Capturar la pantalla del videojuego en tiempo real.
2.  Procesar la imagen.
3.  Extraer información relevante del entorno.
4.  Convertir la información visual en un estado estructurado que el
    módulo de decisión pueda usar.

Es el equivalente a los "ojos" del sistema autónomo.

------------------------------------------------------------------------

## 3. Pipeline general en el proyecto

El flujo general será:

1.  **Captura de pantalla (Screen Grabbing)**
    -   Obtención continua de frames del juego.
2.  **Preprocesamiento**
    -   Conversión a escala de grises.
    -   Redimensionamiento.
    -   Normalización.
    -   Filtros para reducción de ruido.
3.  **Percepción** Técnicas posibles:
    -   Detección de objetos (enemigos, jugador, obstáculos).
    -   Detección de texto (HUD).
    -   Seguimiento de objetos.
    -   Segmentación.
4.  **Representación del estado**
    -   Posición del jugador.
    -   Posición de enemigos.
    -   Vida / puntaje.
    -   Eventos relevantes.

Este estado será entregado al módulo de decisión (reglas o aprendizaje
por refuerzo).

------------------------------------------------------------------------

## 4. Técnicas relevantes

### 4.1 Procesamiento clásico de imágenes (OpenCV)

-   Detección de bordes (Canny)
-   Umbralización
-   Template Matching
-   Transformaciones geométricas
-   Detección de contornos

------------------------------------------------------------------------

### 4.2 Detección de objetos con Deep Learning

Modelos posibles:

-   YOLO (You Only Look Once)
-   Modelos CNN personalizados
-   Segmentación semántica

Ventajas: - Mayor robustez ante cambios visuales. - Mejor desempeño en
escenarios complejos.

Desventajas: - Mayor costo computacional. - Requiere entrenamiento o
modelos preentrenados.

------------------------------------------------------------------------

### 4.3 Seguimiento de objetos (Tracking)

Permite mantener identificados objetos a través del tiempo.

-   Seguimiento por centroides.
-   Optical Flow.
-   Trackers integrados en OpenCV.

Es clave para: - Estimar movimiento. - Predecir trayectorias. - Tomar
decisiones anticipadas.

------------------------------------------------------------------------

## 5. Retos técnicos en videojuegos

1.  HUD pequeño o poco legible.
2.  Efectos visuales (explosiones, partículas).
3.  Motion blur.
4.  Latencia: la percepción debe ser rápida.
5.  Cambios de resolución o interfaz.

El sistema debe equilibrar precisión y velocidad para cumplir requisitos
de tiempo real.

------------------------------------------------------------------------

## 6. Métricas de evaluación

La visión por computadora puede evaluarse mediante:

-   Precisión de detección (accuracy, precision, recall).
-   Tiempo de procesamiento por frame (FPS).
-   Robustez ante cambios visuales.
-   Estabilidad en seguimiento.

------------------------------------------------------------------------

## 7. Enlaces relevantes

-   https://opencv.org/
-   https://docs.opencv.org/
-   https://pjreddie.com/darknet/yolo/
-   https://paperswithcode.com/task/object-detection
-   https://paperswithcode.com/task/semantic-segmentation

------------------------------------------------------------------------

## 8. Código de prueba (ejemplo básico en Python)

``` python
import cv2
import numpy as np
import pyautogui

# Captura de pantalla
screenshot = pyautogui.screenshot()
frame = np.array(screenshot)

# Convertir de RGB a BGR
frame = cv2.cvtColor(frame, cv2.COLOR_RGB2BGR)

# Escala de grises
gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)

cv2.imshow("Gray Frame", gray)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

------------------------------------------------------------------------

## 9. Relación con el sistema autónomo

Dentro de la arquitectura general:

Visión por Computadora → Representación de Estado → Módulo de Decisión →
Módulo de Acción

Sin una buena interpretación visual, el bot no puede tomar decisiones
correctas.
