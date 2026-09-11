## `docs/15-design-decisions.md`

```markdown
# Design Decisions

This document records important architectural decisions.

The purpose is to prevent the project from repeatedly reconsidering decisions that have already been established.

---

# ADR-001 — React First

## Status

Accepted

## Decision

React is the primary public programming model.

## Reason

The goal is to provide a modern component library rather than a collection of legacy CSS classes.

React provides:

- declarative composition;
- predictable state;
- TypeScript integration;
- SSR support;
- ecosystem compatibility.

---

# ADR-002 — TypeScript First

## Status

Accepted

## Decision

The project is written in TypeScript.

## Reason

A component library benefits strongly from:

- typed props;
- typed events;
- typed themes;
- editor support;
- safer refactoring;
- discoverable APIs.

---

# ADR-003 — Original Source Is Reference Only

## Status

Accepted

## Decision

The original RPGUI source is stored under:

```text
original/RPGUI/
````

It is reference material, not runtime code.

## Reason

The original implementation is valuable for understanding the visual and behavioral identity of RPGUI.

However, directly depending on it would preserve the architectural limitations the project is intended to replace.

---

# ADR-004 — Visual Identity Over DOM Compatibility

## Status

Accepted

## Decision

Visual and conceptual compatibility takes priority over reproducing the original DOM and CSS APIs.

## Reason

The goal is to modernize the library.

Preserving old DOM structures would unnecessarily constrain:

* accessibility;
* React composition;
* SSR;
* maintainability;
* responsive behavior.

---

# ADR-005 — Pixel Art Is a Core Requirement

## Status

Accepted

## Decision

Pixel-art fidelity is treated as a functional requirement.

## Reason

Pixel art is one of the defining characteristics of RPGUI.

Blurred or incorrectly scaled assets represent a visual regression.

---

# ADR-006 — Theme System

## Status

Accepted

## Decision

The visual system must be themeable.

## Reason

The original visual identity should be preserved while allowing the library to evolve beyond one fixed appearance.

Themes should be implemented through reusable design tokens and visual primitives.

---

# ADR-007 — Accessibility Is Mandatory

## Status

Accepted

## Decision

Accessibility is part of the component definition of done.

## Reason

The modern library must improve upon the original implementation rather than reproducing historical accessibility limitations.

---

# ADR-008 — Tailwind Is Not Required

## Status

Accepted

## Decision

The library must not require Tailwind CSS.

## Reason

RPGUI Modern is a component library, not a Tailwind plugin.

Consumers should be able to use it regardless of their styling framework.

---

# ADR-009 — NPM Package

## Status

Accepted

## Decision

The intended distribution model is an npm package:

```text
@rpgui/react
```

## Reason

A published package makes the library usable across:

* React applications;
* Vite;
* Next.js;
* other React-compatible environments.

The package must remain independent of any single application repository.

---

# ADR-010 — Declarative Over Imperative APIs

## Status

Accepted

## Decision

Components should be declarative by default.

## Reason

The original RPGUI relies on legacy imperative behavior.

Modern React applications should not require global initialization or manual DOM manipulation.

---

# ADR-011 — Native Semantics Where Possible

## Status

Accepted

## Decision

Native HTML elements should be preferred when they provide the required behavior.

## Reason

Native semantics provide significant accessibility and interaction behavior for free.

The RPG visual layer should customize appearance rather than unnecessarily replace platform behavior.

````