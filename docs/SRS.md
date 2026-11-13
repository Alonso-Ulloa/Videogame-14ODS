# Especificación de requisitos de software (SRS)

**Videojuego educativo ODS 14 · Versión 1.0 · 12 de noviembre de 2026**  
Equipo: Daniel Jesus Santana Moreno y Jorge Alonso Ulloa Zapoteco.  
Estado: primera versión para revisar con el equipo. Describe lo que se va a desarrollar; las pruebas todavía no se han realizado.

## 1. Introducción

### 1.1 Propósito
Este documento explica qué debe hacer nuestro videojuego y cómo vamos a comprobar que funciona. Servirá de guía para el equipo y para que el docente pueda revisar el proyecto. Conserva los 40 requisitos funcionales y los 20 no funcionales del documento del 17 de septiembre de 2026. A cada uno se le agregó un título y una forma de comprobarlo. Los nuevos valores propuestos para las pruebas todavía deben revisarse con el equipo.

### 1.2 Alcance
El proyecto es un videojuego educativo para una persona sobre la contaminación del agua y la supervivencia de los peces. El jugador empieza con una especie elegida al azar, ve nacer al pez, busca alimento y evita la basura. A lo largo de la partida cambia de especie hasta llegar al tiburón tigre. También habrá fichas informativas, eventos de pesca y parásitos, una pelea final, tutorial, pausa, sonidos y mensajes educativos. No tendrá multijugador, cuentas ni compras. Los cambios de especie y de hábitat son parte de la ficción del juego: no representan exactamente lo que pasa en la naturaleza ni significan que los peces de agua dulce vivan en el mar.

### 1.3 Glosario
| Término | Definición |
|---|---|
| SRS | Especificación de requisitos de software. |
| RF / RNF | Requisito funcional / no funcional. |
| ODS 14 | Objetivo de Desarrollo Sostenible relativo a océanos, mares y recursos marinos. |
| Vida | Salud del personaje; cero produce el final correspondiente. |
| Crecimiento | Progreso hacia tamaño adulto, independiente de vida. |
| Etapa | Periodo de control de una especie antes de la transición o pelea. |
| Semilla de prueba | Valor que permite repetir decisiones pseudoaleatorias. |
| FPS / ms | Fotogramas por segundo / milisegundos. |
| Gore | Representación explícita de lesiones, vísceras o desmembramiento. |
| Fishtality | Rótulo de cierre de pelea, sin violencia gráfica. |

## 2. Descripción general

### 2.1 Usuarios
El juego está dirigido a estudiantes que sepan usar un teclado; no necesitan conocimientos previos de biología. El equipo de desarrollo ajustará las especies, la dificultad y las reglas. El docente o quien revise el proyecto podrá comprobar el contenido educativo, las fuentes y los requisitos. Estas tareas del equipo no requieren cuentas dentro del juego.

### 2.2 Restricciones
El juego estará en español, se controlará con teclado QWERTY y deberá funcionar con las resoluciones de RNF-10. Se podrá jugar sin internet, no pedirá datos personales y no mostrará violencia gráfica. Los documentos se guardarán en Markdown. Cada requisito conservará su ID para encontrarlo fácilmente en este archivo, en su Issue y en las pruebas.

### 2.3 Supuestos y decisiones pendientes
Todavía falta elegir el motor del juego y la computadora que se usará para medir el rendimiento. Se anotarán su procesador, tarjeta gráfica, memoria RAM, sistema operativo, resolución y versión del juego. También falta acordar las especies intermedias, los tamaños, el daño, los tiempos, las probabilidades y qué ocurre al presionar varias teclas a la vez. Estos valores se guardarán junto con cada versión para poder repetir las pruebas. Los eventos descritos como “raros” deberán ocurrir con menos frecuencia que los riesgos comunes al compararlos durante el mismo periodo. Antes de cerrar RF-19 y RF-21 hay que definir su probabilidad y cada cuánto se decide si ocurren.

Hay que revisar con fuentes confiables la información sobre el parásito Diplostomum. Incluirlo como evento del juego no demuestra que la basura cause esa infección. Si un efecto no está respaldado por las fuentes, se corregirá o se aclarará que es parte de la ficción. Además, cada final deberá explicar su causa real dentro de la partida: una derrota por pelea, pesca o parásito no se presentará como si hubiera sido causada por basura.

