# Memoria

Lo que sé de lo que venimos haciendo. Arriba el presente, abajo el registro.

---

## Ahora

> Al 2026-09-11

**En foco**

- Repo `guts` andando y subido a github.com/sooma-works/guts. A partir de acá se
  trabaja con Claude Code parado en `~/dev/guts`.

**Pendiente**

- **optica-amen** — el demo se le muestra al cliente corriendo solo con el backend
  de `localStorage`. Supabase sigue sin configurar. Si se conecta, hay que correr
  `supabase_setup.sql` completo o el formulario de contacto (tabla `consultas`) va
  a fallar al enviar.
- **videos-marcas** — arrancado el 2026-09-07 con el reel de marca de Sooma. Sin
  remote en GitHub todavía.
- **sooma-signature** — la carpeta no tiene git. Convendría versionarlo.

**Para definir**

- **Óptica A.M.E.N.: pasar de "le gustó" a cerrar.** Falta definir qué incluye el
  trabajo y cuánto se cobra. Es lo que destraba el primer cliente real.
- Armar una referencia de precios propia. Hoy cada presupuesto sale de cero.

---

## Registro

Lo más nuevo arriba. Una entrada por cosa que valga la pena recordar en seis meses.

### 2026-09-11 — Guts se mantiene solo

Quedó establecido que actualizar **todos** los archivos del repo es tarea mía, en el
momento y sin que me lo pidan, y que pusheo apenas hay cambios. El protocolo —qué
archivo se toca y cuándo— está en `CLAUDE.md`, bajo "Mantenimiento". El repo se creó
en github.com/sooma-works/guts (privado) y se subió.

### 2026-09-11 — Para qué existe todo esto

Sooma es hoy una **segunda fuente de ingreso**. La meta es que crezca hasta poder
dedicarse a desarrollar webs y plataformas, ayudando a personas y a marcas.

El repo no nació de un problema: nació de querer estar más organizados con las tareas
y tener memoria e instrucciones respaldadas en la nube. Mantenerlo al día no es un
extra, es el objetivo.

Consecuencia práctica: el tiempo es el recurso escaso. Las propuestas tienen que
entrar en ratos libres, no ser el plan ideal de seis semanas.

### 2026-09-11 — Óptica A.M.E.N. gustó pero no cerró

Primer cliente real. La demo se sigue puliendo y la devolución fue buena, pero no hay
nada cerrado. Lo que falta no es técnico sino comercial: definir alcance, precio y
presentarlo.

### 2026-09-11 — Sooma son dos

Sooma no es Nico solo: trabajan en conjunto con **Carmela**, su novia. Nico hace
código, build y decisiones técnicas; Carmela lleva clientes y comercial (trato,
brief, propuestas, seguimiento) y el contenido: copy de los sitios, redes y
comunicación de la marca.

Los dos van a trabajar desde este repo, así que lo que se escriba acá tiene que ser
legible para los dos — Carmela no programa.

Como el código lo toca solo Nico, la regla de push directo a `main` sin ramas sigue
siendo correcta: no hay riesgo de pisarse. Queda marcada para revisar solo si Carmela
empieza a commitear o aparece producción real.

Están recién arrancando comercialmente: sin canal de entrada principal (llegan por
recomendación, redes y contacto directo) y sin tarifa fija — cada presupuesto se arma
de cero. Se creó `clientes.md` para ir construyendo esa referencia.

### 2026-09-11 — Nace Guts

El repo pasó a llamarse `guts` y a tener nombre propio: dejé de ser "la config" y
pasé a ser un asistente con identidad. La estructura quedó en tres piezas:
`instrucciones.md` (cómo trabajar), `memoria.md` (este archivo) y una ficha por cada
repo de la cuenta `sooma-works`.

Antes de esto se probaron dos enfoques y se descartaron: un repo de configuración
global enlazado por symlinks a `~/.claude/` (aplicaba las instrucciones en todas las
sesiones en silencio, en vez de vivir en el repo) y después `sooma-hq`, que era lo
mismo que esto pero con un nombre que sonaba a carpeta corporativa.

### 2026-09-08 — optica-amen se muestra sin Supabase

El demo se le presenta al cliente con el backend de `localStorage`. La decisión fue
no bloquear la demo esperando credenciales: `src/lib/backend.js` espeja la API de
Supabase y conmuta solo cuando aparecen las variables de entorno.

### 2026-09-07 — Firma de Sooma sobre fondo oscuro

Para el footer bordó de optica-amen no alcanzaba el isotipo monocromo: su tile tinta
se perdía contra el fondo. Se creó `sooma-tile-papel-tinta.svg`, variante de dos
tonos con los roles invertidos. Sigue valiendo la regla de no usar filtros CSS para
forzar un solo color.
