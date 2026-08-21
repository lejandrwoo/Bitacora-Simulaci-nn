## INSTRUMENTO VIRTUAL

La experiencia está dividida en dos modos principales: el Modo LAB, que despliega la interfaz gráfica con las instrucciones de control y el panel de monitoreo táctico, y el Modo PERFORMANCE, el cual se activa o desactiva con la tecla P.
### Mapa del Sistema
En el archivo src/simulation/parameters.js gestiono el Estado y Parámetros, centralizando todos los uniforms como tiempo, morfologías, colores y fuerzas radiales. En src/simulation/createSimulation.js manejo la Integración e Infraestructura, donde creo las geometrías de buffer y asigno los materiales con shaders.

Para la Fuerza y Dinámica GPU, los archivos src/shaders/vertex.glsl y fragment.glsl, donde proceso las deformaciones y la física directamente en la tarjeta gráfica. En src/main.js controlo el Render y Cámara, encargándome del ciclo de animación, la perspectiva, los controles orbitales y las vistas automáticas.

El control de Controles e Interacción también esta en src/main.js para mapear las combinaciones de teclas y rastrear el cursor con un raycaster en tiempo real. Por último, en src/ui/labPanel.js y src/styles.css esta la Interfaz de Usuario, que despliega el panel flotante con las instrucciones.
