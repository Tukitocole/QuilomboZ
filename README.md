# Quilombo Z

Acción y supervivencia 2D con vista desde arriba, hecho en **GDevelop 5** (probado con la
versión 5.6.283). Lionel tiene que cruzar Buenos Aires infestada de zombies hasta el Club
Atlético Último Refugio.

> "Sobrevivir en Argentina ya era difícil. Ahora, con zombies."

## Cómo abrirlo

1. Abrir GDevelop.
2. *Abrir un proyecto* → elegir `game.json` de esta carpeta.
3. Vista previa con el botón ▶ (arranca en la escena `Menu`).

Toda la lógica está en las **hojas de eventos** de cada escena (condiciones y acciones de
GDevelop). No hay bloques de JavaScript.

## Controles

| Acción | Tecla |
|---|---|
| Moverse (4 direcciones) | WASD o flechas |
| Apuntar | Mouse (Lionel y el arma giran hacia el puntero) |
| Disparar | Clic izquierdo (o mantenerlo), toque en pantalla o Espacio |
| Empezar desde el menú | Enter, Espacio o clic en JUGAR |

## Estructura

| Escena | Qué tiene |
|---|---|
| `Menu` | Pantalla de inicio; reinicia las variables globales (partida nueva) |
| `Nivel1_Retiro` | Kiosco de inicio, molinetes, andenes con el Sarmiento parado y salida al Kiosco de Don Ramón. Zombies, objetos para juntar y HUD |
| `Tienda` | Provisoria (se completa en la fase 3) |
| `Victoria` / `Derrota` | Provisorias, con vuelta al menú |

- **Variables globales:** `Kills`, `Municion`, `MunicionMaxima`, `Plata`, `NivelActual`,
  `Inflacion`, `VidaMaxima`, `VelocidadBase`, `DanioExtra`, `ArmaActual`, `HabilidadActiva`,
  `TieneEscopeta` y las de "inicio de nivel" para el reintento (`PlataInicioNivel`,
  `MunicionInicioNivel`, `KillsInicioNivel`).
- **Variables de `Nivel1_Retiro`:** `CadenciaDisparo` (0,3 s), `VelocidadBala` (320 px/s),
  `AnguloApunte`, `IntervaloSpawn` (arranca en 4 s y baja hasta 1,5 s), `MaxZombiesBase` (4;
  se suma 1 cada 500 px que avanza Lionel), `TipoSpawn` y `PlataTexto` (la plata con punto
  de miles para el HUD).
- **Grupo `Obstaculos`:** Pared, Tren, Columna, Molinete y Auto. Todo lo que frena a Lionel y
  a las balas; además tienen el comportamiento de obstáculo para la búsqueda de caminos.
- **Grupo `Zombies`:** `ZombieChorro`, `ZombieJubilado` y `ZombieHincha`. Cada uno tiene las
  variables `Vida`, `Danio`, `Velocidad`, `Plata` (lo que suelta al morir), `Alerta` y `Color`
  (su tinte), y el comportamiento de búsqueda de caminos `Pathfinding`.

### Zombies y objetos

| | Vida (balas) | Daño | Velocidad | Suelta | Extra |
|---|---|---|---|---|---|
| Chorro | 1 | 10 | 95 | $1.000 | Te afana 2 balas y $500 |
| Jubilado | 3 | 8 | 40 | $500 | — |
| Hincha | 2 | 12 | 70 | $1.500 | Aparece en manada de 3 |

- Los zombies esperan hasta ver a Lionel (450 px) o hasta que les disparen; después lo
  persiguen esquivando paredes y trenes. Pegan como máximo una vez por segundo.
- Al morir sueltan un billete con su plata y, a veces (30 %), una caja de balas.
- Objetos: `CajaMunicion` (+6 balas, hasta `MunicionMaxima`), `Mate` (+15 de vida),
  `Botiquin` (+60), `Billete` (variable `Valor`) y `DolarBlue` ($15.000, escondido).
- Los `PuntoAparicion` marcan dónde pueden nacer zombies; son invisibles durante el juego.
- Resolución 640×360 escalada sin suavizado (pixel art).

## Arte

Sprites de 32×32. Lionel, el zombie, las armas y el botiquín son del equipo; el resto es
**provisorio**. Para cambiar uno alcanza con reemplazar el PNG por otro con el mismo nombre
y tamaño, o cargar la imagen nueva desde el editor de objetos de GDevelop. Los eventos no
cambian.

| Carpeta | Contenido |
|---|---|
| `assets/jugador/` | Lionel del equipo: `prota.png` (sin manos, se usa con arma) y `prota1.png` (con manos), `manos.png`. Un solo cuadro por ahora |
| `assets/armas/` | Uzi y AK-47 del equipo (sueltas y empuñadas) y pistola provisoria. El arma empuñada gira sobre la mano: el punto de giro es el centro de los píxeles color piel |
| `assets/zombies/` | `zgenerico.png` (los tres tipos, con tinte distinto) y `ztincho1.png` (para un zombie futuro) |
| `assets/objetos/` | Bala, caja de balas, mate, botiquín (del equipo), billete y dólar blue |
| `assets/escenario/` | Pisos, vías, paredes, tren, columnas, molinetes, autos, zona segura |
| `assets/interfaz/` | Botón, fondo del menú, barra (HUD) y marcador de punto de aparición |

El avance por fases está en [FASES.md](FASES.md).
