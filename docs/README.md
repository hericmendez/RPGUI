````
## `docs/README.md`

````markdown
# RPGUI Modern Documentation

This directory contains the architectural, technical, and product documentation for RPGUI Modern.

The documentation exists to keep implementation decisions consistent across contributors and coding agents.

## Documentation Index

### Project

- [Project Overview](./00-project-overview.md)
- [Goals and Non-Goals](./01-goals-and-non-goals.md)
- [Original RPGUI Analysis](./02-original-rpgui-analysis.md)

### Architecture

- [Architecture](./03-architecture.md)
- [Component System](./04-component-system.md)
- [Theming](./05-theming.md)
- [Pixel Art](./06-pixel-art.md)
- [Accessibility](./07-accessibility.md)
- [Next.js and SSR](./08-nextjs-and-ssr.md)

### Distribution

- [Packaging](./09-packaging.md)
- [NPM Publishing](./10-npm-publishing.md)

### Quality

- [Testing](./11-testing.md)

### Migration

- [Migration from Original RPGUI](./12-migration-from-rpgui.md)

### Planning

- [Roadmap](./13-roadmap.md)
- [Development Workflow](./14-development-workflow.md)
- [Design Decisions](./15-design-decisions.md)

## Reading Order

For contributors and coding agents, the recommended reading order is:

1. `AGENTS.md`
2. `00-project-overview.md`
3. `01-goals-and-non-goals.md`
4. `02-original-rpgui-analysis.md`
5. `03-architecture.md`
6. The documentation relevant to the current task

## Important

The directory:

```text
original/RPGUI/
````

contains the original RPGUI implementation and must be treated as reference material.

The original implementation should be analyzed before implementing equivalent modern components.

This documentation describes the intended modern architecture.

It does not require the modern implementation to reproduce the original implementation's internal structure.
