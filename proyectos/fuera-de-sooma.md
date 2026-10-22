# Fuera de sooma-works

Proyectos de `~/dev` que **no** viven en la cuenta de la organización. No llevan
ficha propia, pero conviene tenerlos anotados para no perderlos de vista.

## portfolio — cuenta personal

`~/dev/portfolio` · `git@github-ramireznicc:ramireznicc/portfolio.git`

Portfolio personal de Nico. React + Vite con `framer-motion` e i18n (`i18next` +
`react-i18next`). Es donde se validó la firma de Sooma sobre **fondo claro**
(`src/components/SoomaSignature.jsx`), después de varias iteraciones; al sumarla se
sacó la línea "Powered by Claude" del pie.
Pendiente menor: el `name` del `package.json` todavía dice `temp-app`.

## dimension_belleza — cuenta personal

`~/dev/dimension_belleza` · `git@github.com:ramireznicc/dimension_belleza.git`

Donde nació el patrón de demos de catálogo. A diferencia del resto, **tiene backend
propio**: `backend/` con Express, que existe únicamente para el checkout de Mercado
Pago. El frontend en `frontend/`, y `supabase_setup.sql` + `netlify.toml` en la raíz.
**Por qué importa:** es la referencia de cuándo sí corresponde un backend. Si un demo
nuevo no tiene pagos, no lleva backend.
Ojo: el remote apunta a `github.com` directo, no al alias SSH. Es el único así.

## sooma-signature — sin git

`~/dev/sooma-signature`

Copia standalone de la firma animada, extraída de `~/dev/sooma` para reusar en otros
sitios. Trae `Signature.jsx`, `Signature.css`, el SVG, `package.json` y `README.md`.
**Advertencia:** trae variantes `variant="white"|"black"` que fuerzan un color con
`filter: brightness(0)`. Ese enfoque **se descartó** en las integraciones reales. La
receta que sí funciona está en la sección 6 de `instrucciones.md`.
Pendiente: ponerle git y subirlo.

## videos-marcas — sin remote

`~/dev/videos-marcas`

Videos de marca. Git local con un solo commit: el scaffold y el arranque del reel de
Sooma. Para animación se usa HyperFrames (las skills están instaladas en la máquina).
Pendiente: crearle el repo y pushear.

## claude-usage — cuenta personal

`~/.local/share/gnome-shell/extensions/claude-usage@ramireznicc` ·
`git@github-ramireznicc:ramireznicc/claude-usage-extension.git`

Extensión de GNOME (Shell 48–50) que muestra en la barra de arriba cuánto se gastó
del límite de Claude (sesión de 5 h y semanal). No vive en `~/dev`: GNOME la carga
desde esa carpeta, y el repo está ahí mismo.

Lee el token de Claude Code de `~/.claude/.credentials.json` y lo refresca sola
(desde el 2026-10-02).

**Trampa conocida:** la sesión de Claude Code dura **~30 días desde el login** y no
se estira al refrescar: el `refreshToken` rota, pero `refreshTokenExpiresAt` queda
fijo. Pasada esa fecha no hay refresh posible, haya estado la compu prendida o no. Se
arregla corriendo `claude` en una terminal y haciendo `/login`, una vez por mes. La
app de escritorio no renueva ese archivo, solo el CLI.
Evidencia (2026-10-22): login del 11/9 → venció el 10/10, aunque el CLI había
refrescado el 9/10. Login del 22/10 → vence el 20/11.

Desde el 2026-10-22 la extensión lo detecta sola (por `refreshTokenExpiresAt` o porque
el servidor rechaza el refresh con 400/401) y muestra *"Session expired — run `claude`
in a terminal and /login"*. Si el server está caído muestra el código HTTP y reintenta.

**Error a corregir:** en ese commit (`41af91c`) escribí que el `refreshToken` vence
~25 h después del access token. Es falso: es lo de los 30 días de arriba. Quedó así
en el README y en un comentario de `extension.js`. Además, al refrescar, la extensión
borra `refreshTokenExpiresAt` si la respuesta no lo trae; como el vencimiento es fijo,
lo correcto es conservarlo.

**Para probar cambios:** en Wayland GNOME no recarga el código de una extensión con
disable/enable. Hay que cerrar sesión y volver a entrar.
