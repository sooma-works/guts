# Stack

## Demos de catálogo para clientes

Patrón validado en `dimension_belleza` y reusado en `optica-amen`. Para un sitio con
**catálogo público + panel admin con login** (sin checkout ni control de stock):

- Vite + React 19 + Tailwind v4 (`@tailwindcss/vite`) + `react-router-dom` +
  `framer-motion` + `lucide-react`
- **Supabase** para persistencia: Postgres con RLS (`SELECT` público, escrituras para
  el rol `authenticated`), bucket de storage público para imágenes, Supabase Auth
  para el login del admin. Sin backend propio.
- `supabase_setup.sql` en la raíz del repo, con schema + políticas RLS + seed, para
  correr una vez en el SQL Editor de Supabase.
- **Nada de Next.js ni SSR.** Un SPA de Vite alcanza y sobra para estos demos.
- Backend propio (Express) solo si hay pagos reales. Es el caso de
  dimension_belleza con Mercado Pago.

**Antes de elegir stack para un demo nuevo:** mirá las carpetas hermanas de `~/dev`
y seguí este patrón, salvo que el cliente necesite e-commerce de verdad.
**Por qué:** repetir un stack ya validado hace que un demo nuevo se arme rápido y me
deja copiar SQL y componentes entre proyectos.

### El truco del backend falso

Si todavía no hay credenciales de Supabase, armá un backend de demo sobre
`localStorage` en `src/lib/backend.js` que **espeje exactamente la forma de la API**
de las llamadas a Supabase, y que conmute solo cuando existan `VITE_SUPABASE_URL` y
`VITE_SUPABASE_ANON_KEY` en `.env`. Documentá las variables vacías en `.env.example`.

**Por qué:** así el demo se le puede mostrar al cliente sin depender de tener la
infraestructura levantada, y el día que aparecen las credenciales no hay que
reescribir nada.

## Deploy

Netlify en los proyectos que ya están arriba (`netlify.toml` en la raíz). En
optica-amen se fijó Node 22 para el build porque el default rompía.

## Sitios propios

- **sooma** — React + Vite, cuatro rutas (`/`, `/proceso`, `/proyectos`,
  `/contacto`), cada una prerenderizada a un HTML propio en el build. Sin Tailwind.
- **portfolio** — React + Vite con `framer-motion` e i18n (`i18next` +
  `react-i18next`). Ojo: el `name` del `package.json` todavía dice `temp-app`.
