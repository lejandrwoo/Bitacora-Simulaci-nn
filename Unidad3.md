## INSTRUMENTO VIRTUAL

https://lejandrwoo.github.io/alejosimulacion/

La experiencia está dividida en dos modos principales: el Modo LAB, que despliega la interfaz gráfica con las instrucciones de control y el panel de monitoreo táctico, y el Modo PERFORMANCE, el cual se activa o desactiva con la tecla P.
### Mapa del Sistema
En el archivo src/simulation/parameters.js gestiono el Estado y Parámetros, centralizando todos los uniforms como tiempo, morfologías, colores y fuerzas radiales. En src/simulation/createSimulation.js manejo la Integración e Infraestructura, donde creo las geometrías de buffer y asigno los materiales con shaders.

Para la Fuerza y Dinámica GPU, los archivos src/shaders/vertex.glsl y fragment.glsl, donde proceso las deformaciones y la física directamente en la tarjeta gráfica. En src/main.js controlo el Render y Cámara, encargándome del ciclo de animación, la perspectiva, los controles orbitales y las vistas automáticas.

El control de Controles e Interacción también esta en src/main.js para mapear las combinaciones de teclas y rastrear el cursor con un raycaster en tiempo real. Por último, en src/ui/labPanel.js y src/styles.css esta la Interfaz de Usuario, que despliega el panel flotante con las instrucciones.


### Ficha de Fuerzas y Deformaciones
Para la Repulsión Radial Dinámica, la posición del cursor se proyecta sobre un plano 3D ($z = 0$) calculando un campo de fuerza cuadrático inverso. Al mantener presionada la barra espaciadora (Espacio), se activa una fuerza de $-12.0$ que desplaza las partículas cercanas al cursor, generando una cavidad concéntrica que colapsa suavemente al liberar la tecla.

La Morfogénesis Base (WASD) opera mediante perturbaciones trigonométricas en coordenadas esféricas para alternar entre cuatro comportamientos estructurales: Dalia Organoide en W, Rosa/Crisálida helicoidal en A, Panal en S y Prisma Flora en D.

Los Modificadores Orgánicos (Q y E) introducen distorsiones superficiales sumando ruido de alta frecuencia para espinas con la tecla Q, o impulsos sinusoidales globales con la tecla E. 

Al accionar combinaciones simultáneas (W+Q, A+E, etc.), el sistema amplifica los parámetros generando estados híbridos.

La Escultura e Inercia Axial (I, K, J, L) permite aplicar deformaciones en el eje Y y rotaciones de torsión espacial. Con el fin de simular un comportamiento viscoelástico, se integró una amortiguación inercial que retorna progresivamente la estructura a su forma base al soltar los mandos.


### Registro de Pruebas


https://github.com/user-attachments/assets/2bcbb69c-7ce9-450d-8688-34c636f4bd37

<img width="1918" height="897" alt="pp" src="https://github.com/user-attachments/assets/8a354f09-a6cc-4caf-b76c-8aaa163dcd3f" />
<img width="1919" height="902" alt="image" src="https://github.com/user-attachments/assets/a308744e-4c1e-406f-92ac-825255c04767" />
<img width="1918" height="893" alt="Captura de pantalla 2026-08-21 082418" src="https://github.com/user-attachments/assets/f80b3787-bec1-496f-9045-cc36faa7e2f1" 

.



https://github.com/user-attachments/assets/3d7dcd01-ffa3-4324-80c7-61a9d45a05fd



.
### Score Visual:


### Bitacora IA
<img width="640" height="640" alt="descarga (3)" src="https://github.com/user-attachments/assets/22cf1d2a-f0ce-4d13-8446-d2f606501705" />
<img width="736" height="1104" alt="Thermal Orchid Aesthetic 🌺 Infrared Floral Art" src="https://github.com/user-attachments/assets/b5085970-672a-451d-8916-4e25ac3f431e" />
<img width="586" height="628" alt="descarga (4)" src="https://github.com/user-attachments/assets/0de89222-f486-45c4-bc5c-00cb72309ec6" />
<img width="736" height="736" alt="descarga (5)" src="https://github.com/user-attachments/assets/f598869d-18b0-432e-9628-13c0aee00eb5" />

### Autoevaluación
<img width="1028" height="620" alt="image" src="https://github.com/user-attachments/assets/abb7c141-9577-45d3-839c-257b8bf48e2f" />

## NOTA: 4,2

