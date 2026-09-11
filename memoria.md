# Memoria

Lo que sé de lo que venimos haciendo. Arriba el presente, abajo el registro.

---

## Ahora

> Al 2026-09-11

**En foco**

- Armar este repo (`guts`) como base de contexto y memoria. Falta crearlo en GitHub
  y pushear: `sooma-works/guts`, privado.

**Pendiente**

- **optica-amen** — el demo se le muestra al cliente corriendo solo con el backend
  de `localStorage`. Supabase sigue sin configurar. Si se conecta, hay que correr
  `supabase_setup.sql` completo o el formulario de contacto (tabla `consultas`) va
  a fallar al enviar.
- **videos-marcas** — arrancado el 2026-09-07 con el reel de marca de Sooma. Sin
  remote en GitHub todavía.
- **sooma-signature** — la carpeta no tiene git. Convendría versionarlo.

**En pausa**

_(nada)_

---

## Registro

Lo más nuevo arriba. Una entrada por cosa que valga la pena recordar en seis meses.

### 2026-09-11 — Nace Guts

El repo pasó a llamarse `guts` y a tener nombre propio: dejé de ser "la config" y
pasé a ser un asistente con identidad. La estructura quedó en tres piezas:
`instrucciones.md` (cómo trabajar), `memoria.md` (este archivo) y una ficha por cada
repo de la cuenta `sooma-works`.

Antes de esto se probaron dos enfoques y se descartaron: un repo de configuración
global enlazado por symlinks a `~/.claude/` (aplicaba las instrucciones en todas las
sesiones en silencio, en vez de vivir en el repo) y después `sooma-hq`, que era lo
mismo que esto pero con un nombre que sonaba a carpeta corporativa.

### 2026-09-08 — optica-amen se muestra sin Supabase

El demo se le presenta al cliente con el backend de `localStorage`. La decisión fue
no bloquear la demo esperando credenciales: `src/lib/backend.js` espeja la API de
Supabase y conmuta solo cuando aparecen las variables de entorno.

### 2026-09-07 — Firma de Sooma sobre fondo oscuro

Para el footer bordó de optica-amen no alcanzaba el isotipo monocromo: su tile tinta
se perdía contra el fondo. Se creó `sooma-tile-papel-tinta.svg`, variante de dos
tonos con los roles invertidos. Sigue valiendo la regla de no usar filtros CSS para
forzar un solo color.
