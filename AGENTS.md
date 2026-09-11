# `AGENTS.md`

````markdown
# RPGUI Modern — OpenCode Agent Instructions

## 1. Project Identity

RPGUI Modern is a modern React/TypeScript reimplementation of the original RPGUI library.

The project aims to preserve the visual language, interaction concepts, and useful functionality of the original RPGUI while replacing its legacy implementation with a modern, composable, accessible, SSR-friendly architecture.

The original RPGUI source code is kept inside:

    original/RPGUI/

This directory is historical/reference material.

The project is NOT a direct fork or mechanical port of the original implementation.

The intended result is a modern library inspired by and derived from the original RPGUI design and behavior.

---

# 2. Core Objective

The project must provide a modern RPG-oriented UI library for React applications while preserving the recognizable identity of the original RPGUI.

The library should provide:

- pixel-art visual language;
- RPG-style containers and frames;
- decorative borders and textures;
- RPG-style typography;
- pixel-art icons;
- RPG-style buttons;
- form controls;
- checkboxes and radio buttons;
- dropdown/select controls;
- listbox controls;
- sliders;
- progress bars;
- RPG-specific resource bars;
- customizable themes;
- configurable colors and sizes;
- accessible interactions;
- modern React APIs;
- TypeScript support;
- SSR compatibility;
- Next.js compatibility;
- Vite compatibility;
- tree-shakable package exports;
- npm/pnpm/Yarn compatibility.

The project should feel like the evolution of RPGUI, not like a generic component library with a fantasy skin applied afterward.

---

# 3. Product Philosophy

The fundamental principle of this project is:

> Preserve the RPGUI identity, modernize the technology.

The original implementation is valuable because of its visual language and the interaction patterns it established.

Its implementation architecture, however, belongs to an older generation of web development.

Therefore:

- preserve the intended visual result;
- preserve meaningful interaction behavior;
- preserve useful component concepts;
- redesign the implementation where necessary;
- redesign the public API for React;
- improve accessibility;
- improve SSR compatibility;
- improve maintainability;
- improve extensibility;
- avoid blindly reproducing legacy implementation details.

Visual and conceptual compatibility is more important than DOM or CSS-class compatibility.

---

# 4. Original RPGUI Reference

The original RPGUI implementation lives at:

    original/RPGUI/

Treat this directory as the historical reference implementation.

It exists so that the modern implementation can be compared against the original.

## 4.1 Read-only rule

Do NOT modify files inside:

    original/RPGUI/

unless the user explicitly requests an archival/reference change.

The original source must remain available for comparison.

## 4.2 Runtime isolation

Do NOT import runtime code directly from the original implementation.

Do NOT make the new package depend on the original project's JavaScript, CSS, build system, or runtime.

The original project is reference material, not a runtime dependency.

## 4.3 Before implementing a component

Before implementing a modern component that corresponds to an original RPGUI feature:

1. inspect the original implementation;
2. identify the intended visual behavior;
3. identify the intended interaction behavior;
4. identify the assets involved;
5. identify DOM assumptions;
6. identify JavaScript behavior;
7. identify responsive behavior;
8. identify potential accessibility problems;
9. identify legacy implementation details;
10. determine the appropriate modern equivalent.

Do not copy code merely because it exists in the original project.

---

# 5. Compatibility Philosophy

The project does NOT aim for complete source compatibility with the original RPGUI.

For example, the original pattern:

```html
<div class="rpgui-container framed">
    ...
</div>
````

does not need to remain the primary API.

The modern API should instead be React-oriented:

```tsx
<RPGContainer variant="framed">
    ...
</RPGContainer>
```

The goal is:

* visual compatibility;
* conceptual compatibility;
* behavioral compatibility where appropriate.

The goal is NOT:

* identical DOM;
* identical CSS classes;
* identical JavaScript APIs;
* identical initialization process.

---

# 6. Primary Technology Direction

The project should be built around:

* React;
* TypeScript;
* modern ECMAScript;
* ESM;
* modern CSS;
* Vite;
* Vitest.

The project should avoid unnecessary framework-specific dependencies.

The package should remain usable from:

* Vite;
* Next.js;
* Remix;
* Astro with React;
* standard React applications;
* applications using CSS Modules;
* applications using Tailwind;
* applications not using Tailwind.

Tailwind CSS must NOT be a requirement.

---

# 7. React Architecture

React is the primary public programming model.

Components should be declarative.

Prefer:

```tsx
<RPGButton variant="primary">
    Start Game
