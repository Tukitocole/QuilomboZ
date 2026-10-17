# Quilombo Z: fases de estado y entrega

Proyecto GDevelop 5 (probado con la versión 5.6.283). Toda la lógica va en **eventos nativos**
(condiciones y acciones), sin bloques de JavaScript.

Estados: ✅ Hecha · 🧪 Entregada, en prueba del equipo · ⏳ En curso · ⬜ Pendiente · ⚠️ Bloqueada

| Fase | Estado | Entregable | Criterio de "lista" |
|---|---|---|---|
| 0 · Base técnica | ✅ Hecha | Formato de proyecto relevado y validador con libGD funcionando | El `game.json` carga en el motor sin errores |
| 1 · Núcleo jugable | 🧪 En prueba | Escenas `Menu`, `Nivel1_Retiro`, `Tienda`, `Victoria` y `Derrota`; variables globales; Lionel con movimiento en 4 direcciones (WASD y flechas) y disparo al mouse con munición; mapa de Retiro con paredes; cámara que sigue al jugador | Se abre en GDevelop, se mueve y dispara dentro del mapa |
| 2 · Enemigos y supervivencia | 🧪 En prueba | Zombies Chorro, Jubilado e Hincha con pathfinding; daño con cooldown de 1 s; spawn progresivo; HUD (vida, balas, kills, plata); munición, mate, botiquín y billetes para juntar | Se puede morir, matar zombies y juntar recursos |
| 3 · Objetivo, plata y pantallas | ⬜ Pendiente | Zona segura (Kiosco de Don Ramón); tienda mínima (chaleco, mochila, escopeta) con inflación; Victoria y Derrota con reintento y penalización de plata; carteles, frases de Lionel y radio | Se juega de principio a fin y se vuelve a jugar desde ambas pantallas |
| 4 · Pulido y entrega | ⬜ Pendiente | Música y efectos; parpadeo al recibir daño; pausa con Esc; balance; exportación web; guía de pruebas con terceros | Cumple los criterios de aceptación del MVP (sección 7 del documento de diseño) |

## Cuadro de avance

| Fase | Estado | Se agregó | Se mejoró | Se modificó |
|---|---|---|---|---|
| 0 · Base técnica | ✅ Hecha | Validador con libGD (el motor del editor), exportador HTML5 para probar en el navegador, plan de fases y tablero de Trello | — | — |
| 1 · Núcleo jugable | 🧪 En prueba | 5 escenas, variables globales, movimiento WASD/flechas, disparo al mouse con munición, mapa de Retiro con obstáculos, cámara, HUD de vida y balas | — | En la fase 2: Lionel pasó a los sprites del equipo y el arma empuñada es un objeto aparte que apunta al mouse |
| 2 · Enemigos y supervivencia | 🧪 En prueba | Zombies Chorro, Jubilado e Hincha con búsqueda de caminos; daño con 1 s de espera; robo del Chorro; muerte y paso a Derrota; aparición progresiva fuera de cámara; billetes que sueltan los zombies; caja de balas, mate, botiquín, billetes y dólar blue en el mapa; HUD con barra de vida, kills y plata | Disparo: la bala sale pegada al cuerpo para pegarle también a un zombie que está encima; Lionel y el arma miran hacia donde se apunta | Sprites provisorios de Lionel y zombies reemplazados por los del equipo (`prota`, `zgenerico`, botiquín); objeto de munición renombrado `CajaMunicion` (chocaba con la variable `Municion`) |
| 3 · Objetivo, plata y pantallas | ⬜ Pendiente | — | — | — |
| 4 · Pulido y entrega | ⬜ Pendiente | — | — | — |

## Correspondencia con Trello ("Quilombo Z – MVP")

Cada fase equivale a un sprint del documento de diseño y agrupa tarjetas que ya existen:

| Fase | Tarjetas |
|---|---|
| 1 | Movimiento del jugador · Sistema de disparo · Mapa base: Estación Retiro y tren Sarmiento · Sprites de Lionel, Chorro, Jubilado y bala (provisorios) |
| 2 | Zombie Chorro · Zombie Jubilado · Sistema de vida y daño · Contador de zombies eliminados · Sistema de plata (pesos) · Ubicación de enemigos, objetos y billetes · HUD · Sprites de billetes y dólar blue |
| 3 | Evento de victoria · Escena Tienda mínima (3 productos) · Variables globales de mejoras entre niveles · Cambio de nivel y reinicio con penalización · Zona segura y tienda al final de cada nivel · Pantallas de inicio, victoria y derrota · Interfaz de la tienda (kiosco) · Textos y carteles argentinos |
| 4 | Sonido y música · Balance de dificultad, precios e inflación · Exportación y presentación · Pruebas con terceros |

