# Quilombo Z: fases de estado y entrega

Proyecto GDevelop 5 (probado con la versión 5.6.283). Toda la lógica va en **eventos nativos**
(condiciones y acciones), sin bloques de JavaScript.

Estados: ✅ Hecha · 🧪 Entregada, en prueba del equipo · ⏳ En curso · ⬜ Pendiente · ⚠️ Bloqueada

| Fase | Estado | Entregable | Criterio de "lista" |
|---|---|---|---|
| 0 · Base técnica | ✅ Hecha | Formato de proyecto relevado y validador con libGD funcionando | El `game.json` carga en el motor sin errores |
| 1 · Núcleo jugable | 🧪 En prueba | Escenas `Menu`, `Nivel1_Retiro`, `Tienda`, `Victoria` y `Derrota`; variables globales; Lionel con movimiento en 4 direcciones (WASD y flechas) y disparo al mouse con munición; mapa de Retiro con paredes; cámara que sigue al jugador | Se abre en GDevelop, se mueve y dispara dentro del mapa |
| 2 · Enemigos y supervivencia | 🧪 En prueba | Zombies Chorro, Jubilado e Hincha con pathfinding; daño con cooldown de 1 s; spawn progresivo; HUD (vida, balas, kills, plata); munición, mate, botiquín y billetes para juntar | Se puede morir, matar zombies y juntar recursos |
| 3 · Objetivo, plata y pantallas | 🧪 En prueba | Zona segura (Kiosco de Don Ramón); tienda mínima (chaleco, mochila, escopeta) con inflación; Victoria y Derrota con reintento y penalización de plata; carteles, frases de Lionel y radio | Se juega de principio a fin y se vuelve a jugar desde ambas pantallas |
| 4 · Pulido y entrega | 🧪 En prueba | Música y efectos; parpadeo al recibir daño; pausa con Esc; balance; exportación web; guía de pruebas con terceros | Cumple los criterios de aceptación del MVP (sección 7 del documento de diseño) |
| 5 · Nivel 2: Obelisco y 9 de Julio | 🧪 En prueba | Escena `Nivel2_Obelisco`; zombies Delivery y Colectivero; sánguche de milanesa; flujo Nivel 1 → tienda → Nivel 2 → tienda → Victoria; jugabilidad compartida en eventos externos | Se juegan los dos niveles seguidos y se vuelve a jugar desde Victoria y Derrota |
| 6 · Nivel 3: Cabildo y Plaza de Mayo | 🧪 En prueba | Escena del Cabildo y la Plaza de Mayo; zombie Trapito; Hinchas en manada; cierre en el subsuelo del Cabildo | Se juegan los tres niveles seguidos |
| 7 · Hinchas, dificultad y mapas | ⏳ En curso | Camisetas de clubes (colores y diseños, sin escudos ni nombres) para los Hinchas; más dificultad y más zombies; mapas más detallados y a escala realista | Se nota más el ambiente argentino y el juego es más exigente |
| 8 · Nivel 4: Casa Rosada | ⬜ Pendiente | Patio, escaleras y balcón; jefe Zombie Político (promesas como proyectiles) | Se derrota al jefe y se sale por la puerta de atrás |

## Cuadro de avance