El cronograma incluye las semanas de trabajo y los responsables. El periodo indicado empieza en septiembre de 2026 y llega a 2027, con Alonso-Ulloa como responsable de coordinación. Falta acordar el día de inicio y cómo se repartirán las 16 semanas. Los colores del Excel original no se toman como prueba de que el trabajo ya esté terminado.

## 3. Requerimientos

### 3.1 Convenciones y verificación
Cada ficha indica qué debe hacer el juego y cómo comprobarlo. La prioridad **alta** corresponde a lo necesario para jugar o para que la información educativa sea correcta; la **media**, a funciones de apoyo, accesibilidad o eventos adicionales; y la **baja**, a mejoras de comodidad. Todos los requisitos siguen formando parte del proyecto. En cada prueba se anotará la versión del juego y su configuración. Para probar eventos al azar se podrán usar valores de prueba que permitan repetirlos. Los criterios indican lo que deberá cumplirse; no son resultados de pruebas ya realizadas.

### 3.2 Requisitos funcionales

#### RF-01 · Selección aleatoria

- **ID:** RF-01
- **Título:** Selección aleatoria
- **Descripción:** El juego debe elegir automáticamente una especie inicial del catálogo sin permitir selección manual.
- **Prioridad:** Alta
- **Criterio de aceptación:** Al iniciar con semillas de prueba que cubran el catálogo, se obtiene una especie válida y no aparece selector.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-02 · Catálogo inicial

- **ID:** RF-02
- **Título:** Catálogo inicial
- **Descripción:** El catálogo inicial debe incluir Danio rerio y Paracheirodon innesi.
- **Prioridad:** Alta
- **Criterio de aceptación:** Ambas especies existen y pueden obtenerse con semillas controladas.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-03 · Huevo y eclosión

- **ID:** RF-03
- **Título:** Huevo y eclosión
- **Descripción:** Cada partida debe mostrar un huevo y su eclosión antes de habilitar el movimiento.
- **Prioridad:** Alta
- **Criterio de aceptación:** La secuencia registrada es huevo, eclosión y control del pez.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-04 · Tamaño tras transición

- **ID:** RF-04
- **Título:** Tamaño tras transición
- **Descripción:** Cada especie recibida tras una transición debe empezar por debajo de su tamaño adulto máximo.
- **Prioridad:** Alta
- **Criterio de aceptación:** En todas las transiciones, tamaño inicial < tamaño máximo de la especie.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-05 · Ficha de especie

- **ID:** RF-05
- **Título:** Ficha de especie
- **Descripción:** Al comenzar con una especie, el juego debe mostrar su ficha informativa.
- **Prioridad:** Alta
- **Criterio de aceptación:** La ficha incluye nombre común, científico, tamaño promedio, tamaño máximo y hábitat, con unidades y fuente.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-06 · Barra de vida

- **ID:** RF-06
- **Título:** Barra de vida
- **Descripción:** El juego debe mostrar la vida actual del pez.
- **Prioridad:** Alta
- **Criterio de aceptación:** Al aplicar daño o recuperación controlados, la barra coincide con la vida interna y sus límites.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-07 · Indicador de crecimiento

- **ID:** RF-07
- **Título:** Indicador de crecimiento
- **Descripción:** El juego debe mostrar el crecimiento en un indicador separado de la vida.
- **Prioridad:** Alta
- **Criterio de aceptación:** Un cambio de crecimiento actualiza su indicador sin confundirse con el de vida.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-08 · Alimento por etapa

- **ID:** RF-08
- **Título:** Alimento por etapa
- **Descripción:** El juego debe generar alimentos compatibles con la especie y etapa según el catálogo.
- **Prioridad:** Alta
- **Criterio de aceptación:** En cada etapa aparece alimento configurado como válido y el pez puede consumirlo.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-09 · Crecimiento al comer

- **ID:** RF-09
- **Título:** Crecimiento al comer
- **Descripción:** Consumir alimento válido debe aumentar el crecimiento por el valor configurado, hasta el máximo.
- **Prioridad:** Alta
- **Criterio de aceptación:** Con crecimiento g y alimento de valor a, el resultado es min(g+a, máximo).
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-10 · Residuos humanos

- **ID:** RF-10
- **Título:** Residuos humanos
- **Descripción:** El juego debe generar residuos humanos como riesgos del escenario.
- **Prioridad:** Alta
- **Criterio de aceptación:** Aparecen residuos del catálogo, identificados como basura y con colisión activa.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-11 · Daño por basura