Fuera de estas fases: "Nivel 2: Obelisco y 9 de Julio" (el documento lo pone como opcional
para el MVP) y "Documento de diseño" (lo mantiene Felipe).

Regla del tablero: nada pasa a "Hecho" sin que lo pruebe otro integrante. Por eso, al cerrar
una fase, sus tarjetas van a **"En prueba"** con un comentario que dice qué se implementó.

## Cómo se cierra cada fase

1. Validación con el motor de GDevelop (libGD): instrucciones y expresiones sin errores.
2. Exportación de una vista previa HTML y prueba en el navegador.
3. Actualización de este archivo: estado, qué se entregó y qué no se pudo verificar.
4. Commit de la fase.

## Registro

### Fase 0 · Base técnica (✅)
- Leído el documento de diseño (MVP, sprints, nombres de escenas, objetos y variables).
- Relevado el formato del proyecto de GDevelop 5.6.283 y los nombres exactos de las
  instrucciones (movimiento top-down, pathfinding, variables, temporizadores, texto).
- Validador armado sobre la librería del propio editor (libGD).
- Assets provisorios: los genero yo y Santiago los reemplaza después sin tocar los eventos.

### Fase 1 · Núcleo jugable (🧪 en prueba)

Entregado:
- `game.json` con 5 escenas: `Menu`, `Nivel1_Retiro`, `Tienda`, `Victoria` y `Derrota`
  (las tres últimas son provisorias, con navegación).
- Variables globales del documento de diseño (secciones 10 y 20). El menú las reinicia en
  cada partida nueva.
