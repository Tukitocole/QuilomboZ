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
| Usar (disparar / pegar) | Clic izquierdo (o mantenerlo), toque en pantalla o Espacio |
| Inventario | 1 puños · 2 pistola · 3 arma principal (la que se compra) |
| Pagarle al trapito | E (nivel 3, $500) |
| Pausa | Esc (Esc o Enter para seguir, M para ir al menú) |
| Tienda | 1, 2, 3 o clic para comprar · Enter para seguir viaje |
| Empezar desde el menú | Enter, Espacio o clic en JUGAR |
| Victoria / Derrota | Enter: jugar de nuevo / reintentar · M: menú |

## Estructura

La jugabilidad común está en los **eventos externos "Jugabilidad"** (panel del proyecto → Eventos
externos). Cada escena de nivel la incluye con un evento de **enlace** y suma solo lo propio
(qué zombies aparecen, objetos especiales). Un cambio en "Jugabilidad" vale para todos los niveles.

| Escena | Qué tiene |
|---|---|
| `Menu` | Pantalla de inicio; reinicia las variables globales (partida nueva) |
| `Nivel1_Retiro` | Estación a escala: hall de mármol con boleterías y reloj, molinetes, dos naves con 8 andenes y trenes de 7 vagones, Torre Monumental y el Kiosco de Don Ramón cruzando la calle |
| `Nivel2_Obelisco` | La 9 de Julio a escala: 7 carriles por mano, Metrobus, Corrientes con marquesinas, taxis y colectivos, el Obelisco, puesto de choripán y la parada blindada. Zombies Delivery y Colectivero |
| `Nivel3_Cabildo` | La Plaza de Mayo a escala: reja de la Casa Rosada, Pirámide con los pañuelos, Monumento a Belgrano, Catedral, vallas con trapitos, carpas y las arcadas del Cabildo con la bajada al subsuelo. Zombie Trapito |
| `Nivel4_CasaRosada` | La Casa Rosada por dentro: Patio de las Palmeras, escaleras de honor, Salón Blanco, balcón, Galería de los Bustos y la puerta de atrás a Paseo Colón. Jefe Zombie Político |
| `Tienda` | Kiosco de Don Ramón (nivel 1) o Parada blindada (nivel 2): chaleco, mochila y escopeta con inflación |
| `Victoria` | Resumen, jugar de nuevo y menú |
| `Derrota` | Pierde la mitad de la plata del nivel; reintentar o menú |

- **Variables globales:** `Kills`, `Municion`, `MunicionMaxima`, `Plata`, `NivelActual`,
  `Inflacion`, `VidaMaxima`, `VelocidadBase`, `DanioExtra`, `ArmaActual`, `HabilidadActiva`,
  `TieneEscopeta` y las de "inicio de nivel" para el reintento (`PlataInicioNivel`,
  `MunicionInicioNivel`, `KillsInicioNivel`).
- **Variables de cada nivel** (las usa "Jugabilidad"; además `AnchoMapa` y `AltoMapa` para la cámara): `CadenciaDisparo` (0,3 s), `VelocidadBala` (320 px/s),
  `AnguloApunte`, `IntervaloSpawn` (3 / 2,6 / 2,4 s según el nivel; baja hasta 1 s), `MaxZombiesBase` (6 / 7 / 8;
  se suma 1 cada 350 px que avanza Lionel), `TipoSpawn` y `PlataTexto` (la plata con punto
  de miles para el HUD).
- **Grupo `Obstaculos`** (cada nivel arma el suyo): todo lo que frena a Lionel y a las balas;
  además tienen el comportamiento de obstáculo para la búsqueda de caminos.
- **Grupo `Zombies`:** todos los zombies del nivel. Cada uno tiene las variables `Vida`, `Danio`,
  `Velocidad`, `Plata` (lo que suelta al morir), `Alerta` y `Color` (su tinte).
- **Grupo `Caminantes`:** los zombies con el comportamiento de búsqueda de caminos `Pathfinding`
  (todos menos el Delivery, que carga en línea recta).

### Zombies y objetos

| | Vida (balas) | Daño | Velocidad | Suelta | Extra |
|---|---|---|---|---|---|
| Chorro | 1 | 10 | 105 | $1.000 | Te afana 2 balas y $500 |
| Jubilado | 3 | 8 | 48 | $500 | — |
| Hincha | 2 | 12 | 80 | $1.500 | Manada de 3 (4 en el nivel 3); camiseta de club al azar (17 diseños, sin escudos) |
| Delivery (nivel 2) | 1 | 10 | 230 en carga | $2.000 | Carga en línea recta, frena y vuelve a cargar |
| Colectivero (nivel 2) | 6 | 20 | 32 | $3.000 | Más grande; "el tanque de la avenida" |
| Zombie Político (jefe, nivel 4) | 40 | 20 (promesas: 8) | 45 / 70 | $20.000 | Tira promesas; a mitad de vida, abanico y custodia de Colectiveros |
| Trapito (nivel 3) | 3 | 0 tranquilo / 12 enojado | 55 | $1.000 | Pide una moneda: E para pagarle $500; si no, se enoja |

- Los zombies esperan hasta ver a Lionel (550 px) o hasta que les disparen; después lo
  persiguen esquivando paredes y trenes. Pegan como máximo una vez por segundo.
- Al morir quedan tirados sobre un charco de sangre y sueltan su plata en billetes argentinos
  ($500, $1.000, $2.000, $10.000 y $20.000) y, a veces (30 %), una caja de balas. El Chorro suelta
  también lo que te robó.
- Lionel se ve herido (≤ 60 % de vida) y grave (≤ 30 %).
- Sonidos en `assets/sonidos` (música del menú y de los niveles, disparos, recarga, recolectar,
  caja registradora, botones y gruñidos).
- Ambiente: nevada, viñeta fría y decoración post-apocalíptica repartida sola en cada mapa.
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
| `assets/jugador/` | Lionel del equipo: `prota.png` (sin manos), `prota1.png` (con manos), `manos.png`. Caminata provisoria derivada de esos sprites: `lionel_<dir>_<0-3>.png` (con arma) y `lionel_manos_<dir>_<0-3>.png` (con los puños); `mano.png` (mano suelta) |
| `assets/armas/` | Uzi y AK-47 del equipo (sueltas y empuñadas), pistola y escopeta provisorias. El arma empuñada gira sobre la mano: el punto de giro es el centro de los píxeles color piel |
| `assets/zombies/` | `zgenerico.png` y su caminata provisoria `zombie_<dir>_<0-3>.png` (los tres tipos, con tinte distinto); `ztincho1.png` para un zombie futuro |
| `assets/objetos/` | Bala, caja de balas, mate, botiquín (del equipo), billete y dólar blue |
| `assets/escenario/` | Estación Retiro: piso del hall, franja táctil, vías de hormigón, topes, muro de piedra, vagones y cabinas, columnas de hierro, sombra del techo, puesto de diarios, bancos, cestos, faroles, bandera, banderines, grafitis, bolsas, perro, palomas; además paredes de ladrillo, molinetes, autos y zona segura |
| `assets/interfaz/` | Botón, fondos del menú y de la tienda, barra (HUD), íconos (puño, chaleco, mochila), cartel y marcador de punto de aparición |

El avance por fases y sprints está en [FASES.md](FASES.md). Guion de la demo: [DEMO.md](DEMO.md). Pruebas con terceros: [PRUEBAS.md](PRUEBAS.md).
