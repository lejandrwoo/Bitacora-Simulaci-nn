## Diseño del sistema
Sistema de agentes autónomos (Particle Life) simulado en p5.js, donde partículas discretas en un espacio bidimensional interactúan mediante fuerzas de atracción, repulsión y dispersión física para generar comportamientos colectivos emergentes.
### Posibilidad
Aquí no hay rutas marcadas ni paredes invisibles. Es como cuando llegas a una plaza gigante en plena fiesta: tienes todo el mapa abierto para arrancar hacia donde te dé la gana, el parche es tuyo.

### Tendencia
Es cuando las ganas de unos pocos se vuelven parche de todos. Si a un color le trama seguir a otro y lo hace una y otra vez, esa pequeña bobada termina armando los desfiles, las serpientes de luces y las coreografías que le dan ritmo a la calle.

### Normalidad
Es el flow suave de la noche. La mayor parte del tiempo, la gente y las luces se mantienen en su órbita, parchando tranquilos en dinámicas que ya todos conocemos y donde se siente la energía bacana pero controlada.

### Excepción
El chispazo que rompe el video. De la nada, dos colores que no pegan se encuentran o explota un petardo festivo, y ¡pum!, las partículas salen disparadas para zonas vacías, descubriendo nuevos rincones del mapa.

### Influencia
La fiesta cambia según quién llegue. Con que solo asome un color nuevo o tú mismo metas la mano, el equilibrio se voltea por completo, cambiando lo que los demás iban a hacer y reconfigurando todo el parche o la fiesta en un segundo. 

## Tipos de partículas
Definí 6 tipos de partículas usando una paleta de colores cálidos para diferenciarlas fácil: Carmesí Intenso ($0$), Lima Cálido ($1$), Naranja Coral ($2$), Amarillo Solar ($3$), Mandarina Intenso ($4$) y Terracota ($5$).
## Cantidad de partículas
Configuré el sistema con $1100$ partículas en total, distribuidas según los porcentajes de población que definí para cada color.
## Matriz de atracción, repulsión o indiferencia
Creé una matriz de $6 \times 6$ (BASE_MATRIX) donde cada celda $M_{ij}$ define qué siente la partícula $i$ por la $j$: valores positivos para atracción, negativos para repulsión y cercanos a cero para indiferencia.
## Intensidad y alcance de cada relación
Ajusté la fuerza global con FORCE_SCALE = 0.55 multiplicada por el valor de la matriz, mientras que el alcance visual de cada especie varía individualmente entre $85\text{px}$ y $120\text{px}$ a través de su rMax.
## Distancias de interacción
Establecí un rango de repulsión fuerte por debajo de $14\text{px}$ (R_MIN) para evitar superposiciones, una zona de atracción/repulsión gradual entre rMin y rMax, y un radio de dispersión inmediata ($16\text{px}$ a $18\text{px}$) al haber un choque cercano entre ciertos colores.
## Fricción y velocidad máxima
Apliqué una fricción constante de $0.86$ para desacelerar el movimiento suavemente y fijé una velocidad máxima base de $4.5$, con multiplicadores especiales para los momentos de evasión o explosión.
## Distribución inicial
Hice que al iniciar, las partículas aparezcan en posiciones totalmente aleatorias en el canvas (random(width), random(height)), asignando la cantidad de cada tipo según los porcentajes definidos.
## Parámetros constantes y variables Constantes: 
El tamaño de las celdas de la grilla espacial (CELL_SIZE = 100), la fuerza de dispersión por colisión y las escalas globales de física.
Variables: La posición $(x, y)$, velocidad $(v_x, v_y)$, aceleración $(a_x, a_y)$ y los temporizadores internos de estado de cada partícula.
## Apariencia e interacción
Diseñé un fondo oscuro con rastro de movimiento (TRAIL_ALPHA = 45) y dibujé las partículas como círculos planos sin borde; además, agregué un reinicio de la simulación al presionar la tecla 'R' o hacer clic en la pantalla.
## INVARIANTES
La fricción del entorno, las distancias de repulsión y la velocidad en la que se alejan o corren por asi decirlo sera la misma.

## VARIABLES
Cambia por asi decirlo la semilla, ya que se puede reiniciar el sistema y cambian de lugar las particulas y a veces se presentan destellos en ciertas interacciones.

## CONDICIONES
### Posición, velocidad y aceleración:
Cada partícula tiene su posición, velocidad y aceleración que cambian en cada frame según la suma de fuerzas que recibe de las demás.

### Varias poblaciones de partículas:
El sistema tiene seis poblaciones cálidas: Carmesí, Lima Cálido, Naranja Coral, Amarillo Solar, Mandarina y Terracota, cada una con un rol y comportamiento distinto en la calle.

### Interacciones dependientes de la distancia:
Todas las fuerzas dependen de qué tan cerca o lejos estén las partículas, usando radios de visión y rangos de impacto físico diferentes.

### Relaciones de atracción, repulsión o indiferencia:
Las partículas pueden buscarse, salir huyendo o ignorarse entre sí según el tipo de color y la distancia en la que se encuentren.

### Al menos una relación asimétrica:
Existe una cadena de persecución unilateral donde un color persigue apasionadamente a otro (como el Morado/Terracota al Mandarina), mientras que el segundo siente terror y huye aceleradamente.

### Variabilidad entre ejecuciones:
Cada simulación empieza con posiciones aleatorias en la pantalla y varía en cada reinicio gracias al pequeño porcentaje de variación aleatoria en las matrices y radios.

### Comportamientos emergentes, no trayectorias predefinidas:
Las aglomeraciones de la multitud, las persecuciones serpentinas y los estallidos de dispersión aparecen solos por las reglas de fuerza, no porque los haya animado cuadro por cuadro.

### Una identidad reconocible entre sus diferentes resultados:
Aunque cada ejecución genera trayectorias únicas, siempre se mantiene la misma esencia visual: el dinamismo, el ritmo de fiesta, la tensión de la multitud y el brillo de la paleta del Barrio Chino.
## PRUEBA Y ERROR:
<img width="1082" height="685" alt="image" src="https://github.com/user-attachments/assets/3efc0256-2b79-452a-a9a1-61a73b70c776" />

<img width="1081" height="682" alt="image" src="https://github.com/user-attachments/assets/8a31f685-3e6b-4013-b6c2-a384be44edd0" />

<img width="1081" height="677" alt="image" src="https://github.com/user-attachments/assets/e4131cb0-10ef-4ea4-a087-28e068a439ae" />

<img width="1082" height="677" alt="image" src="https://github.com/user-attachments/assets/07719df6-d86e-45c0-8999-1483a53da729" />

<img width="1082" height="682" alt="image" src="https://github.com/user-attachments/assets/a9c2625b-08f6-47be-90bf-57bed9b47841" />

## RESULTADO FINAL:


https://github.com/user-attachments/assets/2fea86cb-1d62-4e83-b280-5784298f9679

## LINK PROYECTO:
https://editor.p5js.org/lejandrwoo/sketches/NdWTRj8az
## AUTOEVALUACIÓN

<img width="972" height="687" alt="image" src="https://github.com/user-attachments/assets/1d472667-5c26-4df3-bb14-32bd5cd552bb" />

Las evidencias están arriba ☝️☝️☝️













