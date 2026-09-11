# sooma-hq

La base de operaciones de Sooma. **No hay código acá: hay contexto.**

Abro Claude Code parado en este repo y ya sabe quién soy, cómo trabajo, en qué ando
y cómo está cada proyecto. Todo en markdown, todo en GitHub, siempre al día.

## Mapa

```
CLAUDE.md      Las instrucciones. Claude lee esto solo, al abrir el repo.
ahora.md       En qué estoy trabajando hoy. El archivo que más cambia.
bitacora.md    Decisiones y cambios de rumbo, con fecha. Lo nuevo arriba.

contexto/
  quien-soy.md      Quién soy y cómo me gusta que se trabaje.
  stack.md          El stack por defecto y por qué.
  convenciones.md   Git, las dos cuentas de GitHub, la firma del footer.

proyectos/
  <uno por proyecto>  Dónde vive, en qué anda, qué hay que tener presente.
```

## Cómo se usa

Abrís Claude Code en `~/dev/sooma-hq` y arrancás a hablar. Él lee `CLAUDE.md` solo,
y desde ahí sabe qué más leer.

El código de los proyectos sigue viviendo en `~/dev/<proyecto>/`. Este repo guarda
el contexto de esos proyectos, no sus archivos.

## La regla que lo mantiene vivo

Si algo se decide, se cambia o se aprende, **se escribe acá antes de cerrar la
sesión**. Un repo de contexto desactualizado es peor que no tenerlo, porque te hace
confiar en algo que ya no es cierto.

Claude tiene indicado commitear y pushear solo en este repo, sin preguntar.