| Fase | Sprint | Estado | Implementado | Mejorado / modificado | Falta |
|---|---|---|---|---|---|
| 0 · Base técnica | 0 | ✅ Hecha | Validador con libGD (el motor del editor), exportador HTML5, plan de fases y tablero de Trello | Fase 2: el validador maneja bien los eventos "para cada objeto" | — |
| 1 · Núcleo jugable | 1 | 🧪 En prueba | 5 escenas, variables globales, movimiento WASD/flechas, disparo al mouse con munición, mapa con obstáculos, cámara | Fase 2: sprites del equipo. Fase 3: corregido el reinicio de `TieneEscopeta`. Fase 4: mapa de Retiro rediseñado | Aprobación de otro integrante en Trello; primeros sonidos |
| 2 · Enemigos y supervivencia | 2 | 🧪 En prueba | Zombies Chorro, Jubilado e Hincha con búsqueda de caminos; daño con 1 s de espera; robo del Chorro; derrota; aparición progresiva; billetes y objetos; HUD | Fase 3: caminata en 4 direcciones. Fase 4: la parte de abajo de la calle quedaba encerrada para los zombies (autos reubicados) | Aprobación en Trello; sprites de Chorro y Jubilado; efectos de sonido; Nivel 2 (opcional) |
| 3 · Objetivo, plata y pantallas | 3 | 🧪 En prueba | Zona segura → tienda con inflación; Victoria y Derrota con reintento y penalización; inventario 1-2-3; caminata; radio, carteles y frases | Fase 4: decoración argentina del mapa (pendiente de este sprint) | Aprobación en Trello; arte final de pantallas y tienda; música |
| 4 · Pulido y entrega | 4 | 🧪 En prueba | Lionel con camiseta celeste y blanca; Retiro según fotos (trenes blancos y azules, andenes con borde amarillo y franja táctil, vías con topes, columnas de hierro, sombra de los arcos, piedra clara, puestos, bancos, cestos, faroles, carteles, bandera, banderines, grafitis, publicidades parodia, perro y palomas); pausa con Esc; parpadeo al recibir daño; avisos flotantes al juntar; exportación web; `DEMO.md` y `PRUEBAS.md` | Autos de la calle reubicados; arte viejo del mapa eliminado | Balance con las pruebas de terceros; sonido y música (archivos del equipo); publicar la versión web |
| 5 · Nivel 2: Obelisco y 9 de Julio | 2-3 (opcional del MVP) | 🧪 En prueba | Escena `Nivel2_Obelisco` (dos manos de carriles, sendas, "mar de colectivos" de colores genéricos, autos, canteros con árboles, Metrobus, plaza del Obelisco, edificios, puesto de choripán, parada blindada como zona segura); Zombie Delivery (carga en línea recta) y Zombie Colectivero (6 tiros, pega 20); sánguche de milanesa (+30); flujo entre niveles; eventos externos "Jugabilidad" | Plan B de persecución (si no hay camino y Lionel está cerca, el zombie va derecho); el Obelisco y los árboles ya no dejan escondites; validador revisa los eventos externos en cada nivel; identificador del proyecto completado (la compilación en la nube daba error 400) | Sprites definitivos de Delivery y Colectivero; balance del nivel |
| 6 · Nivel 3: Cabildo y Plaza de Mayo | Versión 2 | 🧪 En prueba | Escena `Nivel3_Cabildo` (Casa Rosada, plaza con palmeras, canteros y palomas, Pirámide de Mayo, mástil, vallas con pasos, carpas, arcadas del Cabildo con su torre y la bajada al subsuelo como zona segura); Zombie Trapito (pide una moneda: con E se le pagan $500; si no, a los 3 s se enoja); Hinchas en manada de 4; flujo de tres niveles | Las herramientas pasaron a GDevelop 5.6.284 (la exportación web estaba rota por el desfase); un zombie con daño 0 ya no hace parpadear a Lionel | Sprite definitivo del Trapito |

**Fase siguiente: 7 · Hinchas, dificultad y mapas.** Camisetas de clubes de la Liga Profesional
(colores y diseños, sin escudos ni nombres, como pide el documento) para los Hinchas, más dificultad
y más zombies, y los tres mapas más detallados y a escala realista. Después, **8 · Nivel 4: Casa
Rosada** con el jefe Zombie Político.

## Sprints del documento y fases

| Sprint (documento) | Fase | Cumplido | Falta |
|---|---|---|---|
| 0 · Preparación | 0 | Proyecto en GDevelop, repo con `assets/`, sprites de 32×32, Trello, convención de nombres | Paleta y estilo los define el arte del equipo |
| 1 · Núcleo jugable | 1 | Movimiento, disparo, mapa con colisiones, escenas y variables globales | Primeros sonidos |
| 2 · Enemigos y supervivencia | 2 | Persecución, daño, vida, muerte, aparición, ubicación de zombies y objetos, HUD, coleccionables, plata | Sprites finales de Chorro y Jubilado; efectos de sonido; Nivel 2 (opcional) |
| 3 · Objetivo y pantallas | 3 y 4 | Victoria, reinicio, zona segura, tienda mínima, pantallas, textos, carteles, radio, decoración argentina | Arte final de pantallas; música ambiental; segundo nivel |
| 4 · Pulido y pruebas | 4 | Pausa, parpadeo, avisos al juntar, exportación web, guion de demo, guía de pruebas | Pruebas con 3 personas de afuera; balance; sonidos al juntar; publicar |