- **ID:** RF-11
- **Título:** Daño por basura
- **Descripción:** El contacto con basura debe reducir la vida según el daño configurado sin aumentar el crecimiento.
- **Prioridad:** Alta
- **Criterio de aceptación:** En una colisión aislada, vida final=max(0,vida inicial-daño) y crecimiento final=crecimiento inicial.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-12 · Mensaje sobre residuos

- **ID:** RF-12
- **Título:** Mensaje sobre residuos
- **Descripción:** Una interacción dañina con basura debe mostrar un mensaje educativo sobre su efecto.
- **Prioridad:** Media
- **Criterio de aceptación:** Cada tipo de residuo muestra su mensaje de ingestión, enredo o daño al hábitat sin bloquear el control.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-13 · Final por vida agotada

- **ID:** RF-13
- **Título:** Final por vida agotada
- **Descripción:** Agotar la vida en crecimiento debe activar Bad Ending con explicación de la causa y opción de reinicio.
- **Prioridad:** Alta
- **Criterio de aceptación:** Con vida cero se detiene el crecimiento, aparece el final y se permite reiniciar; si la causa fue basura, se explica la contaminación.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-14 · Madurez

- **ID:** RF-14
- **Título:** Madurez
- **Descripción:** Completar el crecimiento debe finalizar la etapa de crecimiento de la especie.
- **Prioridad:** Alta
- **Criterio de aceptación:** Al alcanzar el máximo, el indicador queda limitado al máximo y se activa una sola transición de etapa.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-15 · Escena de depredación

- **ID:** RF-15
- **Título:** Escena de depredación
- **Descripción:** La madurez de una especie no final debe activar una escena de depredación sin gore.
- **Prioridad:** Alta
- **Criterio de aceptación:** La escena precede al cambio de control y no aparece para el tiburón tigre adulto.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-16 · Control de nueva especie

- **ID:** RF-16
- **Título:** Control de nueva especie
- **Descripción:** Tras la depredación, el juego debe transferir el control a la siguiente especie y reiniciar su crecimiento.
- **Prioridad:** Alta
- **Criterio de aceptación:** La entrada mueve al nuevo pez y su crecimiento parte del valor inicial configurado.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-17 · Secuencia hasta tiburón

- **ID:** RF-17
- **Título:** Secuencia hasta tiburón
- **Descripción:** La progresión debe recorrer especies de tamaño adulto máximo creciente y terminar en Galeocerdo cuvier.
- **Prioridad:** Alta
- **Criterio de aceptación:** El catálogo ordenado cumple tamaños crecientes y la última especie controlable es el tiburón tigre.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-18 · Aviso de simplificación

- **ID:** RF-18
- **Título:** Aviso de simplificación
- **Descripción:** El juego debe advertir cuando una transición cambie de ecosistema o represente una relación no directa.
- **Prioridad:** Media
- **Criterio de aceptación:** Cada transición marcada como simplificada muestra una nota explicativa antes de continuar.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-19 · Evento de anzuelo

- **ID:** RF-19
- **Título:** Evento de anzuelo
- **Descripción:** El anzuelo debe poder activarse con probabilidad configurable solo en especies elegibles pequeñas o medianas.
- **Prioridad:** Media
- **Criterio de aceptación:** Con sorteo controlado se activan y rechazan casos elegibles; nunca se activa en tiburón tigre ni especies excluidas.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-20 · Final secreto

- **ID:** RF-20
- **Título:** Final secreto
- **Descripción:** Caer en el anzuelo debe terminar la partida con Final secreto.
- **Prioridad:** Media
- **Criterio de aceptación:** Se muestra captura y preparación como alimento sin imágenes gráficas, seguida de la pantalla final.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-21 · Evento de parásito

- **ID:** RF-21
- **Título:** Evento de parásito
- **Descripción:** El evento de Diplostomum spathaceum debe poder activarse solo en especies pequeñas elegibles.
- **Prioridad:** Media
- **Criterio de aceptación:** Con sorteo forzado se activa en elegibles y no se activa en ninguna especie excluida.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-22 · Zona de riesgo

- **ID:** RF-22
- **Título:** Zona de riesgo
- **Descripción:** Entrar en una zona marcada sucia debe aumentar la probabilidad configurada del evento sin garantizarlo.
- **Prioridad:** Media
- **Criterio de aceptación:** La configuración cumple 0 <= p_base < p_zona < 1 y sorteos controlados permiten ocurrencia y no ocurrencia dentro de la zona.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-23 · Efecto progresivo

