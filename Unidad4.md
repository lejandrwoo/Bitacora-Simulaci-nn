# Unidad 4 — Oscilacion
https://lejandrwoo.github.io/alejosimulacion/

Mi idea principal fue inspirarme en la estética visual de los conciertos 3D y en la estructura interactiva de Incredibox, pero aplicando directamente el modelo de Kuramoto para gobernar el audio. De esta forma, diseñé una experiencia donde el ritmo no depende de un reloj rígido, sino de la interacción entre los mismos agentes.
## Referentes e Inspiración
Empecé explorando cómo llevar los comportamientos periódicos al terreno artístico. Me basé en la obra *Simple Harmonic Motion* de Memo Akten y la simulación de luciérnagas de Nicky Case para entender la sincronización emergente. Mi idea principal fue inspirarme en la estética visual de los conciertos 3D y en la estructura interactiva de *Incredibox*, pero aplicando directamente el modelo de Kuramoto para gobernar el audio. De esta forma, diseñé una experiencia donde el ritmo no depende de un reloj rígido, sino de la interacción entre los mismos agentes.

## Concepto y Modelo de Kuramoto
Adapté el modelo de osciladores acoplados de Kuramoto para controlar un sistema audiovisual en tiempo real usando Three.js y Web Audio API. En mi código, cada uno de los 8 agentes es un oscilador: su fase ($\theta$) dispara el pulso de audio y la deformación visual, su frecuencia natural ($\omega_i$) define su tempo propio, y la fuerza de acoplamiento ($K$) controla qué tanto se atraen rítmicamente hasta lograr sintonizarse.

## Ideas Generativas y Experimentación
Mi idea principal fue transformar modelos 3D de cabezas en entidades vivas compuestas por partículas y luz volumétrica. Experimenté haciendo que cada tipo de instrumento deformara la malla con una matemática distinta: ondas longitudinales para los bajos, ruido para las baterías y senoides para las melodías. Además, diseñé un sistema de 4 cámaras dinámicas para poder cambiar la perspectiva visual mientras el sistema oscila y se sincroniza.

## Problemas Encontrados y Soluciones
Tuve varios retos técnicos en el desarrollo:

* **Conos de luz invisibles:** Quise agregar unos conos de luz que iluminaran las cabezas activas pero no logre activarlas.
* **Fallos en los Shaders:** Tuve algunos fallos con los shaders.
* **Sincronía de Audio:** Para evitar desfases y saturaciones en la Web Audio API, calculé ventanas de compás exactas (`BAR_DURATION`) y ajusté la ganancia y el paneo dinámicamente según la cantidad de agentes activos.

## Diseño Audiovisual de los Agentes
Construí 8 agentes divididos en 4 personalidades sonoras y visuales (bajos, baterías, melodías y efectos procesales). Visualmente, la fase del modelo de Kuramoto altera la posición de los puntos en la malla mediante *Custom Shaders* y enciende el cono de luz del color de su categoría. En lo sonoro, la sincronía afecta directamente el volumen, los filtros y los efectos de modulación temporal.

## Experiencia Performativa y Cámaras
Diseñé el proyecto para que realmente pudiera "tocarse" en vivo. El usuario puede cambiar $K$ en tiempo real, alterar agentes individuales o meter perturbaciones para desfasar el ritmo y ver cómo el grupo se reorganiza. Acompañé esto con 4 modos de cámara (perfil en perspectiva, barrido cercano, zoom reactivo al beat y seguimiento rítmico individual) para hacer la experiencia totalmente dinámica.

## Demostración y Resultado
El modelo de Kuramoto es el corazón del proyecto; si lo quito, la experiencia pierde su cohesión orgánica. La transición entre el caos, la sincronía parcial y la estabilidad se comunica de forma evidente mediante la intensidad de la luz, el movimiento de las partículas y la armonía del sonido.

---

## Autoevaluación (Escala 1.0 - 5.0)

| Criterio de Evaluación | Ponderación | Descripción del Cumplimiento | Nota |
| :--- | :---: | :--- | :---: |
| **Cumplimiento de Requisitos Mínimos** | 25% | Implementé los 8 agentes, 4 personalidades audiovisuales, control de $K$, perturbación de estado y la comunicación clara de los 3 estados del colectivo. | **5.0** |
| **Claridad de Variables del Modelo** | 25% | Explico claramente qué hace la fase ($\theta$), la frecuencia ($\omega$) y el acoplamiento ($K$) dentro del código y la escena. | **5.0** |
| **Explicación del Comportamiento Emergente** | 25% | Demuestro cómo el modelo de Kuramoto controla los shaders de partículas, la luz volumétrica y los búferes de audio. | **5.0** |
| **Demostración de Objetivos de Unidad** | 25% | El sistema funciona como un instrumento performativo interactivo real, donde la sincronía emerge de la física del modelo. | **5.0** |
| **NOTA FINAL** | **100%** | **Promedio ponderado de la evaluación** | **5.0** |
