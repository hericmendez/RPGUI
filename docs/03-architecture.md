## `docs/03-architecture.md`

```markdown
# Architecture

## Architectural Goal

The architecture should separate:

- visual primitives;
- components;
- themes;
- assets;
- interaction logic;
- package exports.

The system should remain composable and maintainable as the library grows.

## Target Stack

- React
- TypeScript
- ESM
- Vite
- Vitest
- Modern CSS

## Conceptual Layers

### 1. Primitives

Low-level visual building blocks.

Examples:

```text
RPGSurface
RPGFrame
RPGText
RPGIcon
````

### 2. Core Components

Reusable UI components.

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

### 3. RPG Components

Higher-level domain-oriented UI.

Examples:

```text
RPGHealthBar
RPGManaBar
RPGStaminaBar
RPGExperienceBar
RPGItemSlot
RPGStat
RPGCharacterCard
```

### 4. Theme Layer

Theme tokens and theme configuration.

### 5. Asset Layer

Pixel-art images, textures, icons, fonts, and other visual resources.

### 6. Public API

Only intentionally public components and utilities should be exported.

## Composition

Prefer:

```tsx
<RPGPanel>
    <RPGHeading>Character</RPGHeading>

    <RPGHealthBar
        value={72}
        max={100}
    />

    <RPGButton>
        Continue
    </RPGButton>
</RPGPanel>
```

over large monolithic components.

## Repository Structure

```text
src/
├── components/
├── primitives/
├── themes/
├── styles/
├── assets/
├── hooks/
├── utils/
└── index.ts
```

The exact organization may change as the implementation becomes clearer.

## Architectural Rule

Do not optimize for theoretical extensibility before real use cases exist.