- **ID:** RF-23
- **Título:** Efecto progresivo
- **Descripción:** La infección debe aplicar por etapas un deterioro visual o del control definido en configuración.
- **Prioridad:** Media
- **Criterio de aceptación:** Al avanzar los umbrales temporales se aplican en orden niveles crecientes del efecto elegido.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-24 · Ascenso del pez

- **ID:** RF-24
- **Título:** Ascenso del pez
- **Descripción:** Tras el tiempo configurado de infección, el juego debe desplazar progresivamente al pez hacia la superficie.
- **Prioridad:** Media
- **Criterio de aceptación:** Antes del umbral no se aplica el ascenso; después, la fuerza vertical apunta hacia la superficie.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-25 · Final trágico

- **ID:** RF-25
- **Título:** Final trágico
- **Descripción:** El evento de infección debe terminar con la captura del pez por un ave y Final trágico.
- **Prioridad:** Media
- **Criterio de aceptación:** Al alcanzar el fin del evento se muestra la captura sin gore y finaliza el control de la partida.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-26 · Aclaración del parásito

- **ID:** RF-26
- **Título:** Aclaración del parásito
- **Descripción:** La ficha del evento o el final trágico debe explicar el ciclo del parásito y aclarar que la basura no causa directamente la infección.
- **Prioridad:** Alta
- **Criterio de aceptación:** La pantalla incluye ambas aclaraciones con una referencia científica identificable, revisada antes de la demo.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-27 · Inicio de pelea final

- **ID:** RF-27
- **Título:** Inicio de pelea final
- **Descripción:** Completar el crecimiento del tiburón tigre debe activar la pelea territorial.
- **Prioridad:** Alta
- **Criterio de aceptación:** El máximo de crecimiento cambia una sola vez de exploración a pelea, sin depredación de transición.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-28 · Teclas de pelea

- **ID:** RF-28
- **Título:** Teclas de pelea
- **Descripción:** La pelea debe usar únicamente Q, W, E, R, T, A, S, D, F, G, Z, X, C y V como retos.
- **Prioridad:** Alta
- **Criterio de aceptación:** Todos los retos generados pertenecen al conjunto exacto; teclas ajenas no producen aciertos.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-29 · Reto y temporizador

- **ID:** RF-29
- **Título:** Reto y temporizador
- **Descripción:** Cada acción de pelea debe mostrar una tecla aleatoria válida y una cuenta regresiva.
- **Prioridad:** Alta
- **Criterio de aceptación:** Cada turno tiene tecla y tiempo positivo configurado; al vencer el plazo se registra fallo una sola vez.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-30 · Resolución del reto

- **ID:** RF-30
- **Título:** Resolución del reto
- **Descripción:** La tecla correcta dentro del plazo debe ejecutar el ataque o evasión del turno; error o demora debe aplicar su consecuencia configurada.
- **Prioridad:** Alta
- **Criterio de aceptación:** Se prueban acierto, tecla errónea y expiración, verificando un solo resultado por turno.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-31 · Vida de ambos tiburones

- **ID:** RF-31
- **Título:** Vida de ambos tiburones
- **Descripción:** La pelea debe mostrar por separado la vida del jugador y del rival.
- **Prioridad:** Alta
- **Criterio de aceptación:** Dañar uno actualiza únicamente su barra y mantiene valores entre cero y su máximo.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-32 · Fishtality

- **ID:** RF-32
- **Título:** Fishtality
- **Descripción:** Cuando un tiburón agote su vida, el juego debe mostrar Fishtality antes del resultado.
- **Prioridad:** Alta
- **Criterio de aceptación:** Al llegar a cero se observa Fishtality y después el final correspondiente, sin gore.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-33 · Final bueno

- **ID:** RF-33
- **Título:** Final bueno
- **Descripción:** La victoria del jugador debe mostrar la obtención del territorio y un mensaje ambiental.
- **Prioridad:** Alta
- **Criterio de aceptación:** Con rival sin vida y jugador con vida, aparece el final bueno con ambos textos.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-34 · Reinicio tras derrota