</RPGButton>
```

over:

```ts
RPGUI.init();
RPGUI.create(...);
```

or:

```ts
document.querySelector(...);
RPGUI.initialize(...);
```

The normal component lifecycle must be controlled by React.

Imperative APIs may exist when genuinely useful, but they must not be required for ordinary component usage.

---

# 8. Component Design

Components should be:

* composable;
* predictable;
* typed;
* accessible;
* framework-friendly;
* independently testable;
* visually consistent.

Prefer small reusable primitives over giant components with dozens of unrelated props.

For example:

```tsx
<RPGPanel>
    <RPGHeading>Inventory</RPGHeading>

    <RPGButton>
        Use Item
    </RPGButton>
</RPGPanel>
```

Avoid creating one component that attempts to control every possible RPG UI scenario.

---

# 9. Naming

Public components should normally use the `RPG` prefix.

Examples:

```text
RPGButton
RPGContainer
RPGPanel
RPGInput
RPGCheckbox
RPGRadio
RPGSelect
RPGListbox
RPGSlider
RPGProgressBar
RPGHealthBar
RPGManaBar
RPGStaminaBar
RPGExperienceBar
```

The exact component naming scheme may evolve, but public naming should remain predictable and consistent.

---

# 10. Public API Principles

Public APIs must prioritize:

1. semantic meaning;
2. usability;
3. accessibility;
4. consistency;
5. type safety;
6. extensibility.

Prefer semantic props such as:

```tsx
variant
size
disabled
value
max
min
label
animated
theme
```

Avoid exposing internal implementation details.

For example, avoid APIs such as:

```tsx
backgroundImage="frame_corner_03.png"
borderSliceSize={17}
internalTextureMode="legacy"
```

unless there is a deliberate and documented reason to expose them.

Internal asset implementation should remain internal whenever possible.

---

# 11. Controlled and Uncontrolled Components

Interactive form components should follow established React conventions.

Where appropriate, components should support:

### Controlled usage

```tsx
<RPGSelect
    value={value}
    onChange={setValue}
/>
```

### Uncontrolled usage

```tsx
<RPGSelect
    defaultValue="warrior"