## Criterios del MVP (documento, sección 7)

| # | Criterio | Estado |
|---|---|---|
| 1 | Mapa chico: kiosco, andenes de Retiro y zona segura | ✅ |
| 2 | Movimiento en 4 direcciones y disparo | ✅ |
| 3 | Chorro y Jubilado (y el Hincha) | ✅ |
| 4 | Vida, daño y munición con HUD | ✅ |
| 5 | Munición y mate o botiquín | ✅ |
| 6 | Colisiones con paredes, autos y obstáculos | ✅ |
| 7 | Contador de zombies | ✅ |
| 8 | Pantallas de inicio, victoria y derrota | ✅ (arte provisorio) |
| 9 | Música y 4 o 5 efectos | ❌ Esperando los archivos del equipo |
| 10 | Victoria al llegar a la zona segura | ✅ |
| — | Ambientación argentina | ✅ |
| — | Probado por 3 personas de afuera | ❌ Guía lista en `PRUEBAS.md` |

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

### Fase 3 · Objetivo, plata y pantallas (🧪 en prueba)

Entregado:
- Caminata en 4 direcciones con 4 cuadros por dirección: Lionel con arma (cuerpo sin manos),
  Lionel con los puños (cuerpo con manos que se balancean) y los zombies. Son provisorios,
  derivados de `prota.png`, `prota1.png` y `zgenerico.png`: `assets/jugador/lionel_<dir>_<n>.png`,
  `lionel_manos_<dir>_<n>.png` y `assets/zombies/zombie_<dir>_<n>.png`.
- Lionel mira hacia donde apunta el mouse y los pies se mueven solo cuando camina. Los zombies
  miran hacia donde caminan.
- Inventario (`SlotActual`, `ArmaActual`, `ArmaPrincipal`): 1 = puños (golpe de 0,5 de daño,
  alcance ~29 px), 2 = pistola, 3 = arma principal (la escopeta, si se compró). Casilleros
  con íconos abajo a la derecha.
- Con arma: el arma empuñada gira sobre la mano y la otra mano flota (sostiene el caño de la
  escopeta). Mirando hacia arriba, el arma queda detrás del cuerpo.
- Zona segura: entrar al Kiosco de Don Ramón lleva a la `Tienda`.
- Tienda: chaleco (+20 de vida máxima, $3.000), mochila (+6 de capacidad, $2.000) y escopeta
  ($15.000), multiplicados por la inflación (×1,2 por nivel). Las mejoras suben 50 % por compra,
  hasta el nivel 5. Mensajes "No te alcanza, pibe", "Ya la tenés, pibe" y cartel de Don Ramón.
  Se compra con 1, 2, 3 o clic; "Seguir viaje" sube la inflación y el nivel y pasa a `Victoria`.
- Escopeta: tres perdigones a −10°, 0° y +10°, cadencia 0,7 s, una bala por tiro.
- `Victoria`: resumen (zombies y plata), "Jugar de nuevo" (partida nueva) y "Menú".
- `Derrota`: pierde la mitad de la plata juntada en el nivel y vuelve a las balas y kills del
  inicio del nivel; "Reintentar" (conserva lo comprado) y "Menú".
- Radio al empezar el nivel (7 s), 4 carteles del documento y frases de Lionel ("¡Qué bajón!"
  con poca vida, "¡Uh, se vino la hinchada!", sin balas: "¡A las piñas!").

Verificado:
- Validador libGD: 552 instrucciones en 5 escenas, 0 errores, 0 avisos.
- Exportación HTML5 en el navegador: animación por puntería y movimiento; teclas 1-2-3; piñas
  (Chorro en 2 golpes, alcance a 28 px); animaciones de zombie; zona segura → Tienda; las tres
  compras, "No te alcanza", "Ya la tenés", compra con clic; precios con punto de miles e
  inflación; "Seguir viaje" (inflación 1,2, nivel 2); escopeta (3 perdigones, 1 bala, cadencia);
  Derrota (perdió $3.000 de $6.000 juntados); Reintentar conserva la escopeta; "Jugar de nuevo"
  reinicia todo; capturas del nivel, la tienda y la derrota.
- Probado por el equipo en el editor de GDevelop con ▶ (2026-10-17).

