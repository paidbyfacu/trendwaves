# trendwaves

Sitio estático de Trendwaves (trendwaves.net, deploy en Vercel desde `main`). Sin build: cada carpeta con `index.html` es una ruta.

## Páginas

- `/` → `index.html` (main del sitio).
- `/ramma/accion` → `ramma/accion/index.html`: página principal de la campaña de Ta Te Ti (Ramma). Los alias `/ramma-accion-single` y `/ramma-campaña` redirigen acá (`vercel.json`).
- `/ramma-accion-reglas` → `ramma-accion-reglas/index.html`: reglas de contenido para creadores de la misma campaña. Es independiente de `/ramma/accion` (no la modifica).
- Media de la campaña en `media/ramma/`. Las páginas usan rutas absolutas (`/media/...`) para que funcionen con o sin barra final.

## Trabajo compartido entre agentes — SIEMPRE sincronizar con GitHub

Este repo lo editan varios agentes de Claude (en distintas sesiones o PCs) además del usuario. GitHub es la fuente de verdad, no la copia local. Para no pisarse:

1. **Antes de tocar nada:** `git pull --rebase`. Nunca editar sobre una copia desactualizada.
2. **Después de cada cambio:** commit chico y descriptivo, `git pull --rebase` y `git push` a `main`, sin preguntar.
3. **Agregar solo lo que tocaste** (`git add <archivo>`, no `git add -A`): puede haber trabajo sin commitear de otro agente o del usuario.
4. **Conflictos:** resolverlos conservando los cambios del otro; si no está claro cuál vale, preguntar al usuario. Nunca `push --force` ni `reset --hard` sobre trabajo ajeno.
5. **Nada de secretos:** no subir `.env`, keys, tokens ni datos privados; si aparecen, sumarlos a `.gitignore` y avisar.
6. **Este CLAUDE.md es la memoria compartida:** toda regla, decisión o dato nuevo del proyecto se anota acá y se pushea, así el otro agente lo ve.
