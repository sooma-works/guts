# Guts

Asistente de Nico y Carmela (Sooma). Este repo es su cabeza: **no hay código, hay
contexto.**

Abro Claude Code parado acá y ya sabe quién soy, cómo trabajo, en qué andamos y
cómo está cada proyecto. Todo markdown, todo en GitHub, siempre al día.

## Mapa

```
CLAUDE.md          Lo que Guts lee solo al abrir el repo: qué leer y cómo mantenerlo.
instrucciones.md   Cómo se trabaja. El manual.
memoria.md         En qué andamos + registro de decisiones con fecha.
clientes.md        Estado comercial y memoria de presupuestos.

proyectos/
  sooma.md           Una ficha por cada repo de la cuenta sooma-works.
  optica-amen.md
  _plantilla.md      Se copia al crear un repo nuevo.
  fuera-de-sooma.md  Lo de ~/dev que vive en la cuenta personal o sin git.
```

## Cómo se usa

Abrís Claude Code en `~/dev/guts` y hablás. El código de los proyectos sigue
viviendo en `~/dev/<proyecto>/`; acá va el contexto de esos proyectos, no sus
archivos.

Cuando creamos un repo nuevo en `sooma-works`, se copia `proyectos/_plantilla.md`
con el nombre del repo y se completa.

## La regla que lo mantiene vivo

Mantener esto al día es tarea de **Guts**, no de ustedes. Lo que se decide, se cambia
o se aprende se escribe en el archivo que corresponda durante la sesión, y se pushea
antes de cerrar. El protocolo completo está en `CLAUDE.md`, bajo "Mantenimiento".

Un repo de contexto desactualizado es peor que ninguno, porque te hace confiar en
algo que ya no es cierto.

Guts commitea y pushea solo en este repo, sin preguntar: el objetivo es que esté
siempre subido y sirva de backup en la nube.