- **ID:** RF-34
- **Título:** Reinicio tras derrota
- **Descripción:** Tras perder la pelea, el jugador debe poder iniciar una partida desde el huevo con nueva selección aleatoria.
- **Prioridad:** Alta
- **Criterio de aceptación:** El reinicio desde la derrota muestra huevo, eclosión y especie válida del catálogo inicial.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-35 · Tutorial

- **ID:** RF-35
- **Título:** Tutorial
- **Descripción:** El juego debe enseñar movimiento, alimentación, basura, vida y crecimiento antes de exponer al jugador a riesgos.
- **Prioridad:** Media
- **Criterio de aceptación:** Un recorrido inicial muestra los cinco temas antes de habilitar daños y eventos peligrosos.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-36 · Pausa y continuación

- **ID:** RF-36
- **Título:** Pausa y continuación
- **Descripción:** En estados interrumpibles, pausar debe congelar movimiento y temporizadores de juego; continuar debe restaurarlos.
- **Prioridad:** Media
- **Criterio de aceptación:** Tras esperar en pausa, posiciones y tiempos son iguales; continuar retoma desde ellos. Las escenas bloqueadas indican que no admiten pausa.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-37 · Reiniciar partida

- **ID:** RF-37
- **Título:** Reiniciar partida
- **Descripción:** El menú de pausa y cada pantalla final deben permitir reiniciar eliminando el progreso de la partida actual.
- **Prioridad:** Media
- **Criterio de aceptación:** Desde cada acceso se restablecen vida, crecimiento, eventos y pelea, y se vuelve a seleccionar especie inicial.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-38 · Dificultad progresiva

- **ID:** RF-38
- **Título:** Dificultad progresiva
- **Descripción:** La configuración debe aumentar al menos un factor de dificultad entre etapas sucesivas.
- **Prioridad:** Media
- **Criterio de aceptación:** La tabla por etapas muestra incremento de velocidad de riesgos, densidad de basura u obstáculos, o reducción de disponibilidad de alimento; se verifica en ejecución.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-39 · Resumen educativo

- **ID:** RF-39
- **Título:** Resumen educativo
- **Descripción:** Cada final debe explicar su causa y relación con el ODS 14, e incluir una acción preventiva contra contaminación.
- **Prioridad:** Alta
- **Criterio de aceptación:** Cada pantalla final contiene causa real, relación educativa y al menos una medida de prevención sin atribuir todos los finales a basura.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RF-40 · Parámetros editables

- **ID:** RF-40
- **Título:** Parámetros editables
- **Descripción:** El equipo debe poder ajustar probabilidades, daño, crecimiento y tiempos sin cambiar la lógica principal.
- **Prioridad:** Alta
- **Criterio de aceptación:** Se modifica un valor de cada grupo en configuración y se observa el efecto tras recargar sin editar lógica.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

### 3.3 Requisitos no funcionales

#### RNF-01 · Rendimiento

- **ID:** RNF-01
- **Título:** Rendimiento
- **Descripción:** El juego debe mantener al menos 30 FPS en el equipo de referencia; 60 FPS es una meta.
- **Prioridad:** Alta
- **Criterio de aceptación:** Capturar tiempos de fotograma durante 10 minutos de juego con escenario de mayor carga; ninguna ventana de un segundo debe promediar menos de 30 FPS.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-02 · Respuesta de entrada

- **ID:** RNF-02
- **Título:** Respuesta de entrada
- **Descripción:** La respuesta visible a una tecla debe ocurrir en menos de 100 ms en el equipo de referencia.
- **Prioridad:** Alta
- **Criterio de aceptación:** Medir 100 entradas válidas distribuidas entre movimiento y pelea; todas deben tener latencia menor a 100 ms.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-03 · Carga

- **ID:** RNF-03
- **Título:** Carga
- **Descripción:** Las escenas principales deben cargar en no más de 5 segundos en el equipo de referencia.
- **Prioridad:** Media
- **Criterio de aceptación:** Medir inicio y fin de carga de cada escena en tres ejecuciones; cada resultado debe ser <= 5 s.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-04 · Estabilidad

- **ID:** RNF-04
- **Título:** Estabilidad
- **Descripción:** El juego debe ejecutar una sesión de 30 minutos sin cierre, bloqueo ni pérdida inesperada de estado.
- **Prioridad:** Alta
- **Criterio de aceptación:** Completar una sesión registrada de 30 minutos con crecimiento, pausa, eventos y pelea sin las fallas indicadas.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-05 · Usabilidad

