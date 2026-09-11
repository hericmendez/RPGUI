## `docs/01-goals-and-non-goals.md`

```markdown
# Goals and Non-Goals

## Goals

### Preserve RPGUI Identity

The project must preserve the recognizable visual characteristics of RPGUI.

This includes:

- pixel-art borders;
- frames;
- textures;
- RPG typography;
- icons;
- buttons;
- retro controls;
- visual hierarchy.

### Modern React API

The library must provide a declarative React API.

### TypeScript First

Public APIs must have strong TypeScript definitions.

### Modern Distribution

The package must be suitable for modern npm ecosystems.

### Pixel Integrity

Pixel-art assets must remain crisp and intentional.

### Accessibility

Interactive components must provide appropriate keyboard and assistive-technology behavior.

### SSR Compatibility

The library must work with SSR environments such as Next.js.

### Themeability

The architecture must allow multiple themes and customization.

### Extensibility

New RPG-oriented components should be possible without rewriting the foundation.

### Framework Independence

The package should not depend on a specific application framework.

---

# Non-Goals

The project is not intended to:

- reproduce the original DOM;
- reproduce the original CSS class API;
- preserve obsolete browser hacks;
- preserve legacy JavaScript initialization;
- depend on jQuery;
- depend on Gulp;
- require Tailwind;
- become a general-purpose UI framework;
- become a game engine;
- provide application state management;
- provide backend services;
- reproduce every historical implementation detail;
- prioritize old browser compatibility over modern behavior.
````

---