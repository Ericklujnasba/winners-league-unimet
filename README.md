# Winners League UNIMET · App de la liga

Prototipo de una app web para la liga de fútbol [Winners League UNIMET](https://unimet.winnersleague.net/). No es el sitio oficial.

**Demo:** https://ericklujnasba.github.io/winners-league-unimet/

## Qué incluye

- **Marcador en vivo** con reloj de 40′, fases del partido (1v1 → 7v7), ventana de ruleta (20′–38′) y sanciones con cuenta regresiva (amarilla 2′, roja 5′).
- **Avisos de gol** dentro de la app, con opción de recibir solo los de tus equipos favoritos.
- **Tabla de posiciones** con el sistema de puntos de la liga (G 3 · GP 2 · PP 1 · P 0), forma y goleadores.
- **Noticias y anuncios**; cada resultado final se publica solo.
- **Gestión** para organizadores: inventario (balones, chalecos, cintas de capitán…), jugadores, entrenadores, equipos, deudas, tarjetas y reportes de lesión.

## Roles

| Rol | Qué puede hacer |
| --- | --- |
| Organizador | Edita todo, maneja la mesa de control del partido, el inventario y los anuncios |
| Entrenador | Ve la plantilla de su equipo y reporta lesiones a los organizadores |
| Jugador | Ve noticias, marcadores y tabla, y apoya a sus equipos y jugadores favoritos |

## Nota sobre los datos

Esta versión es una demostración: cada persona puede probar los tres roles con el selector **Rol** y lo que cambia se guarda solo en su navegador (`localStorage`). Para compartir marcadores en vivo entre todos los dispositivos hace falta conectar una base de datos (por ejemplo Supabase o Firebase).

Es un solo archivo, `index.html`, sin dependencias de compilación.
