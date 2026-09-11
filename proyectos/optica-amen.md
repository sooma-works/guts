# optica-amen — demo de catálogo

| | |
|---|---|
| Código | `~/dev/optica-amen` |
| Repo | `git@github-sooma:sooma-works/optica-amen.git` |
| Cliente | Óptica A.M.E.N. |
| Estado | Demo activo, mostrándose al cliente. |

Catálogo público (productos, precios, promos con tarjeta y cuotas) + panel interno
para cargar productos y destacar promociones. Sigue el stack de demos de
`contexto/stack.md`.

Panel separado por subdominio. Paleta sacada del logo del cliente. Node fijado en 22
para el build.

## Lo que hay que tener presente

- **Supabase no está configurado.** Corre con el backend de `localStorage`
  (`src/lib/backend.js`). Funciona standalone para mostrárselo al cliente.
- `supabase_setup.sql` ya incluye la tabla `consultas` (formulario de contacto, con
  RLS de insert público y lectura solo autenticada), pero **nunca se ejecutó**. Si
  se conecta Supabase, hay que correr ese archivo completo o el formulario va a
  fallar al enviar.
- El footer es bordó (`#33090a`), así que la firma va en su variante para fondo
  oscuro: `src/components/SoomaSignature.jsx` + `.css`.
