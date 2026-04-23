# 🔄 actualizar-proyecto

Claude Code skill que sincroniza toda la documentación de un proyecto (CLAUDE.md global, CLAUDE.md del proyecto, memorias, scripts) al cierre de una sesión de trabajo.

## ✨ Qué hace

- Detecta qué cambió en la sesión (decisiones, nombres, rutas, feedback, roadmap).
- Actualiza `CLAUDE.md` global y `CLAUDE.md` del proyecto con la información relevante.
- Sincroniza memorias (`project_*.md`, `feedback_*.md`) y el índice `MEMORY.md`.
- Revisa scripts (`.sh`, `.py`, `.command`) y configs (`.plist`) cuando cambió un nombre o ruta, y propaga los cambios.
- Crea un commit local descriptivo en español (nunca hace push automático).
- Entrega un resumen final en tabla con qué archivo se tocó y qué cambió.

## 🎯 Casos de uso

- Cerrar una sesión de trabajo larga sin perder decisiones en el olvido.
- Propagar un cambio de nombre o ruta de proyecto sin buscar a mano dónde quedó hardcodeado.
- Mantener las memorias del asistente alineadas con el estado real del proyecto.
- Dejar la documentación lista para que el próximo arranque tenga contexto completo.

## 📋 Requisitos

- [Claude Code](https://docs.claude.com/claude-code) instalado.
- Estructura de proyecto tipo `~/Documents/CLAUDE/` con memorias en `~/.claude/projects/.../memory/`. La skill está pensada para ese layout — si lo usas distinto, adapta las rutas del `SKILL.md`.

## 🚀 Instalación

```bash
git clone https://github.com/abgarciafdz/actualizar-proyecto.git
cd actualizar-proyecto
./install.sh
```

El instalador copia `SKILL.md` a `~/.claude/skills/actualizar-proyecto/` y deja la skill disponible como comando.

## 💻 Uso

Desde Claude Code, al terminar una sesión de trabajo:

```
/actualizar-proyecto
```

Claude identifica el proyecto, detecta los cambios de la sesión, actualiza documentación y memorias, hace commit local y muestra un resumen.

## 📄 Licencia

MIT — ver [LICENSE](LICENSE).