- **ID:** RNF-05
- **Título:** Usabilidad
- **Descripción:** Un jugador nuevo debe comprender las reglas mediante el tutorial y las señales del juego.
- **Prioridad:** Alta
- **Criterio de aceptación:** Tres personas sin experiencia previa completan el tutorial y demuestran movimiento, alimentación y evasión de basura sin manual ni ayuda verbal.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-06 · Consistencia de interfaz

- **ID:** RNF-06
- **Título:** Consistencia de interfaz
- **Descripción:** La interfaz debe mantener posición y estilo de elementos equivalentes entre escenas.
- **Prioridad:** Media
- **Criterio de aceptación:** Comparar capturas de escenas con la guía de interfaz; barras, mensajes e iconos equivalentes conservan estilo y anclaje.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-07 · Legibilidad

- **ID:** RNF-07
- **Título:** Legibilidad
- **Descripción:** La información importante debe ser legible en 1366×768 y contar con indicaciones adicionales al color.
- **Prioridad:** Alta
- **Criterio de aceptación:** Revisar todas las pantallas a escala 100 %: textos sin recorte ni superposición y estados identificables mediante texto o símbolo.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-08 · Accesibilidad visual

- **ID:** RNF-08
- **Título:** Accesibilidad visual
- **Descripción:** Alimentos y riesgos deben distinguirse mediante forma, símbolo o animación además del color.
- **Prioridad:** Media
- **Criterio de aceptación:** En capturas en escala de grises, cada categoría conserva una señal distinta documentada.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-09 · Teclado

- **ID:** RNF-09
- **Título:** Teclado
- **Descripción:** La pelea debe aceptar el conjunto de RF-28 en teclado QWERTY independientemente de mayúsculas.
- **Prioridad:** Alta
- **Criterio de aceptación:** Probar cada tecla con y sin Bloq Mayús y confirmar el mismo resultado.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-10 · Resolución

- **ID:** RNF-10
- **Título:** Resolución
- **Descripción:** La interfaz debe adaptarse a 1366×768 y 1920×1080.
- **Prioridad:** Alta
- **Criterio de aceptación:** Recorrer todas las pantallas en ambas resoluciones sin controles, barras ni textos importantes cortados.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-11 · Retroalimentación

- **ID:** RNF-11
- **Título:** Retroalimentación
- **Descripción:** Comer, daño, transición, evento raro y acción de pelea deben producir señal visual y, con audio activo, sonora.
- **Prioridad:** Media
- **Criterio de aceptación:** Ejecutar cada evento con audio activo y silenciado; siempre hay señal visual y solo con audio activo hay señal sonora.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-12 · Audio

- **ID:** RNF-12
- **Título:** Audio
- **Descripción:** El jugador debe poder reducir y silenciar música y efectos conservando las señales necesarias.
- **Prioridad:** Baja
- **Criterio de aceptación:** Ajustar ambos canales a nivel intermedio y cero; el volumen cambia y cada evento sigue siendo reconocible visualmente.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-13 · Modularidad

- **ID:** RNF-13
- **Título:** Modularidad
- **Descripción:** Movimiento, crecimiento, daño, eventos, transición y pelea deben estar separados en módulos identificables.
- **Prioridad:** Alta
- **Criterio de aceptación:** Una revisión de código identifica el módulo responsable de cada función y sus interfaces documentadas.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-14 · Configuración centralizada

- **ID:** RNF-14
- **Título:** Configuración centralizada
- **Descripción:** Los datos de especies y parámetros de juego deben estar centralizados en recursos identificables.
- **Prioridad:** Alta
- **Criterio de aceptación:** La revisión localiza los datos listados en RF-40 y los catálogos sin buscar constantes dispersas en lógica.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-15 · Extensibilidad

- **ID:** RNF-15
- **Título:** Extensibilidad
- **Descripción:** Agregar una especie o residuo debe poder hacerse mediante datos e imágenes utilizando las reglas existentes.
- **Prioridad:** Media
- **Criterio de aceptación:** En una rama de prueba se agrega un elemento de cada tipo y se usa en juego sin modificar algoritmos existentes.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-16 · Pruebas repetibles

- **ID:** RNF-16
- **Título:** Pruebas repetibles
- **Descripción:** Cada RF de prioridad alta debe contar con al menos una prueba repetible.
- **Prioridad:** Alta
- **Criterio de aceptación:** La matriz RF-prueba cubre todos los RF de alta prioridad y registra pasos, datos, resultado esperado y evidencia.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-17 · Rigor educativo

