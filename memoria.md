# Memoria

Lo que sé de lo que venimos haciendo. Arriba el presente, abajo el registro.

---

## Ahora

> Al 2026-11-22

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
- **claude-usage** — la sesión de Claude Code vence el **2026-11-20**. La extensión
  avisa en el menú desde el 17/11; ahí hay que hacer `/login` en el CLI.

**Para definir**

- **Óptica A.M.E.N.: pasar de "le gustó" a cerrar.** Falta definir qué incluye el
  trabajo y cuánto se cobra. Es lo que destraba el primer cliente real.
- Armar una referencia de precios propia. Hoy cada presupuesto sale de cero.

---

## Registro

Lo más nuevo arriba. Una entrada por cosa que valga la pena recordar en seis meses.

### 2026-11-22 — Los teles de la red de casa

En el wifi de casa (`192.168.100.0/24`, router en `.1`) hay dos teles:

- **`leles`** — el **Android TV**, un **TCL**, en `192.168.100.9`. Tiene abiertos los puertos del
  control remoto de Android TV (6466/6467) y Chromecast integrado (8008/8009).
- **`50" Crystal UHD`** — un Samsung en `192.168.100.58`. No es Android (es Tizen),
  solo acepta Chromecast.

**Ficha del TCL:** modelo `UnionTV`, Android TV 9 (`PPR2.180905.006.A1`), kernel
4.4, 1,4 GB de RAM y 4,2 GB de almacenamiento. Es lento porque se queda sin RAM.
ADB por red en el puerto 5555: se abre solo con la depuración USB activada, aunque
el menú no muestre "depuración por red". Esta compu ya está autorizada.

**Qué se le hizo (2026-11-22), todo reversible:**

- Animaciones: ya estaban en 0,5× cuando llegamos.
- Ya venían apagadas: Play Music, Galería, Play Películas y Play Juegos.
- Apagamos `com.tcl.bi` (telemetría de TCL), `com.tcl.esticker` (stickers y
  promos), `com.tcl.appmarket2` (tienda de TCL), `com.tcl.usercenter` (cuenta TCL)
  y `com.google.android.tvrecommendations` (las filas de recomendados).
- **Launcher nuevo: Projectivy** (`com.spocky.projengmenu`), del Play Store. En
  Android 9 el launcher de Google (`com.google.android.tvlauncher`) tiene prioridad
  de sistema y le gana a `set-home-activity`, así que lo apagamos. Si Projectivy
  falla, el tele cae a una pantalla de inicio de emergencia de TCL.
- Búsqueda por voz apagada (`com.google.android.katniss` y
  `com.google.android.speech.pumpkin`) a pedido: no usan el micrófono. El botón
  del micrófono del control ya no hace nada.
- **Apps que usan:** Netflix, YouTube, Crunchyroll, HBO Max y Disney+. Nada más.
  HBO Max (`com.wbd.stream`) no estaba y la instalamos desde el Play Store.
- Quitamos con `pm uninstall -k --user 0` todo lo demás que era de cara al usuario:
  Prime Video, los reproductores de TCL (audio, fotos, video y media center),
  `tvweishi`, `copydatatotv`, `keyhelp`, `backdrop` (protector de Google),
  TalkBack, la cola de impresión, `feedback`, `bugreportsender` y el launcher viejo
  (`leanbacklauncher` y dos de sus complementos). Para devolver una:
  `adb shell cmd package install-existing <paquete>`.
- Dejamos Chromecast (`mediashell`): sirve para mandar cosas desde el celular.
- **Projectivy configurado:** la fila "Aplicaciones Móviles" oculta (mostraba
  apps internas) y GalaView oculto (es una promo de TCL que viene en
  `com.tcl.partnercustomizer`; no la apagamos porque ese paquete también maneja
  botones del control). Se ve: Entradas (HDMI), las cinco apps más Play Store y
  TV, y "Continuar viendo".
