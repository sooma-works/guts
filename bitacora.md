# Bitácora

Decisiones y cambios de rumbo, lo más nuevo arriba. Una entrada por cosa que valga
la pena recordar dentro de seis meses.

---

## 2026-09-10 — Repo base de contexto

Creado `sooma-hq` para trabajar con Claude Code desde un solo lugar: instrucciones,
contexto y estado de los proyectos, todo en markdown y siempre subido a GitHub.

Antes de esto se probó otro enfoque — un repo de configuración global enlazado por
symlinks a `~/.claude/` — y se descartó: aplicaba las instrucciones en todas las
sesiones en silencio, en vez de que vivieran en el repo y se leyeran al abrirlo.

## 2026-09-08 — optica-amen se muestra sin Supabase

El demo se le presenta al cliente con el backend de `localStorage`. La decisión fue
no bloquear la demo esperando credenciales: `src/lib/backend.js` espeja la API de
Supabase y conmuta solo cuando aparecen las variables de entorno.

## 2026-09-07 — Firma de Sooma sobre fondo oscuro

Para el footer bordó de optica-amen no alcanzaba el isotipo monocromo: su tile tinta
se perdía contra el fondo. Se creó `sooma-tile-papel-tinta.svg`, variante de dos
tonos con los roles invertidos. Sigue valiendo la regla de no aplicar filtros CSS
para forzar un solo color.
