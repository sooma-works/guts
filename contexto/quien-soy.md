# Quién soy y cómo me gusta trabajar

Soy Nicolás Ramírez. Trabajo bajo la marca **Sooma** (soomaworks.com): hago sitios
web y demos para clientes. Casi siempre soy el único desarrollador del proyecto.

## Cómo hablarme

- **Español rioplatense.** Los nombres técnicos (variables, archivos, commits,
  código) en inglés, salvo que el proyecto ya use español.
- Directo. Si hay una opción claramente mejor, elegila y decime por qué. No me des
  un menú de cinco alternativas para que elija yo.
- Si algo falla, mostrame el error crudo. No lo maquilles ni me digas que está listo
  cuando no lo está.

## Cómo trabajar

- **No agregues dependencias sin avisarme.** Si se resuelve con lo que ya está
  instalado, resolvelo con eso.
- Antes de escribir un componente nuevo, fijate si ya existe uno parecido en el
  proyecto o en los proyectos hermanos de `~/dev`. Reuso antes que reinvento.
- **No inventes datos de clientes**, precios ni contenido de relleno que parezca
  real. Si falta contenido, poné un placeholder obvio y avisame.
- Si un cambio se ve en el navegador, verificalo vos antes de decirme que está.
  No me pidas que lo revise a mano.

## Secretos

- Nunca commitees `.env`, claves de Supabase, tokens ni credenciales de clientes.
- Las claves van en `.env` (gitignoreado) y se documentan vacías en `.env.example`.
- La `anon key` de Supabase es pública por diseño. La `service_role` **nunca** va al
  frontend ni al repo.

## Modelo

Trabajo con Claude Opus 5. Si escribís código que llame a la API de Claude, usá los
IDs de la familia Claude 5 (`claude-opus-5`, `claude-sonnet-5`) o
`claude-haiku-4-5-20251001`. Nunca hardcodees modelos viejos (`claude-3-*`).
