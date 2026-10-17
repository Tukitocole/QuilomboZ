# Quilombo Z: fases de estado y entrega

Proyecto GDevelop 5 (probado con la versión 5.6.283). Toda la lógica va en **eventos nativos**
(condiciones y acciones), sin bloques de JavaScript.

Estados: ✅ Hecha · ⏳ En curso · ⬜ Pendiente · ⚠️ Bloqueada

| Fase | Estado | Entregable | Criterio de "lista" |
|---|---|---|---|
| 0 · Base técnica | ✅ Hecha | Formato de proyecto relevado y validador con libGD funcionando | El `game.json` carga en el motor sin errores |
| 1 · Núcleo jugable | ⏳ En curso | Escenas `Menu`, `Nivel1_Retiro`, `Tienda`, `Victoria` y `Derrota`; variables globales; Lionel con movimiento en 4 direcciones (WASD y flechas) y disparo al mouse con munición; mapa de Retiro con paredes; cámara que sigue al jugador | Se abre en GDevelop, se mueve y dispara dentro del mapa |
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