/>
```

Do not create unusual state-management conventions without a strong reason.

---

# 12. Native HTML Semantics

Prefer native HTML elements whenever possible.

For example:

* use `<button>` for buttons;
* use `<input>` for text input;
* use `<input type="checkbox">` for checkboxes;
* use `<input type="radio">` for radio controls;
* use `<input type="range">` where appropriate;
* use `<select>` when a native select provides the required behavior.

Do not replace native semantics with `<div>` elements merely because the visual design is custom.

If a fully custom interaction is required, reproduce the expected keyboard and accessibility behavior explicitly.

---

# 13. Accessibility

Accessibility is a first-class requirement.

Visual fidelity must never be used as justification for knowingly inaccessible behavior.

Interactive components must consider:

* keyboard navigation;
* focus management;
* visible focus;
* disabled states;
* labels;
* descriptions;
* screen readers;
* semantic HTML;
* ARIA;
* reduced motion;
* contrast;
* touch interaction.

Use ARIA only when necessary.

Do not add redundant ARIA attributes when native HTML semantics already provide the required information.

---

# 14. Keyboard Interaction

Interactive components must follow familiar web conventions.

Examples:

### Buttons

* Enter;
* Space.

### Dialogs

* Escape;
* focus management.

### Select/Listbox

Depending on implementation:

* Arrow keys;
* Enter;
* Escape;
* Home;
* End.

### Sliders

Follow normal range-input expectations whenever possible.

Do not invent keyboard interactions unless the component requires behavior that cannot reasonably follow native conventions.

---

# 15. Focus

All interactive components must have a visible focus state.

The focus state must remain compatible with the RPG visual identity.

Do not remove:

```css
outline: none;
```

without providing an accessible replacement.

Focus indicators should be clearly distinguishable from ordinary visual decoration.

---

# 16. Reduced Motion

Animations must respect:

```css
@media (prefers-reduced-motion: reduce)
```

Animations should be disabled, shortened, or simplified when the user requests reduced motion.

This is particularly important for:

* progress bars;
* damage indicators;
* healing effects;
* hover animations;
* transitions;
* dialogs;
* interactive controls.

---

# 17. Pixel Art

Pixel-art rendering is a core product requirement.

Pixel art must remain visually crisp.

Pay particular attention to:

* `image-rendering`;
* integer scaling;
* fractional scaling;
* fractional transforms;
* browser interpolation;
* device pixel ratio;
* background-image scaling;
* sprite dimensions;
* CSS transforms;
* animation positions;
* responsive layouts.

Avoid knowingly introducing blur.

---

# 18. Pixel Scaling

Do not assume that:

```css
image-rendering: pixelated;
```

alone solves every pixel-art problem.

Pixel-perfect rendering depends on:

* source image dimensions;
* rendered dimensions;
* scaling ratios;
* transforms;
* browser behavior;
* device pixel ratio.

Whenever possible, prefer integer-friendly scaling.

Be particularly careful with:

```css
transform: scale(...)
```

and fractional dimensions.

---

# 19. Pixel-Art Assets

Assets should be treated as first-class project resources.

Do not casually replace original artwork with generic alternatives.

Before replacing an original asset:

1. determine why it exists;
2. determine whether it is public-domain, licensed, or project-specific;
3. preserve attribution requirements;
4. determine whether the visual role can be reproduced technically;
5. document provenance where appropriate.

Do not remove credits or licensing information from inherited assets.

---

# 20. Frames and Borders

Frames are one of the most important parts of the RPGUI visual identity.

When modernizing frame rendering, consider:

* CSS border techniques;
* pseudo-elements;
* layered backgrounds;
* nine-slice techniques;
* `border-image`;
* multiple background layers;
* dedicated frame primitives.

Do not choose a technique solely because it is easiest to implement.

The rendered result must remain visually faithful and responsive.

---

# 21. Themes

The visual system must support themes.

The original RPGUI aesthetic should be represented as a first-class theme rather than hard-coded into every component.

The architecture should make it possible to add future themes without rewriting component logic.

Potential future themes include:

* Classic;
* Golden;
* Stone;
* Wood;
* Dark Fantasy;
* Arcane;
* Sci-Fi.

These do not all need to exist in the first release.

The architecture should simply avoid preventing them.

---

# 22. Design Tokens

Prefer semantic design tokens.

Examples:

```css
--rpg-color-primary
--rpg-color-secondary
--rpg-color-surface
--rpg-color-background
--rpg-color-text
--rpg-color-muted
--rpg-color-danger
--rpg-color-success
--rpg-border-width
--rpg-radius
--rpg-font-body
--rpg-font-heading
--rpg-spacing
```

Do not scatter hard-coded theme values throughout component styles.

Components should consume semantic tokens rather than directly depending on one specific theme.

---

# 23. Theme API

The exact theme API is an architectural decision that must be documented before implementation.

Possible approaches include:

```tsx
<RPGThemeProvider theme="classic">
    ...
</RPGThemeProvider>
```

or:

```tsx
<RPGProvider theme={classicTheme}>
    ...
</RPGProvider>
```

or CSS-based theme selection.

Do not introduce a provider merely because it is fashionable.

If CSS variables are sufficient, prefer the simpler architecture.

---

# 24. RPG Resource Bars

Progress/resource bars are an important modernization opportunity.

The project should support a reusable progress abstraction capable of representing:

* health;
* mana;
* stamina;
* experience;
* generic progress.

Potential public components:

```text
RPGProgressBar
RPGHealthBar
RPGManaBar
RPGStaminaBar
RPGExperienceBar
```

Specialized bars should reuse shared implementation rather than duplicate rendering logic.

---

# 25. Resource Bar Features

Where appropriate, resource bars may support:

* current value;
* maximum value;
* percentage;
* label;
* numeric display;
* animated transitions;
* delayed damage visualization;
* healing visualization;
* custom variants;
* custom colors through theme tokens;
* reduced-motion behavior.

Example:

```tsx
<RPGHealthBar
    value={72}
    max={100}
    showValue