Errores encontrados y corregidos en las pruebas:
- El puño no alcanzaba a un zombie encimado: el área del golpe pasó a 28×28 y más cerca.
- "Crear objeto" suma el objeto nuevo a los elegidos y los perdigones se sumaban las fuerzas.
  Cada perdigón va ahora en su propio subevento.
- El atajo de variables booleanas ponía siempre verdadero (venía de la fase 1).
- Íconos del inventario de distinto tamaño: ahora todos miden 32×32.

### Fase 4 · Pulido y entrega (🧪 en prueba)

Entregado:
- Lionel con camiseta celeste y blanca a rayas (sin escudo), short negro y medias blancas, en
  todos los cuadros de caminata (con arma y con los puños).
- Estación Retiro rediseñada a partir de fotos de la estación: formaciones blancas con franjas
  azules (cabina, vagones y cabina; sin logos), andenes de hormigón con borde amarillo y franja
  de baldosas con relieve, vías con durmientes de hormigón y paragolpes (Retiro es terminal),
  columnas de hierro remachadas, sombra de los arcos del techo de hierro y vidrio, paredes de
  piedra clara (los kioscos siguen de ladrillo), dos puestos de diarios (obstáculos), bancos,
  cestos azules, faroles, carteles azules "ESTACIÓN RETIRO" y "ANDÉN 1/2/3", bandera argentina
  colgada en el hall, banderines celestes y blancos en la calle, grafitis, publicidades parodia,
  bolsas de basura, un perro callejero y palomas. La línea sigue siendo el Sarmiento (decisión
  del equipo).
- Pausa con Esc: escala de tiempo 0 y capa "PAUSA" con SEGUIR (Esc, Enter o clic) y MENÚ (M o
  clic). Toda la lógica del juego corre solo sin pausa.
- Parpadeo en rojo de Lionel durante 0,6 s al recibir un golpe.
- Avisos flotantes al juntar objetos ("+6 balas", "+$1000"...), que suben y se desvanecen.
- Exportación web en `export/web` (fuera de git), [DEMO.md](DEMO.md) con el guion de la demo y
  [PRUEBAS.md](PRUEBAS.md) con la guía de pruebas con terceros.

Verificado:
- Validador libGD: 606 instrucciones, 0 errores, 0 avisos.
- Exportación HTML5 en el navegador: pausa (Lionel y temporizadores frenados; se retoma con Esc
  y con clic), parpadeo (opacidad 90/255 y vuelve a normal), aviso flotante (sube, se desvanece
  y se borra), cruces entre andenes por los huecos de los trenes sin tocar obstáculos, rodeo de
  los puestos de diarios, los 15 puntos de aparición con camino hasta el kiosco de inicio.
- Probado por el equipo en el editor de GDevelop con ▶ (2026-10-17).

Errores encontrados y corregidos:
- Los zombies no encontraban camino desde la parte de abajo de la calle (venía de la fase 2):
  la búsqueda de caminos necesita pasillos de más de ~60 px y el auto rojo dejaba 32. Se
  reubicaron los autos.

No hecho / no verificado:
- Balance de números: se mantienen los del documento hasta tener las pruebas con terceros.
- Sonido y música: esperan los archivos del equipo.
- No se pudo comprobar si `export/web` abre con doble clic (las exportaciones web de GDevelop
  suelen necesitar un servidor). Para la demo se recomienda el ▶ del editor.

### Fase 5 · Nivel 2: el Obelisco y la 9 de Julio (🧪 en prueba)

Entregado:
- Escena `Nivel2_Obelisco` (sección 16): se cruza la 9 de Julio de oeste a este. Vereda con
  edificios porteños y el puesto de choripán ("CHORI $2.500 (AYER $2.000)"), dos manos de cinco
  carriles con líneas y sendas peatonales, "mar de colectivos" (colores genéricos, sin líneas ni
  empresas reales) y autos atravesados, canteros con árboles, Metrobus, la plaza del Obelisco y,
  del otro lado, la parada blindada con bolsas de arena (zona segura).
- Zombie Delivery: en bici, no busca caminos; cada 2,2 s apunta a Lionel y carga en línea recta a
  ~230 px/s durante 1,3 s. Zombie Colectivero: chaleco y gorra, 30 % más grande, vida 6, pega 20,
  muy lento. En el nivel 2 aparecen 30 % Chorro, 20 % Jubilado, 35 % Delivery y 15 % Colectivero.
