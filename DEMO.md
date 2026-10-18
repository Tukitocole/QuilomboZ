# Demo del lunes: guion

Duración sugerida: 6 a 8 minutos. Objetivo: mostrar que el MVP se juega de principio a fin
y contar qué parte de los sprints está cumplida y qué sigue.

## Antes de empezar

1. Abrir GDevelop → *Abrir un proyecto* → `game.json` de esta carpeta.
2. Probar ▶ una vez antes de la demo (la primera vista previa tarda un poco más).
3. Tener a mano [FASES.md](FASES.md) (cuadro de sprints y fases) para el cierre.

> La carpeta `export/web` tiene la versión web exportada. Para abrirla hace falta un servidor
> web (no anda con doble clic en `index.html`). Para la demo lo más seguro es el ▶ del editor,
> o publicarla en gd.games desde GDevelop (*Compartir → Publicar*, pide iniciar sesión).

## Guion

| Min. | Qué se muestra | Qué se dice |
|---|---|---|
| 0:00 | Menú | "Quilombo Z: sobrevivir en Argentina ya era difícil. Ahora, con zombies." Acción top-down en GDevelop, todo con eventos nativos, sin código. |
| 0:30 | Entrar al nivel: radio y kiosco | El mensaje de radio arma la historia. Lionel arranca en el kiosco de la estación, con la camiseta celeste y blanca. |
| 1:00 | Caminar en 4 direcciones y apuntar con el mouse | Lionel mira hacia donde apunta; el arma flota en la mano (estilo "Among Us", idea del equipo de arte). |
| 1:30 | Inventario 1 · 2 · 3 | 1 puños (golpe cuerpo a cuerpo), 2 pistola, 3 arma principal (se compra). Casilleros abajo a la derecha. |
| 2:00 | Andenes: zombies | Chorro (rápido, te roba balas y plata), Jubilado (lento, aguanta 3 tiros), Hincha (en manada de 3). Esquivan los trenes buscando el camino. |
| 3:00 | Objetos y plata | Caja de balas, mate, botiquín, billetes y el dólar blue escondido. HUD con vida, balas, kills y plata en pesos. |
| 3:30 | Pausa con Esc | Pausa real: se frena todo. |
| 4:00 | Llegar al Kiosco de Don Ramón | Zona segura → tienda. Precios con inflación ("Los precios los pone el mercado. El mercado soy yo."). Comprar algo y mostrar "No te alcanza, pibe". |
| 5:00 | Seguir viaje → Victoria | Resumen de zombies y plata; "Jugar de nuevo". |
| 5:30 | (Opcional) Morir a propósito → Derrota | Se pierde la mitad de la plata del nivel y se reintenta conservando lo comprado. |
| 6:00 | Cierre con FASES.md | Sprints 0 a 3 cumplidos en lo jugable; falta sonido, arte final, balance con pruebas de terceros y el Nivel 2 opcional. |

## Atajos para que la demo salga bien

- **Plata rápida para la tienda:** el dólar blue ($15.000) está en la esquina de abajo a la
  derecha de la calle, antes de entrar al kiosco de Don Ramón. Con eso alcanza para la escopeta.
- **Si los zombies aprietan:** tecla 1 y piñas, o volver hacia el kiosco del inicio.
- **Sin sonido:** la música y los efectos se suman cuando estén los archivos del equipo.
