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