/>
```

Do not implement complex animation before the static rendering model is stable.

---

# 26. State and Animation

Animation should never become a requirement for basic component correctness.

A component should have a correct static state first.

Then animation can be layered on top.

For example:

1. render current value;
2. establish correct geometry;
3. establish theme;
4. establish accessibility;
5. add transition;
6. add optional delayed-value effects;
7. add reduced-motion behavior.

Do not allow animation logic to obscure basic component behavior.

---

# 27. Server-Side Rendering

The package must be SSR-safe by default.

Components that do not need browser APIs must render correctly during SSR.

Avoid accessing:

```ts
window
document
localStorage
navigator
```

during module initialization or server rendering.

Browser-specific APIs must only be used where appropriate.

---

# 28. Next.js

The package must work with Next.js.

Do not make Next.js a runtime dependency.

Static components should not unnecessarily require:

```tsx
"use client";
```

Only components that genuinely require client-side behavior should need a client boundary.

Avoid turning an entire component tree into a client component because one optional enhancement requires browser APIs.

---

# 29. Hydration

Components must produce deterministic server/client output where SSR is supported.

Avoid generating different markup between server and client.

Be careful with:

* random IDs;
* timestamps;
* browser-dependent measurements;
* viewport-dependent rendering;
* random animation state;
* generated class names.

Use React's supported ID mechanisms where appropriate.

---

# 30. Package Name

The intended package name is:

```text
@rpgui/react
```

Before publishing, verify npm availability.

Do not assume the package name is available merely because it is the intended name.

If the name is unavailable, stop and discuss alternatives rather than silently choosing a different package identity.

---

# 31. Package Managers

The published package must work with:

```bash
npm install @rpgui/react
```

```bash
pnpm add @rpgui/react
```

```bash
yarn add @rpgui/react
```

The package manager is a consumer choice.

Do not create package-manager-specific runtime assumptions.

---

# 32. Package Format

The package should provide:

* ESM JavaScript;
* TypeScript declarations;
* styles;
* required assets;
* explicit package exports.

Use an explicit `exports` map.

Do not accidentally expose internal source files as part of the public API.

---

# 33. Tree Shaking

The package should be designed for tree shaking.

Avoid unnecessary side effects.

If a module has side effects, document and configure them correctly.

Do not import every component into every consumer bundle merely because it simplifies internal organization.

---

# 34. CSS Distribution

The final CSS distribution strategy must be deliberate.

The consumer should have a predictable way to load the library's styles.

Possible patterns include:

```tsx
import "@rpgui/react/styles.css";
```

or component-level style imports.

Choose one primary supported approach and document it.

Do not require consumers to copy CSS manually.

---

# 35. Tailwind Compatibility

Tailwind is optional.

The library must not require Tailwind.

Do not build component behavior around Tailwind-generated classes.

The library's own styling system must work independently.

It is acceptable for consumers to place RPGUI components inside Tailwind layouts.

---

# 36. Dependencies

Keep dependencies minimal.

Before adding a dependency, ask:

1. Is it actually necessary?
2. Can the platform provide the functionality?
3. Can React provide the functionality?
4. Would a small internal utility be simpler?
5. What is the bundle-size impact?
6. Does it affect SSR?
7. Does it affect accessibility?
8. Does it complicate installation?

Do not add dependencies simply because they are popular.

---

# 37. No Legacy Build System

Do not reproduce the original build architecture.

Do not introduce:

* Gulp;
* jQuery;
* legacy Sass pipelines;
* obsolete browser polyfills;
* imperative global initialization.

Modern tooling should replace the original build system.

---

# 38. Component Categories

The project should conceptually organize components into layers.

### Primitives

Low-level reusable building blocks.

Examples:

```text
RPGSurface
RPGFrame
RPGText
RPGIcon
```

### Core UI

General interface controls.

Examples:

```text
RPGButton
RPGInput
RPGCheckbox
RPGRadio
RPGSelect
RPGListbox
RPGSlider
```

### Layout / Containers

Examples:

```text
RPGContainer
RPGPanel
RPGCard
RPGDialog
```

### RPG Components

Examples:

```text
RPGHealthBar
RPGManaBar
RPGStaminaBar
RPGExperienceBar
RPGItemSlot
RPGInventory
RPGStat
RPGCharacterCard
```

Do not implement all categories at once.

---

# 39. Advanced Components

Advanced RPG components may eventually include:

* tooltip;
* dialog;
* inventory slot;
* inventory grid;
* character card;
* stat display;
* equipment slot;
* quest/status display;
* notification;
* RPG menu;
* tab system.

These are future extensions unless explicitly prioritized.

Do not allow future component ideas to overcomplicate the initial architecture.

---

# 40. Testing

Use Vitest for unit and component behavior tests.

Tests should focus on observable behavior.

Good:

```text
button can be activated with keyboard
disabled button cannot be activated
progress bar exposes correct value
select changes value correctly
component renders accessible label
```

Avoid tests that merely verify internal implementation details.

Bad:

```text
component calls internalFunction()
specific private class exists
specific internal state variable equals X
```

---

# 41. Accessibility Testing

Where appropriate, tests should verify:

* semantic roles;
* accessible names;
* keyboard interaction;
* disabled behavior;
* focus;
* form values;
* ARIA state.

Prefer queries that resemble how users and assistive technologies interact with the interface.

---

# 42. SSR Testing

Representative SSR-compatible components should be tested in an SSR-like environment.

At minimum, ensure that static components do not accidentally access browser globals during render.

---

# 43. Visual Testing

Visual regression testing may be introduced later.

Before introducing a visual regression framework, establish:

* representative components;
* reference themes;
* stable rendering;
* deterministic assets;
* predictable viewport sizes.

Do not introduce visual snapshot infrastructure before the visual system is sufficiently stable.

---

# 44. Documentation

Every public component should eventually document:

* purpose;
* basic usage;
* props;
* variants;
* accessibility;
* styling;
* theming;
* limitations;
* migration notes when applicable.

Keep the main README focused on onboarding.

Put architectural decisions in:

```text
docs/
```

---

# 45. Development Workflow

Before implementing a significant feature:

1. read this file;
2. read the relevant documentation under `docs/`;
3. inspect the original implementation;
4. identify the desired behavior;
5. identify visual requirements;
6. identify accessibility requirements;
7. identify SSR implications;
8. identify public API implications;
9. implement the smallest coherent change;
10. test;
11. visually verify;
12. document meaningful decisions.

---

# 46. Small Incremental Changes

Prefer incremental implementation.

Do not combine unrelated changes such as:

* component implementation;
* complete theme rewrite;
* package restructure;
* testing framework migration;
* documentation rewrite;

in one task unless explicitly requested.

Large architectural changes require explicit reasoning.

---

# 47. Visual Verification

A component is not complete merely because its tests pass.

Visual verification is required for components whose purpose is primarily visual.

Check:

* normal size;
* small size;
* large size;
* responsive layout;
* high-DPI display;
* browser zoom;
* dark/light theme where applicable;
* hover;
* focus;
* active;
* disabled;
* loading;
* animation;
* reduced motion.

Pixel-art components must receive particular attention.

---

# 48. Definition of Done

A public component is considered complete when applicable:

* TypeScript compiles;
* tests pass;
* public API is typed;
* accessibility has been addressed;
* visual rendering has been verified;
* SSR/client boundaries are correct;
* styles are included correctly;
* assets are correctly packaged;
* documentation exists;
* no unnecessary dependency was introduced;
* package exports remain valid.

Rendering something on screen is NOT sufficient.

---

# 49. Change Discipline

Before changing architecture, determine whether the change affects:

* public API;
* package exports;
* themes;
* assets;
* component hierarchy;
* CSS architecture;
* SSR behavior;
* build configuration;
* dependency strategy.

If it does, document the reasoning before implementation.

Do not silently redesign the architecture while implementing an unrelated component.

---

# 50. Decision Hierarchy

When requirements conflict, prioritize:

1. correctness;
2. security;
3. accessibility;
4. framework/runtime compatibility;
5. public API stability;
6. visual fidelity;
7. performance;
8. bundle size;
9. implementation convenience.

Implementation convenience is never sufficient justification for preserving a known defect.

---

# 51. Legacy Defects

Do not reproduce a known legacy defect merely because it exists in the original RPGUI.

Examples include:

* blurry rendering;
* inaccessible controls;
* global DOM assumptions;
* hydration incompatibility;
* unnecessary browser requirements;
* broken keyboard behavior;
* obsolete browser workarounds.

If a legacy behavior is intentionally changed, document the change.

---

# 52. Original Feature Classification

When analyzing the original library, classify each feature into one of these categories:

### Preserve

Behavior and appearance should remain substantially unchanged.

### Modernize

The behavior remains, but the implementation is replaced.

### Redesign API

The concept remains, but the public API is redesigned for React.

### Conceptual Evolution

The original concept is retained but expanded for modern applications.

### Legacy Detail

The behavior is specific to the old architecture and should not be reproduced.

### Legacy Defect

The behavior should explicitly NOT be reproduced.

### Future Enhancement

A useful idea exists but should not block the initial implementation.

---

# 53. Avoid Premature Abstraction

Do not create generalized abstractions before at least two or three real use cases demonstrate the need.

A component abstraction should emerge from actual requirements.

Avoid:

```text
GenericUniversalRPGThing
ConfigurableMegaComponent
AbstractVisualPrimitiveManager
```

unless there is a concrete reason.

Prefer simple, composable abstractions.

---

# 54. Public API Stability

Once a component is publicly documented and released, changing its API requires consideration of backward compatibility.

Before removing or renaming a public API:

1. determine whether the package has been released;
2. determine the semantic version impact;
3. update documentation;
4. provide migration guidance when necessary.

Do not break public APIs casually during internal refactoring.

---

# 55. Semantic Versioning

The package should follow Semantic Versioning.

Conceptually:

```text
PATCH
bug fixes

