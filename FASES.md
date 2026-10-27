# Quilombo Z: fases de estado y entrega

Proyecto GDevelop 5 (probado con la versión 5.6.284). Toda la lógica va en **eventos nativos**
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
| 7 · Hinchas, dificultad y mapas | 🧪 En prueba | Camisetas de clubes (colores y diseños, sin escudos ni nombres) para los Hinchas; más dificultad y más zombies; mapas más detallados y a escala realista | Se nota más el ambiente argentino y el juego es más exigente |
| 8 · Nivel 4: Casa Rosada | 🧪 En prueba | Patio, escaleras y balcón; jefe Zombie Político (promesas como proyectiles) | Se derrota al jefe y se sale por la puerta de atrás |
| 9 · Sonido, plata y ambiente | 🧪 En prueba | Sonidos y música del equipo; plata en billetes argentinos según el documento; cuerpos y sangre; zombies gore; Lionel demacrado según su vida; escenarios post-apocalípticos (El Eternauta, The Last of Us) | Se escucha el juego y se siente el apocalipsis porteño |
| 10 · Nivel 5: el Monumental | ⏳ En curso | Tribunas, túnel y cancha; jefe final Gordo Barra con bombo; oleada final | Se aguanta la oleada, se vence al jefe y se entra al túnel del Club Último Refugio |

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
| 7 · Hinchas, dificultad y mapas | Versión 2 | 🧪 En prueba | 17 camisetas de clubes de la Liga Profesional (colores y diseños, sin escudos ni nombres) al azar en cada Hincha; más dificultad (zombies más rápidos, aparición más seguida, más zombies a la vez, alerta a 550 px); los tres mapas rehechos a escala (1 m ≈ 12 px): Retiro con hall de mármol, boleterías, reloj, molinetes, dos naves con 8 andenes, trenes de 7 vagones y Torre Monumental; 9 de Julio con 7 carriles por mano, Metrobus, Obelisco alto, taxis y marquesinas de Corrientes; Plaza de Mayo con Catedral, Cabildo con arcadas, Monumento a Belgrano, pañuelos alrededor de la Pirámide y la reja de la Casa Rosada | Un tren de Retiro cerraba el andén de abajo (corrido 10 m) | Arte definitivo de los mapas del equipo |
| 8 · Nivel 4: Casa Rosada | Versión 2 | 🧪 En prueba | Escena `Nivel4_CasaRosada` a escala (Balcarce 50, hall, Patio de las Palmeras con fuente, palmeras y galería, escaleras Italia y Francia, Salón Blanco con arañas y sillas, balcón sobre Balcarce, Galería de los Bustos, despacho, puerta de Paseo Colón y helipuerto); jefe Zombie Político (40 de vida, promesas como proyectiles, abanico y custodia de Colectiveros en la segunda mitad, $20.000); flujo de cuatro niveles | Barra del jefe corrida para no tapar la vida; piso en los vanos de las puertas | Sprite definitivo del Político |
| 9 · Sonido, plata y ambiente | 4 + Versión 2 | 🧪 En prueba | Los 11 sonidos del equipo (música del menú y de los niveles, disparos, recarga, recolectar, caja registradora, botones y gruñidos); plata en billetes argentinos ($500, $1.000, $2.000, $10.000 y $20.000) según la sección 17, el Chorro lleva lo que roba; cuerpos tirados con charco de sangre (cada uno con su ropa), salpicaduras al pegar y al recibir golpes; zombies gore; Lionel herido y grave (ropa rota, tierra, sangre, venda); nevada, viñeta fría, escombros, basura, yuyos, fogatas, cuerpos viejos y pintadas | El Trapito suelta $1.000 (antes $800); la música de los niveles es FLAC (venía con extensión .mp3) | Pruebas con 3 personas de afuera; balance |

**Fase siguiente: 10 · Nivel 5: el Monumental.** Tribunas, túnel y cancha, la oleada final y el
jefe Gordo Barra con su bombo; se entra al túnel del Club Último Refugio.

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
| 9 | Música y 4 o 5 efectos | ✅ (archivos del equipo, fase 9) |
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

### Fase 7 · Hinchas, dificultad y mapas (🧪 en prueba)

Entregado:
- Camisetas: 17 diseños con los colores clásicos de clubes de la Liga Profesional, sin escudos,
  nombres ni sponsors (secciones 3 y 11 del documento). Cada Hincha sale con una al azar
  (animaciones `derecha_k`, `abajo_k`, etc.; variable `Sufijo`).
- Dificultad: Chorro 105, Jubilado 48 y Hincha 80 de velocidad; los zombies ven a Lionel a 550 px;
  la aparición baja 0,2 s por vez hasta 1 s; tope de zombies = base + 1 cada 350 px. Nivel 1: cada
  3 s, base 6; nivel 2: 2,6 s, base 7; nivel 3: 2,4 s, base 8. Más zombies al arrancar cada nivel.
- Mapas a escala realista (1 m ≈ 12 px), con datos relevados de Urbipedia, argentina.gob.ar,
  Wikipedia y Turismo BA:
  - Retiro (3840×1312): hall de mármol con boleterías, reloj y bancos; molinetes; dos naves de
    250 m con arcos cada 10 m y 8 andenes; formaciones de 7 vagones; fachada con la Torre
    Monumental; el Kiosco de Don Ramón cruzando la calle.
  - 9 de Julio (2400×1400): 7 carriles por mano, Metrobus central, la plaza del Obelisco (base de
    6,8 m), Corrientes con sendas y marquesinas de teatro, taxis negros y amarillos, colectivos.
  - Plaza de Mayo (3200×1500): fachada y reja de la Casa Rosada, canteros de Thays con palmeras,
    Pirámide con los pañuelos pintados, Monumento a Belgrano, mástil, Catedral, Cabildo con sus
    arcadas, la torre y la bajada al subsuelo.

