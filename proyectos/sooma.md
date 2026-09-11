# sooma — sitio de la marca

| | |
|---|---|
| Código | `~/dev/sooma` |
| Repo | `git@github-sooma:sooma-works/sooma.git` |
| Web | soomaworks.com |
| Estado | En línea. Último toque 2026-08-31. |

Sitio propio de Sooma. React + Vite, cuatro rutas (`/`, `/proceso`, `/proyectos`,
`/contacto`), cada una prerenderizada a su propio HTML en el build. Sin Tailwind.

Scripts: `dev`, `build`, `preview`, `deploy`.

**Es la fuente de la firma.** El componente `Signature` vive en
`src/components/Brand.jsx` y los assets del isotipo en `public/assets/`. Cuando hay
que poner la firma en otro sitio, la receta está en `contexto/convenciones.md`.

Lo último que se tocó fue el pie: unificar mail e Instagram en un solo bloque.