- **Orden de filas:** primero "Aplicaciones de TV", segunda "Entradas". Projectivy
  no lo deja cambiar desde "Editar categorías": hay que prender Ajustes →
  Apariencia → Cabeceras izquierdas → Habilitar + "Mostrar reordenado", ir a la
  izquierda de todo de una fila en el inicio y usar las flechas. Quedaron
  prendidas; desde ahí lo siguió Nico a mano.
- Para manejar el tele por ADB, un "mantener apretado OK" de verdad se simula con
  `sendevent /dev/input/event2 1 28 1` … `1 28 0`. `input keyevent --longpress`
  llega como un toque común.
- **Velocidad (2026-11-22):** el procesador es ARMv7 de 32 bits, lento para
  traducir apps al vuelo. Compilamos completas las cinco apps y Projectivy con
  `cmd package compile -m speed -f <paquete>` (venían en `speed-profile`). Ocupan
  unos 300 MB más. YouTube pasó de 3,5 s a 2,2 s en abrir desde cero (1,1 s la
  segunda vez). **Ojo:** cuando el Play Store actualiza una app, vuelve a
  `speed-profile` y pierde la mejora: hay que repetir el comando para esa app.
  No hay forma de evitarlo en el tele: `setprop pm.dexopt.install speed` lo
  rechaza el sistema sin root. Se ofreció una tarea diaria desde la notebook que
  recompile sola y **Nico prefirió pedirlo a mano** cuando lo note lento.
  Animaciones en 0 (las tres escalas en `settings global`) y caché limpiada con
  `pm trim-caches`.
- Resultado: pasó de ~450 a ~600-680 MB de RAM libre.
- No tocamos los updates (`com.tcl.versionUpdateApp`, `com.tcl.rc.ota`).
- **Sistema:** parche de seguridad del 2020-09-05, compilado en noviembre de 2020.
  Seis años sin parche: casi seguro TCL ya no lo actualiza (no lo verificamos en
  el menú de actualización). Las apps sí se actualizan por el Play Store.

Para volver atrás una app: `adb shell pm enable <paquete>`.

Las IP las da el router por DHCP, así que pueden cambiar. Si no aparece, se busca
por nombre con mDNS (`_androidtvremote2._tcp`), que es lo que lo delató.

### 2026-10-31 — apt lento: no eran los mirrors

Un `apt upgrade` tardó mucho y se revisaron repos y mirrors de la compu (Ubuntu
26.04). La config está sana: `ubuntu.sources` apunta a `archive.ubuntu.com` y
`security.ubuntu.com`, más Brave y Claude Desktop, sin duplicados ni proxy. El
`ubuntu.sources.curtin.orig` que queda en `sources.list.d` lo ignora apt, no molesta.
La demora vino de que entró un **kernel nuevo** (7.0.0-42: imagen, headers, módulos,
initramfs y grub) entre 84 paquetes. Ese paso es lento siempre.
Se midieron mirrors: `ar.archive.ubuntu.com` no es un mirror local, resuelve a los
mismos servidores de Canonical. Los de Brasil (`mirror.uepg.br`, `sft.if.usp.br`)
están al día pero la velocidad varió tanto como la del oficial. **No se cambió nada**:
cambiar de mirror no rinde mientras no haya una diferencia sostenida.

### 2026-10-22 — claude-usage: la sesión de Claude dura 30 días

La extensión de GNOME de uso de Claude dejó de andar otra vez. Causa: la sesión de
Claude Code dura ~30 días desde el login y refrescar el token no la estira. Venció el
10/10 (login del 11/9). La compu estuvo apagada del 9/10 al 20/10, y al principio
pensé que esa era la causa, pero fue casualidad. Se arregla con `/login` en el CLI
una vez por mes. La extensión ahora avisa en el menú 3 días antes y, si se vence,
lo dice claro en vez de mostrar un error genérico. Detalle en `proyectos/fuera-de-sooma.md`.

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
