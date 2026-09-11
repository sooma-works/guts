# Cómo trabajar en este repo

Este es el repo base de Sooma. No tiene código: tiene **contexto**. Sirve para que
vos, Claude, sepas quién soy, en qué ando y cómo trabajo, sin que yo lo repita.

## Al empezar una sesión

Leé, en este orden:

1. `ahora.md` — en qué estoy trabajando hoy. Es el archivo más importante.
2. `contexto/quien-soy.md` — quién soy y cómo me gusta que trabajes.
3. `contexto/convenciones.md` — git, naming, decisiones ya tomadas.
4. Si vamos a tocar un proyecto concreto, `proyectos/<nombre>.md`.

No leas todo el repo entero por las dudas. Leé lo que hace falta para la tarea.

## Durante la sesión

- Si trabajamos sobre código, el código vive en `~/dev/<proyecto>/`, **no acá**.
  Este repo es solo el contexto. Abrí los archivos del proyecto donde estén.
- Si aparece una decisión, una preferencia o un dato que me va a servir la próxima
  vez, **escribilo en el archivo que corresponda**. Ese es el punto del repo.
- Si algo de lo que está escrito acá ya no es cierto, corregilo. Un archivo
  desactualizado es peor que no tenerlo.

## Al terminar

1. Actualizá `ahora.md` si cambió en qué estoy trabajando.
2. Si pasó algo que valga la pena recordar (una decisión, un cambio de rumbo, algo
   que probamos y no funcionó), agregá una entrada arriba de todo en `bitacora.md`
   con la fecha.
3. Commiteá y pusheá a `main`. En este repo no hace falta que me preguntes: el
   objetivo es que esté siempre subido. Mensaje de commit corto y en español.

## Cómo escribir acá

- Español rioplatense, igual que como me hablás.
- Frases cortas. Esto lo vas a leer vos, no un cliente.
- Concreto sobre genérico: "Tailwind v4 con `@tailwindcss/vite`" y no
  "framework de CSS moderno".
- Cuando escribas una regla, escribí también **por qué**. Dentro de seis meses el
  porqué es lo único que me va a dejar decidir si sigue valiendo.