MINOR
backward-compatible features

MAJOR
breaking API changes
```

Do not publish arbitrary versions without considering compatibility.

---

# 56. Publishing Safety

Never commit:

* npm tokens;
* API keys;
* credentials;
* `.env` secrets;
* private registry credentials.

Before publishing:

* inspect package contents;
* verify package exports;
* verify README;
* verify license;
* verify assets;
* verify TypeScript declarations;
* test installation in a clean project.

---

# 57. Consumer Validation

Before a release is considered stable, test the package from an external consumer project.

At minimum verify:

```text
Vite + React
Next.js
npm
pnpm
Yarn
```

The library should behave as a real external dependency, not merely as source code inside its own repository.

---

# 58. Documentation Authority

When documentation and implementation disagree:

1. determine whether the implementation is intentional;
2. determine whether the documentation is outdated;
3. do not silently choose one;
4. update the appropriate source;
5. document architectural changes.

The documentation must evolve together with the project.

---

# 59. Repository Structure

The expected high-level structure is:

```text
rpgui-modern/
├── original/
│   └── RPGUI/
│
├── src/
│   ├── components/
│   ├── primitives/
│   ├── themes/
│   ├── styles/
│   ├── assets/
│   ├── hooks/
│   ├── utils/
│   └── index.ts
│
├── docs/
├── examples/
├── tests/
│
├── AGENTS.md
├── README.md
├── LICENSE
├── package.json
├── tsconfig.json
├── vite.config.ts
└── vitest.config.ts
```

The exact structure may evolve.

Do not restructure the repository without architectural justification.

---

# 60. Final Rule

The agent must always remember:

> This is not an exercise in copying old code.
>
> This is an exercise in preserving what made RPGUI good while rebuilding it for the modern web.

When uncertain, inspect the original implementation, inspect the relevant architectural documentation, identify the actual user-facing behavior, and choose the smallest modern implementation that preserves it.

````
