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
| Apuntar | Mouse |
| Disparar | Clic izquierdo (o mantenerlo), toque en pantalla o Espacio |
| Empezar desde el menú | Enter, Espacio o clic en JUGAR |

## Estructura

| Escena | Qué tiene |
|---|---|
| `Menu` | Pantalla de inicio; reinicia las variables globales (partida nueva) |
| `Nivel1_Retiro` | Kiosco de inicio, molinetes, andenes con el Sarmiento parado y salida al Kiosco de Don Ramón |
| `Tienda` | Provisoria (se completa en la fase 3) |
| `Victoria` / `Derrota` | Provisorias, con vuelta al menú |

- **Variables globales:** `Kills`, `Municion`, `MunicionMaxima`, `Plata`, `NivelActual`,
  `Inflacion`, `VidaMaxima`, `VelocidadBase`, `DanioExtra`, `ArmaActual`, `HabilidadActiva`,
  `TieneEscopeta` y las de "inicio de nivel" para el reintento (`PlataInicioNivel`,
  `MunicionInicioNivel`, `KillsInicioNivel`).
- **Variables de `Nivel1_Retiro`:** `CadenciaDisparo` (0,3 s) y `VelocidadBala` (320 px/s).
- **Grupo `Obstaculos`:** Pared, Tren, Columna, Molinete y Auto. Todo lo que frena a Lionel y
  a las balas.
- Resolución 640×360 escalada sin suavizado (pixel art).

## Arte

`assets/` tiene sprites **provisorios** de 32×32. Para cambiarlos alcanza con reemplazar
cada PNG por otro con el mismo nombre y tamaño, o cargar las imágenes nuevas desde el editor
de objetos de GDevelop. Los eventos no cambian.

| Carpeta | Contenido |
|---|---|
| `assets/jugador/` | Lionel: `abajo`, `arriba`, `izquierda`, `derecha`, 2 cuadros cada una |
| `assets/zombies/` | Chorro y Jubilado (se usan desde la fase 2) |
| `assets/objetos/` | Bala |
| `assets/escenario/` | Pisos, vías, paredes, tren, columnas, molinetes, autos, zona segura |
| `assets/interfaz/` | Botón, fondo del menú y barra |

El avance por fases está en [FASES.md](FASES.md).
