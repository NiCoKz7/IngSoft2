# Copilot Instructions for IngSoft2

## Build, test, and lint

This repository currently does **not** define automated build, test, or lint commands (no `package.json`, test runner config, or linter config found).

For local preview during development, serve the static site from the repository root:

```powershell
cd "C:\Users\nico\Ingenieria Software 2\IngSoft2"
python -m http.server 8000
```

Then open `http://localhost:8000`.

Single-test execution is not applicable in the current repository state because no automated test framework is configured.

## High-level architecture

This is a **static frontend-only site**:

1. `index.html` is the entry point and contains almost all page structure/content.
2. Bootstrap is loaded from CDN in `index.html` (CSS + bundled JS).
3. Local styling lives in `css/styles.css` and customizes base elements (`body`, `hr`, `marquee`, `img`) plus Bootstrap class overrides (notably `.btn-primary` and its hover state).
4. Static assets are in `img/` and referenced directly from HTML.
5. `js/` exists but is currently unused (no local JS files referenced by `index.html`).

There is no backend, build pipeline, module bundling, or routing layer.

## Key repository conventions

1. **Language/content**: UI copy and documentation are in Spanish (`lang="es"` in `index.html`, Spanish README). Keep new user-facing text and docs consistent unless explicitly requested otherwise.
2. **Styling model**: Prefer Bootstrap utility/components first, then project overrides in `css/styles.css`. Existing code intentionally overrides Bootstrap’s `.btn-primary` colors and hover transition; preserve this behavior when editing buttons.
3. **Asset paths**: Use simple relative paths from `index.html` (`css/...`, `img/...`). Keep images in `img/` and reference exact filenames (including spaces/accents if present).
4. **Simplicity-first structure**: Current project keeps logic directly in `index.html` + `css/styles.css` without frameworks or build tooling; align new changes to that lightweight setup unless a tooling migration is explicitly requested.

## Recomendaciones 
- Cada vez que ingreses un nuevo código, inserta un comentario en español explicando las etiquetas utilizadas.
- Los ejemplos y el contenido en general deben estar en español.

