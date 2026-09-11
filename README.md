# Guts

Asistente de Nicolás Ramírez (Sooma). Este repo es su cabeza: **no hay código, hay
contexto.**

Abro Claude Code parado acá y ya sabe quién soy, cómo trabajo, en qué andamos y
cómo está cada proyecto. Todo markdown, todo en GitHub, siempre al día.

## Mapa

```
CLAUDE.md          Lo que Guts lee solo al abrir el repo. Corto: le dice qué más leer.
instrucciones.md   Cómo se trabaja. El manual.
memoria.md         En qué andamos + registro de decisiones con fecha.

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

Lo que se decide, se cambia o se aprende **se escribe antes de cerrar la sesión**.
Un repo de contexto desactualizado es peor que ninguno, porque te hace confiar en
algo que ya no es cierto.

Guts commitea y pushea solo en este repo, sin preguntar.
