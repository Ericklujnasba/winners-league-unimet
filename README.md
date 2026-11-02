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

## Datos en vivo (Supabase)

Los datos viven en Supabase y se comparten en tiempo real: cuando un organizador marca un gol, todos los que tengan la app abierta ven el marcador y reciben el aviso.

- **Sin cuenta:** se pueden ver marcadores, tabla, equipos y noticias.
- **Con cuenta** (botón **Entrar**): se guardan los favoritos, los entrenadores eligen su equipo y reportan lesiones.
- **Organizadores:** los correos de la tabla `organizadores_autorizados` reciben el rol de organizador al registrarse. Para añadir uno:

```sql
insert into public.organizadores_autorizados (email) values ('correo@ejemplo.com');
-- si esa persona ya tenía cuenta:
update public.perfiles set rol = 'organizador'
where user_id = (select id from auth.users where email = 'correo@ejemplo.com');
```

Los permisos se controlan con Row Level Security: inventario, deudas, teléfonos de entrenadores y reportes de lesión solo los leen quienes corresponde, y solo los organizadores pueden editar la liga. La clave que aparece en `index.html` es la clave pública (anon) de Supabase, pensada para ir en el navegador.

Si Supabase no carga, la app pasa a una copia local de prueba que se guarda solo en ese navegador.

Es un solo archivo, `index.html`, sin dependencias de compilación.