Verificado:
- Validador libGD 5.6.284: 1528 instrucciones, 0 errores.
- Navegador: los 57 puntos de aparición (30 + 14 + 13) con camino al inicio y a la zona segura;
  objetos y trapitos fuera de los obstáculos; con el mapa vacío se vuelve a llenar en 8 a 16 s;
  camisetas variadas; vistas generales de los tres mapas.
- Probado por el equipo en el editor de GDevelop (2026-10-26).

Errores encontrados y corregidos:
- La formación de la vía 5 de Retiro dejaba 28 px contra la fachada y los zombies del andén de
  abajo no encontraban camino hacia el este: se corrió 10 m.

### Fase 8 · Nivel 4: la Casa Rosada (🧪 en prueba)

Entregado:
- Escena `Nivel4_CasaRosada` (sección 16), a escala (1 m ≈ 12 px; la manzana mide unos 100 × 130 m),
  con datos del sitio oficial de la Casa Rosada: entrada por Balcarce 50; hall con bustos; Patio de
  las Palmeras (patio de honor) con piso cerámico, las cuatro palmeras, la fuente central, dos
  jarrones y la galería de columnas; escaleras de honor Italia y Francia con alfombra roja; Salón
  Blanco con parquet, arañas y sillas; el balcón sobre Balcarce; Galería de los Bustos; Salón de los
  Científicos y despacho; la puerta de atrás en Paseo Colón y la explanada con el helipuerto como
  zona segura.
- Jefe Zombie Político (sección 4): traje, corbata y megáfono. Da su discurso desde el balcón hasta
  que Lionel entra al Salón Blanco o le pegan. 40 de vida, pega 20, tira promesas de campaña (8 de
  daño) con frases que aparecen sobre su cabeza. En la segunda mitad tira tres en abanico, camina
  más rápido y llama a dos Colectiveros de custodia. Suelta $20.000. Al vencerlo se abre la puerta
  de Paseo Colón.
- Flujo de cuatro niveles: Nivel 3 → subsuelo → Nivel 4 → helipuerto → Victoria. "Reintentar"
  vuelve al nivel 4.

Verificado:
- Validador libGD 5.6.284: 2048 instrucciones, 0 errores.
- Navegador: los 18 puntos de aparición con camino a la entrada y al Salón Blanco; el jefe no se
  activa desde la calle; promesas, frases, segunda mitad (abanico y custodia), muerte ($20.000),
  puerta que se abre; con la puerta cerrada no se puede salir; tienda → Victoria; Derrota →
  nivel 4; regresión de los niveles 1 a 3.
- Probado por el equipo en el editor de GDevelop (2026-10-27).

### Fase 9 · Sonido, plata y ambiente post-apocalíptico (🧪 en prueba)

Entregado:
- Sonido (sección 19), con los archivos del equipo en `assets/sonidos`: música del menú (menú,
  tienda, Victoria y Derrota) y de los niveles en el canal 1; disparo de pistola y de escopeta;
  recarga al juntar balas o cambiar de arma; recolectar (mate, botiquín, milanesa); caja
  registradora (billetes, dólar blue, trapito, compras); botones (pasar y clic); gruñidos (los
  zombies cercanos cada 4 a 9 s, al morir, al pegarle a Lionel y el Político al empezar la pelea).
- Plata (sección 17): Jubilado $500, Chorro $1.000 (más lo que te robó), Hincha $1.500, Trapito
  $1.000, Delivery $2.000, Colectivero $3.000 y el Político $20.000. Se sueltan en billetes reales
  en circulación, en pixel art a partir de las fotos del equipo: $500 (verde, ceibo y yaguareté),
  $1.000 (naranja, San Martín), $2.000 (gris y rosado, Grierson y Carrillo), $10.000 (turquesa,
  Remedios del Valle y Belgrano, con el sol) y $20.000 (azul sobre verde amarillento, Alberdi),
  simplificados y sin reproducirlos. El de $5.000 no existe: los fajos del mapa se arman con varios billetes.
- Gore: los cuerpos quedan tirados sobre un charco de sangre (cada uno con su ropa: el Hincha con
  su camiseta, el Político con su traje); salpicaduras al pegar y cuando atacan a Lionel; los zombies
  tienen sangre en la boca, heridas y huesos.
- Lionel se ve según su vida: sano, herido (≤ 60 %: ropa rota, tierra, raspones) y grave (≤ 30 %:
  más sangre, pálido y con una venda en la cabeza).
- Ambiente post-apocalíptico, con El Eternauta y The Last of Us como referencia: nevada en dos
  capas (menos en la Casa Rosada, que es por dentro), viñeta fría, escombros, basura, sangre seca,
  nieve acumulada, yuyos entre las baldosas, fogatas en tachos, zapatillas perdidas, cuerpos viejos
  y pintadas ("LO VIEJO FUNCIONA", "NO SALGAN: LA NEVADA MATA", "QUE SE VAYAN TODOS (YA SE
  FUERON)"...). Se reparten solos en los lugares libres de cada mapa.

Verificado:
- Validador libGD 5.6.284: 2419 instrucciones, 0 errores; los sonidos se exportan.
- Navegador: música de menú y de nivel (la FLAC carga); Hincha muerto → cuerpo con su camiseta,
  charco y $1.000 + $500; el Chorro se lleva $500 y los suelta; Lionel sano, herido y grave; jefe →
  billete de $20.000 y cuerpo; tienda con caja registradora; regresión de los cuatro niveles.
- Probado por el equipo en el editor de GDevelop (2026-10-27).
