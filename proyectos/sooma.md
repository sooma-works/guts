# sooma — sitio de la marca

| | |
|---|---|
| Código | `~/dev/sooma` |
| Repo | `git@github-sooma:sooma-works/sooma.git` |
| Cliente | Propio |
| Estado | En línea, soomaworks.com. Último toque 2026-08-31. |

## Qué es

El sitio propio de Sooma. Cuatro rutas (`/`, `/proceso`, `/proyectos`, `/contacto`).

## Stack

React + Vite, **sin Tailwind**. Cada ruta se prerenderiza a su propio HTML en el
build. Dependencias: `react`, `react-dom`, `react-router-dom`, `lucide-react`.
Scripts: `dev`, `build`, `preview`, `deploy`.

## Qué hay que tener presente

**Es la fuente de la firma.** El componente `Signature` vive en
`src/components/Brand.jsx` y los assets del isotipo en `public/assets/`. Cuando hay
que poner la firma en otro sitio, la receta validada está en la sección 6 de
`instrucciones.md` — no copiar el componente crudo.

## Registro

### 2026-08-31 — Pie unificado

Se juntaron mail e Instagram en un solo bloque, después de varias pasadas sobre cómo
mostrar el link de Instagram (botón → pastilla → link).