- Lionel: movimiento top-down en 4 direcciones (flechas por defecto + WASD con "simular
  tecla"), animación según la dirección y pausada cuando está quieto, máscara de colisión
  en los pies.
- Disparo: clic (mantenido o corto), toque o Espacio; cadencia de 0,3 s; la bala sale hacia
  el mouse y descuenta munición; sin balas aparece "Uh, no, me quedé sin balas". La bala se
  borra al chocar con un obstáculo o al salir de pantalla.
- Mapa de Retiro (2560×768): kiosco de inicio, molinetes con tres pasos, dos formaciones
  del Sarmiento con huecos entre vagones, columnas, salida a la calle con autos y el Kiosco
  de Don Ramón (zona segura, sin evento todavía).
- Cámara que sigue a Lionel y se limita al mapa; HUD de vida y balas en su propia capa.
- Sprites provisorios 32×32 (incluye Chorro y Jubilado para la fase 2).

Verificado:
- Validador libGD: 111 instrucciones, 0 errores, 0 avisos de instrucciones obsoletas.
  Se comprobó que el validador detecta errores reales sembrando dos a propósito.
- Exportación HTML5 con el exportador oficial y prueba en el navegador, avanzando el
  juego a 60 fps simulados:
  - D/A mueven ~103 px por segundo (con aceleración) y cambian la animación.
  - W/S frenan contra las paredes del kiosco (pies en y=288 y y=512).
  - Un clic corto dispara 1 vez, mantener 1 s dispara 4 veces, Espacio dispara 1 vez.
  - La dirección de la bala coincide con el mouse (error de 1°).
  - Las balas se borran contra la pared; sin balas aparece la frase y se oculta a los 2 s.
  - La cámara queda en el límite del mapa (2240, 588) y el HUD sigue fijo.
  - Enter navega Menú → Nivel, Tienda → Victoria, Victoria/Derrota → Menú.

No verificado:
- No lo abrí en la interfaz del editor de GDevelop. El archivo pasó por la misma librería
  del editor (carga y guardado sin diferencias), pero conviene abrirlo una vez y probar ▶.
- El sonido no forma parte de esta fase.

### Fase 2 · Enemigos y supervivencia (🧪 en prueba)

Entregado:
- Zombies `ZombieChorro`, `ZombieJubilado` y `ZombieHincha` (grupo `Zombies`) con los números
  del documento: daño 10 / 8 / 12, vida de 1 / 3 / 2 balas, velocidad alta / baja / media y
  $1.000 / $500 / $1.500 de plata. Los tres usan el sprite `zgenerico` del equipo con un
  tinte por tipo hasta que haya uno para cada uno.
- Persecución con el comportamiento de búsqueda de caminos (pathfinding): los obstáculos del
  mapa tienen el comportamiento de obstáculo y los zombies van por los huecos entre vagones.
  Recalculan el camino cada 0,4 s. Los que están lejos esperan hasta ver a Lionel (450 px)
  o hasta que les disparen.
- Daño a Lionel con 1 s de espera entre golpes; el Chorro además roba 2 balas y $500. Con la
  vida en 0 se pasa a `Derrota`.
- Bala contra zombie: resta `Bala.Danio + DanioExtra` y el zombie parpadea en rojo. Al morir
  suma a `Kills`, suelta un billete con su plata y, con 30 % de chance, una caja de balas.
- Aparición progresiva desde 15 `PuntoAparicion` (invisibles), siempre fuera de cámara (entre
  380 y 900 px de Lionel). Arranca cada 4 s y baja 0,15 s por aparición hasta 1,5 s. El tope
  de zombies vivos es 4 + 1 cada 500 px que avanza Lionel. Tipos: 45 % Chorro, 35 % Jubilado
  y 20 % Hincha (en manada de 3).
- Objetos repartidos por el mapa: 4 cajas de balas (+6, hasta el máximo), 2 mates (+15),
  2 botiquines (+60), 4 billetes ($1.000 a $5.000) y un dólar blue escondido ($15.000).
- HUD: barra de vida verde, amarilla o roja según lo que queda, balas, zombies eliminados y
  plata con punto de miles (`$ 4.500`).
- Sprites del equipo: Lionel sin manos (`prota.png`) con el arma empuñada como objeto `Arma`
  que gira sobre la mano hacia el mouse y se da vuelta al apuntar a la izquierda. Arma
  inicial: pistola provisoria con la paleta del equipo. La Uzi y la AK-47 ya están cargadas
  como animaciones de `Arma` para la tienda de la fase 3.

Verificado:
- Validador libGD: 228 instrucciones, 0 errores y 0 avisos. Se volvió a comprobar con dos
  errores sembrados a propósito (los detecta). El validador tenía un error propio con los
  eventos "para cada objeto", que la fase 1 no usaba: quedó corregido.
- Exportación HTML5 probada en el navegador avanzando el juego a 60 fps simulados:
  - Un Chorro a ~300 px detecta a Lionel y lo persigue; un Jubilado lejano sigue quieto.
  - Un Chorro del andén de arriba cruza las vías por el hueco entre dos vagones y llega en
    4,9 s sin tocar ningún obstáculo.
  - El Jubilado pega 8 de vida cada 61 cuadros (1 s): 100 → 92 → 84 → 76 → 68 → 60 → 52.
  - El Chorro saca 10 de vida, 2 balas y $500 ("¡Ey, pibe! Me afanó balas y plata").
  - Balas para matar: Chorro 1, Hincha 2 y Jubilado 3, aun con el zombie encima de Lionel.
  - El billete que suelta el zombie suma su valor; el HUD muestra `$ 1.000`, `$ 17.500`.
  - Mate +15, botiquín y caja de balas respetan los topes (vida 100, balas 24); dólar blue
    +$15.000.
  - Un minuto de aparición: 17 apariciones, con el tiempo entre ellas bajando de 3,9 s a
    1,6 s; los zombies nacen entre 420 y 602 px de Lionel; el Hincha sale de a 3.
  - Con la vida en 0 se pasa a `Derrota`.
  - Captura con zombies tintados, arma apuntando, HUD y frase en pantalla.

Cambios durante las pruebas:
- El comportamiento de caminos lleva el punto de origen del objeto al destino. Con el origen
  en la esquina, los zombies quedaban corridos y pegaban una sola vez. Ahora el origen está en
  el centro del sprite y el golpe se mide por distancia entre centros (menos de 24 px).
- La bala salía 16 px adelante y no le pegaba a un zombie pegado a Lionel: ahora sale a 6 px.

No verificado:
- No lo abrí en la interfaz del editor de GDevelop: conviene abrirlo y probar ▶ antes de
  aprobar la fase.
- Los clics del navegador automatizado no llegan bien al juego, así que el disparo se probó
  con Espacio y el apuntado moviendo el mouse desde el motor.
- Los sprites de Lionel y del zombie tienen un solo cuadro: no hay animación de caminata hasta
  que el equipo pase los cuadros que faltan.
