# Convenciones

## Git

- En los demos de clientes trabajo **directo sobre `main`**. Cuando pido "commiteá
  y pusheá", va a `main`. Nada de rama de feature ni PR.
  **Por qué:** son proyectos de una sola persona, sin revisión de código. Una rama
  intermedia que después tengo que mergear yo es fricción al pedo.
  **Ojo:** si alguna vez se suma un colaborador o hay un entorno de producción real,
  repreguntame antes de seguir con este flujo.
- En los repos de código, commiteá y pusheá **solo cuando lo pido**.
  En `sooma-hq` (este repo) no hace falta pedir: pusheá siempre.
- Mensajes de commit cortos. En español, salvo que el repo ya los tenga en inglés.

## Las dos cuentas de GitHub

Tengo dos identidades configuradas por alias SSH en `~/.ssh/config`. El alias va en
la URL del remote, en lugar de `github.com`:

| Alias | Cuenta | Se usa en |
|---|---|---|
| `github-sooma` | organización `sooma-works` | sooma, optica-amen, sooma-hq |
| `github-ramireznicc` | personal `ramireznicc` | portfolio, dimension_belleza |

Un remote queda así: `git@github-sooma:sooma-works/optica-amen.git`.

**Importante:** si cloná o agregás un remote con `github.com` en vez del alias, la
autenticación falla o usa la identidad equivocada. Fijate siempre en qué cuenta vive
el repo antes de armar la URL.

## La firma de Sooma en los footers

El componente fuente vive en `~/dev/sooma-signature`. Está validado a lo largo de
varias iteraciones, y estas reglas salieron de cosas que ya probamos y descartamos:

- **Tipografía:** `Bricolage Grotesque` 700, importada en el CSS del propio
  componente. Nunca hereda la fuente del sitio host — la firma se tiene que ver
  igual en todos lados.
- **Tamaño:** 14px de texto, 18px de isotipo. Discreto. El primer intento a 24/32px
  (el tamaño del footer de sooma) quedó muy grande.
- **Fondo claro:** texto `#171717`, isotipo `sooma-tile-monocromo.svg` tal cual.
- **Fondo oscuro:** texto `#fff` con `opacity: 0.72`, isotipo
  `sooma-tile-papel-tinta.svg` (los dos tonos invertidos).
- **Nunca** le apliques filtros CSS (`brightness(0)`, `grayscale`) al isotipo para
  forzarle un color. El asset es de dos tonos por diseño y colapsarlos lo convierte
  en un cuadrado negro feo. Ya se probó y se rechazó. Tampoco sirve usar un SVG
  inline con solo el trazo.
- En sitios sin `react-router-dom`, el link va como
  `<a href="https://soomaworks.com" target="_blank" rel="noreferrer">`.
- Queda bien sacando cualquier "Powered by X" que haya y poniendo un divisor fino
  (`w-8 h-px bg-neutral-200`) arriba.
