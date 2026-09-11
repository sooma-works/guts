# sooma-signature — componente reutilizable

| | |
|---|---|
| Código | `~/dev/sooma-signature` |
| Repo | **sin git todavía** |
| Estado | Funciona, sin versionar. |

Copia standalone de la firma animada ("Hecho por sooma.", el logo se transforma en
el texto en loop), extraída de `~/dev/sooma` para reusar en otros sitios. Contiene
`Signature.jsx`, `Signature.css`, el SVG, `package.json` y `README.md`.

**Advertencia:** este paquete trae variantes `variant="white"|"black"` que fuerzan un
color con `filter: brightness(0)`. Ese enfoque **se descartó** en las integraciones
reales. La receta que sí funciona está en `contexto/convenciones.md`; usá esa, no las
props del paquete.

Pendiente: ponerle git y subirlo.
