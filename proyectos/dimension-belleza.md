# dimension_belleza — sitio con checkout

| | |
|---|---|
| Código | `~/dev/dimension_belleza` |
| Repo | `git@github.com:ramireznicc/dimension_belleza.git` (cuenta personal) |
| Estado | En línea. Último toque 2026-09-07. |

El proyecto donde nació el patrón de demos de catálogo. A diferencia de los demás,
**tiene backend propio**: `backend/` con Express, que existe únicamente para el
checkout de Mercado Pago. El frontend va en `frontend/`, y hay `supabase_setup.sql`
y `netlify.toml` en la raíz.

**Por qué importa:** es la referencia de cuándo sí corresponde un backend. Si un
demo nuevo no tiene pagos, no lleva backend.

Ojo: el remote apunta a `github.com` directo, no al alias SSH. Es el único así.
