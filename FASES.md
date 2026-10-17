# Quilombo Z: fases de estado y entrega

Proyecto GDevelop 5 (probado con la versión 5.6.283). Toda la lógica va en **eventos nativos**
(condiciones y acciones), sin bloques de JavaScript.

Estados: ✅ Hecha · 🧪 Entregada, en prueba del equipo · ⏳ En curso · ⬜ Pendiente · ⚠️ Bloqueada

| Fase | Estado | Entregable | Criterio de "lista" |
|---|---|---|---|
| 0 · Base técnica | ✅ Hecha | Formato de proyecto relevado y validador con libGD funcionando | El `game.json` carga en el motor sin errores |
| 1 · Núcleo jugable | 🧪 En prueba | Escenas `Menu`, `Nivel1_Retiro`, `Tienda`, `Victoria` y `Derrota`; variables globales; Lionel con movimiento en 4 direcciones (WASD y flechas) y disparo al mouse con munición; mapa de Retiro con paredes; cámara que sigue al jugador | Se abre en GDevelop, se mueve y dispara dentro del mapa |
| 2 · Enemigos y supervivencia | ⬜ Pendiente | Zombies Chorro, Jubilado e Hincha con pathfinding; daño con cooldown de 1 s; spawn progresivo; HUD (vida, balas, kills, plata); munición, mate, botiquín y billetes para juntar | Se puede morir, matar zombies y juntar recursos |
| 3 · Objetivo, plata y pantallas | ⬜ Pendiente | Zona segura (Kiosco de Don Ramón); tienda mínima (chaleco, mochila, escopeta) con inflación; Victoria y Derrota con reintento y penalización de plata; carteles, frases de Lionel y radio | Se juega de principio a fin y se vuelve a jugar desde ambas pantallas |
| 4 · Pulido y entrega | ⬜ Pendiente | Música y efectos; parpadeo al recibir daño; pausa con Esc; balance; exportación web; guía de pruebas con terceros | Cumple los criterios de aceptación del MVP (sección 7 del documento de diseño) |

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