- Sánguche de milanesa (+30 de vida, sección 5) junto al puesto de choripán.
- Flujo: Nivel 1 → Kiosco de Don Ramón → Nivel 2 (inflación ×1,2) → "Parada blindada" (la tienda
  cambia de nombre) → Victoria. "Reintentar" vuelve al nivel donde se murió.
- Eventos externos "Jugabilidad": todo lo común (movimiento, inventario, armas, persecución, daño,
  objetos, zona segura, cámara, HUD, pausa, feedback) en una sola hoja que cada nivel incluye con
  un evento de enlace. Cada nivel tiene solo lo propio (aparición, Delivery, objetos especiales).
- Plan B de persecución: si un zombie en alerta no encuentra camino y Lionel está a menos de
  160 px, va derecho hacia él (antes, pegarse a un obstáculo dejaba al zombie quieto).

Verificado:
- Validador libGD: 1038 instrucciones (la jugabilidad compartida se valida dentro de cada nivel),
  0 errores. Error sembrado en la hoja compartida: lo detecta solo en el nivel donde falla.
- Navegador: flujo completo Menú → Nivel 1 → tienda → Nivel 2 → parada → Victoria; los 13 puntos
  de aparición con camino al inicio y a la parada (también el Colectivero); con Lionel pegado a un
  colectivo el zombie llega y pega (plan B); Delivery carga a ~230 px/s; Colectivero muere con 6
  tiros, pega 20 y suelta $3.000; milanesa +30; Derrota en el nivel 2 → "Reintentar" vuelve al
  nivel 2. Regresión del nivel 1 con los mismos números de antes.
- Probado por el equipo en el editor de GDevelop (2026-10-26).

Errores encontrados y corregidos:
- La búsqueda de caminos toma el rectángulo entero de cada obstáculo: el Obelisco y las copas de
  los árboles dejaban escondites. El Obelisco tiene ahora una base invisible como obstáculo y los
  árboles son decorado (la copa se dibuja por encima de Lionel).
- `projectUuid` vacío: la compilación en la nube de GDevelop respondía error 400.

### Fase 6 · Nivel 3: el Cabildo y la Plaza de Mayo (🧪 en prueba)

Entregado:
- Escena `Nivel3_Cabildo` (sección 16): se cruza la Plaza de Mayo desde la Casa Rosada hasta el
  Cabildo. Plaza con canteros, palmeras y muchas palomas, la Pirámide de Mayo (solo frena su base),
  el mástil con la bandera, dos líneas de vallas con pasos, carpas, las arcadas del Cabildo (pilares
  con arcos de 80 px), la torre con el reloj y la bajada al subsuelo como zona segura.
- Zombie Trapito (sección 4): chaleco verde flúor y trapo rojo. Cuida los pasos de las vallas y
  pide una moneda; tranquilo no hace daño. Con E se le pagan $500 y se corre; si Lionel se queda
  3 s cerca sin pagar, o si le pegan, se enoja: persigue y pega 12.
- Hinchas en manada de 4. Aparición del nivel 3: 25 % Chorro, 15 % Jubilado, 40 % Hinchas,
  10 % Delivery y 10 % Colectivero.
- Flujo de tres niveles: Nivel 2 → parada blindada → Nivel 3 → "Subsuelo del Cabildo" → Victoria.
  "Reintentar" vuelve al nivel donde se murió.

Verificado:
- Validador libGD 5.6.284: 1518 instrucciones (la jugabilidad compartida en los tres niveles),
  0 errores.
- Navegador: Trapito (pide, se le paga y se corre; sin pagar se enoja a los 3 s y pega 12; si le
  disparan se enoja); los 13 puntos de aparición con camino al inicio y al subsuelo; camino de punta
  a punta a través de vallas y arcadas; manada de 4 Hinchas; subsuelo → tienda → Victoria; Derrota
  → "Reintentar" vuelve al nivel 3; regresión del nivel 1.
- Probado por el equipo en el editor de GDevelop (2026-10-26).

Errores encontrados y corregidos:
- GDevelop se actualizó a 5.6.284 y el exportador de las herramientas seguía en 5.6.283: la
  exportación web no arrancaba (faltaba `named-easings-manager.js`). Se actualizó la librería.
- Los pilares del Cabildo quedaban pegados (sin pasos): ahora dejan arcos de 80 px.
- El Trapito no se corría después de cobrar (el destino quedaba contra la valla).
