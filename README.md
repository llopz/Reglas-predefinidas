# Bot autónomo para videojuego usando Visión por Computador

Proyecto Final -- Ingeniería de Sistemas\
Universidad del Norte\
Periodo 202610

Docente: Margarita Gamarra\
Área: Inteligencia Artificial -- Visión por Computador -- Sistemas
Autónomos -- Ingeniería de Software

------------------------------------------------------------------------

## Introducción

En los videojuegos modernos, la toma de decisiones ocurre en tiempo real
y está basada principalmente en información visual presentada en
pantalla. Automatizar la ejecución de un videojuego sin acceso interno
al motor representa un desafío significativo, ya que el sistema debe
interpretar la escena únicamente a partir de los píxeles capturados.

Este proyecto propone el diseño e implementación de un bot autónomo
capaz de percibir el estado del juego mediante captura de pantalla,
interpretar información relevante usando técnicas de visión por
computador, tomar decisiones automáticamente y ejecutar acciones
mediante simulación de teclado, mouse o control virtual.

El sistema operará bajo un enfoque black-box visual, es decir, sin
acceso a memoria interna ni modificación del cliente del juego.

------------------------------------------------------------------------

## Planteamiento del problema

Muchos videojuegos requieren percepción visual compleja y decisiones en
milisegundos. Automatizar este proceso sin acceso a APIs internas ni
datos estructurados del juego implica resolver múltiples desafíos
técnicos:

-   Extraer información relevante desde la imagen del juego.
-   Construir una representación del estado del entorno.
-   Diseñar una estrategia de decisión eficiente.
-   Garantizar desempeño en tiempo real.

El problema central del proyecto es diseñar un sistema autónomo capaz de
jugar un videojuego en tiempo real utilizando únicamente información
visual capturada desde pantalla y ejecutando acciones mediante
simulación de entradas.

El desempeño del sistema será medido mediante métricas definidas como
puntaje alcanzado, tiempo de supervivencia, nivel completado y tasa de
victoria.

------------------------------------------------------------------------

## Objetivo

Diseñar e implementar un sistema autónomo que juegue un videojuego en
tiempo real usando exclusivamente información visual capturada desde
pantalla y que ejecute acciones mediante simulación de controles,
logrando un desempeño cuantificable según métricas previamente
definidas.

------------------------------------------------------------------------

## Restricciones y supuestos de diseño

### Restricciones técnicas

1.  El sistema no tendrá acceso a la memoria interna del juego.\
2.  No se modificará el cliente del videojuego.\
3.  La interacción será exclusivamente mediante captura de pantalla
    (screen grabbing) y simulación de entradas (teclado, mouse o gamepad
    virtual).\
4.  El sistema debe cumplir restricciones de tiempo real, minimizando la
    latencia entre percepción y acción.\
5.  Se trabajará con un único videojuego para acotar el alcance del
    proyecto.

### Restricciones operativas y éticas

-   No se utilizarán juegos online competitivos con sistemas anti-cheat
    activos.\
-   Se priorizarán juegos offline, open-source o entornos controlados.\
-   Se respetarán los términos de servicio del juego seleccionado.

### Supuestos

-   El videojuego mantiene una estructura visual relativamente
    consistente.\
-   Es posible identificar información relevante como HUD, personaje,
    enemigos u obstáculos mediante técnicas de visión por computador.\
-   Se contará con recursos computacionales suficientes para pruebas y,
    en caso necesario, entrenamiento de modelos de aprendizaje por
    refuerzo.

------------------------------------------------------------------------

## Alcance

### Incluye

1.  Selección del videojuego objetivo y definición de métricas de éxito
    de manera conjunta entre los grupos.\
2.  Desarrollo del módulo de captura y preprocesamiento de imagen.\
3.  Desarrollo del módulo de percepción para extracción del estado del
    entorno a partir de la imagen, utilizando técnicas como OpenCV,
    detección de objetos, seguimiento y, de ser necesario, modelos como
    YOLO o segmentación.\
4.  Desarrollo del módulo de decisión:
    -   Grupo 1: estrategia basada en reglas.
    -   Grupo 2: aprendizaje por refuerzo.\
5.  Desarrollo del módulo de acción para generación de entradas
    simuladas.\
6.  Diseño de arquitectura del sistema.\
7.  Documentación técnica, pruebas experimentales, análisis de
    resultados y validación del desempeño.

### No incluye

-   Soporte para múltiples videojuegos.\
-   Juegos online competitivos con sistemas anti-cheat.\
-   Modificación del cliente del juego.\
-   Acceso a memoria interna del juego.\
-   Generalización automática a otros videojuegos.

------------------------------------------------------------------------

## Riesgos identificados

1.  Ambigüedad visual debido a HUD pequeño, efectos visuales, baja
    iluminación o motion blur.\
2.  Latencia elevada causada por captura, procesamiento e inferencia.\
3.  Alto costo computacional e inestabilidad en el entrenamiento de
    modelos de aprendizaje por refuerzo.\
4.  Baja generalización ante cambios de resolución, escenarios o
    configuraciones visuales.\
5.  Restricciones técnicas o legales del videojuego seleccionado.\
6.  Riesgo de alcance excesivo, mitigado mediante la selección de un
    único objetivo claramente definido (por ejemplo, sobrevivir cierto
    tiempo o completar un nivel específico).

------------------------------------------------------------------------

## Arquitectura general del sistema

El sistema seguirá un pipeline estructurado compuesto por las siguientes
etapas:

1.  Captura de pantalla\
2.  Preprocesamiento de imagen\
3.  Extracción de características\
4.  Construcción del estado del entorno\
5.  Módulo de decisión\
6.  Generación de acción\
7.  Ejecución de entrada simulada

------------------------------------------------------------------------

## Estructura del repositorio

    /diseno
        /tema1
            README.md
        /tema2
            README.md

    README.md
    Ficha_proyecto.md

------------------------------------------------------------------------

## Ficha del proyecto

En este repositorio se incluye la ficha oficial del proyecto:

Título: Bot autónomo para videojuego usando Visión por Computador\
Enfoque: Diseño de solución tecnológica con estándares de ingeniería y
restricciones reales, alineado con lineamientos ABET.
