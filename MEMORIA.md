# Winners League UNIMET — App de la liga de fútbol

> Actualizada: 2026-11-09.

## Qué es
Prototipo de app web para la liga de fútbol Winners League UNIMET (no es el sitio oficial): marcador en vivo (40′, fases 1v1→7v7, ruleta entre 20′ y 38′, sanciones con cuenta regresiva), avisos de gol, tabla de posiciones (G 3 · GP 2 · PP 1 · P 0), noticias y gestión para organizadores: inventario (balones, chalecos, cintas de capitán), jugadores, entrenadores, equipos, deudas, tarjetas, MVPs, jornadas y reportes de lesión.

## Estado
JET: prioridad alta, ~59 %, responsable Tomás, inicio 2026-11-02, entrega **2026-11-14**.

## Dónde vive
- Repo público: `Ericklujnasba/winners-league-unimet` (Tomás invitado con permiso de escritura).
- Demo: https://ericklujnasba.github.io/winners-league-unimet/ (GitHub Pages).
- Datos en Supabase en tiempo real; los organizadores se autorizan en la tabla `organizadores_autorizados`. Si Supabase falla, la app usa una copia local de prueba.

## Stack
Un solo `index.html` sin compilación + Supabase (la clave anon pública va en el HTML; los permisos se controlan con RLS).

## Roles
Organizador (edita todo), Entrenador (su plantilla y reportes de lesión), Jugador (ve y sigue a sus favoritos).