- **ID:** RNF-17
- **Título:** Rigor educativo
- **Descripción:** La información biológica y ambiental debe tener fuentes identificables y señalar simplificaciones.
- **Prioridad:** Alta
- **Criterio de aceptación:** Cada ficha y mensaje científico tiene referencia en el catálogo editorial; las transiciones simplificadas y el parásito incluyen sus aclaraciones.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-18 · Contenido escolar

- **ID:** RNF-18
- **Título:** Contenido escolar
- **Descripción:** Depredación, pesca, muerte y Fishtality deben evitar gore.
- **Prioridad:** Alta
- **Criterio de aceptación:** Revisar todas las escenas: ausencia de desmembramientos, vísceras y sangre explícita.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-19 · Privacidad

- **ID:** RNF-19
- **Título:** Privacidad
- **Descripción:** La versión académica debe permitir completar partidas sin cuentas, datos personales ni servicios externos.
- **Prioridad:** Media
- **Criterio de aceptación:** Con red deshabilitada se completa el ciclo de juego; no hay formularios de datos personales, inicio de sesión ni telemetría.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

#### RNF-20 · Español

- **ID:** RNF-20
- **Título:** Español
- **Descripción:** La interfaz académica debe usar español con terminología uniforme.
- **Prioridad:** Alta
- **Criterio de aceptación:** Revisar todas las cadenas contra el glosario y corregir errores; se permiten nombres científicos y los rótulos Bad Ending y Fishtality acompañados de explicación en español.
- **Origen:** mismo ID en Requisitos (1).pdf, 17/09/2026.

### 3.4 Checklist de calidad

Esta lista se usará para revisar cada requisito. Las observaciones se anotarán en su Issue. Una casilla sin marcar significa que falta revisar ese punto; no que el juego haya fallado una prueba.

- [x] **Correcto, comparado con el documento original:** se conservaron los IDs y las funciones; se aclararon las causas de los finales y la diferencia entre vida y crecimiento.
- [ ] **Correcto, revisado por el equipo:** confirmar que lo pedido responde al proyecto y que la información sobre los peces es correcta.
- [x] **No ambiguo, en la redacción:** cada ficha dice qué debe pasar y qué resultado se espera. Los valores que falta acordar están señalados en 2.3.
- [ ] **Completo:** definir las especies, los ajustes de dificultad, la computadora de prueba y qué pasa si se presionan varias teclas a la vez.
- [x] **Consistente:** los requisitos mantienen la misma progresión; comer basura no hace crecer y cada final explica su propia causa.
- [ ] **Factible:** comprobar con un prototipo que el equipo puede cumplir lo pedido con el tiempo y los recursos disponibles.
- [x] **Verificable:** todos los RF y RNF incluyen una forma de comprobarlos.
- [ ] **Pruebas realizadas:** guardar los resultados reales antes de cerrar las Issues.

### 3.5 Trazabilidad y control de cambios
El documento fuente es *Especificación de requisitos funcionales y no funcionales: Videojuego educativo sobre contaminación acuática y supervivencia de especies* (Santana Moreno y Ulloa Zapoteco, 17/09/2026), proporcionado como Requisitos (1).pdf. RF-01 a RF-40 y RNF-01 a RNF-20 se mantienen uno a uno. Se agregaron títulos y criterios operativos; no se renumeraron requisitos. RNF-12 conserva su ID aunque expresa una función de audio por trazabilidad con la clasificación original.

Contaminación: RF-10 a RF-13 y RF-39. Aprendizaje: RF-05, RF-18, RF-26, RF-35 y RNF-17. Progresión: RF-14 a RF-18. Cada Issue debe titularse `RF-XX: título`, enlazar esta ficha y la actividad del cronograma, tener responsable y evidencia antes de cerrarse. Una edición posterior debe registrar versión, motivo e IDs afectados. Véase [investigación y plantilla](investigacion-srs.md).

| Versión | Fecha | Cambio |
|---|---|---|
| 1.0 | 2026-11-12 | Organización SRS, preservación de 60 IDs y criterios de aceptación para revisión. |
| 1.0 (ajuste de redacción) | 2026-11-13 | Lenguaje más sencillo y explicación del checklist, sin cambiar IDs ni criterios de aceptación. |
