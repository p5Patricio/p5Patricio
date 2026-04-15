# p5Patricio — GitHub Profile (Yozakura Profundo)

Perfil de GitHub con tema japonés nocturno "Yozakura Profundo" (夜桜 — sakura de noche).
El objetivo es que el perfil se vea como una sola pieza cohesiva, no como secciones separadas.

## Contexto persistente

- **Engram project**: `p5patricio`
- **Observation clave**: #14 — "Rediseño completo perfil GitHub p5Patricio — Yozakura Profundo"
- **Recuperar contexto**: `mem_search(query: "Yozakura OR p5patricio", project: "p5patricio")`
- **Última sesión activa**: 2026-04-13

## Archivos del proyecto

| Archivo | Dimensiones | Descripción |
|---------|------------|-------------|
| `README.md` | ~200 líneas | Perfil principal con typing animation, stats, stacks |
| `header.svg` | 900×88 | Rama de sakura animada — encabezado del perfil |
| `divider.svg` | 900×180 | Sakura + agua + árboles — separador de secciones |
| `footer.svg` | 900×180 | Cierre visual del perfil |

## Design System

**Paleta principal:**
- Fondos: `#0f0f1a` (deep), `#1a1a2e` (mid)
- Sakura pinks: `#fecdd3`, `#ffb6c8`, `#ffa0b4`, `#ffc0d0`
- Ramas: `#3d2b1f`

**Stat widgets:** `?bg_color=0f0f1a&title_color=ffb6c8&text_color=fecdd3&icon_color=ffa0b4`

## Skills — LEER ANTES de modificar

### Obligatorias para SVGs
```
~/.claude/skills/github-profile-svg/SKILL.md      ← Constraints GitHub, patrones de animación
~/.claude/skills/yozakura-design-system/SKILL.md  ← Paleta, timings, cohesión visual
```

### Para nuevo diseño o rediseño
```
~/.claude/skills/frontend-design/SKILL.md   ← Filosofía de diseño, dark themes, tipografía
~/.claude/skills/svg-logo-designer/SKILL.md ← Workflow SVG con conceptos y variaciones
```

### Para artefactos HTML (previews, prototipos)
```
anthropic-skills:web-artifacts-builder  ← React + Tailwind + shadcn/ui
anthropic-skills:canvas-design          ← Arte visual PNG/PDF para mockups
```

## Restricciones GitHub SVG (resumen crítico)

- **NO JavaScript** en SVGs — se elimina al renderizar
- **NO fuentes externas** — usar system fonts o SVG paths
- **SÍ CSS animations** — `@keyframes` dentro de `<style>` funciona
- **SÍ SVG nativo** — `<animate>`, `<animateTransform>`, `<animateMotion>`
- **NO `<details>`** en README — rompe el flujo visual

## Reglas de cohesión README

- Secciones con `<h3 align="center">` — nunca `<details open>`
- Los SVGs deben ser extensión del fondo oscuro, no imágenes insertadas
- Espaciado: `<br>` simple entre secciones

## Animaciones canónicas

| Elemento | Duración | Easing |
|----------|----------|--------|
| Branch sway | 11s | ease-in-out |
| Petal fall | 10–18s | ease-in-out |
| Water shimmer | 6.3s | ease-in-out |

## Secciones del README (estado actual)

1. Header SVG (typing animation tagline)
2. About Me — YAML profile card (proyectos: DEMOX, VoiceAgenda)
3. Tech Ecosystem — Languages, Frameworks, Data, DevOps
4. AI & Developer Tooling — Claude Code, Cursor, Ollama, Gemini, spaCy
5. GitHub Trophies + Stats + Streak + Activity Graph
6. Beyond the Code — gaming interests
7. Connect — (placeholder links)

## Flujo de trabajo para cambios

### Modificar un SVG existente
1. Leer `github-profile-svg/SKILL.md`
2. Leer `yozakura-design-system/SKILL.md`
3. Leer el SVG completo antes de editar
4. Respetar paleta y timings canónicos
5. Testear que las animaciones sean CSS inline (sin JS)

### Agregar nueva sección al README
1. Usar `<h3 align="center">` para el título
2. Mantener `bg_color=0f0f1a` en todos los widgets
3. Sin `<details>` — todo fluye abierto

### Rediseño completo
1. Leer `frontend-design/SKILL.md`
2. Leer `yozakura-design-system/SKILL.md`
3. Proponer cambios antes de ejecutar

## Qué quedó pendiente (última sesión)

El perfil fue rediseñado completamente con el tema Yozakura Profundo.
Verificar estado actual del README y SVGs para determinar qué falta completar.
Buscar en engram: `mem_search(query: "pendiente OR next steps OR profile", project: "p5patricio")`
