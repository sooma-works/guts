# optica-amen — demo de catálogo

| | |
|---|---|
| Código | `~/dev/optica-amen` |
| Repo | `git@github-sooma:sooma-works/optica-amen.git` |
| Cliente | Óptica A.M.E.N. |
| Estado | Demo activo, mostrándose al cliente. |

## Qué es

Catálogo público (productos, precios, promos con tarjeta y cuotas) + panel interno
para cargar productos y destacar promociones. El panel va separado por subdominio.

## Stack

El de siempre. Paleta sacada del logo del cliente. Node fijado en 22 para el build
porque el default rompía.

## Qué hay que tener presente

- **Supabase no está configurado.** Corre con el backend de `localStorage`
  (`src/lib/backend.js`), que funciona standalone para mostrárselo al cliente.
- `supabase_setup.sql` ya incluye la tabla `consultas` (formulario de contacto, con
  RLS de insert público y lectura solo autenticada), pero **nunca se ejecutó**. Si se
  conecta Supabase, hay que correr ese archivo completo o el formulario va a fallar
  al enviar. Es la trampa principal de este proyecto.
- El footer es bordó (`#33090a`): la firma va en la variante para fondo oscuro,
  `src/components/SoomaSignature.jsx` + `.css`.

## Registro

### 2026-09-08 — Datos reales y marca rediseñada

Se cargaron los datos reales del cliente, se sumó la sección de contacto y se aplicó
la marca rediseñada.

### 2026-09-07 — Rediseño y subdominio

UI rediseñada con la paleta del logo; el panel admin se separó por subdominio.
