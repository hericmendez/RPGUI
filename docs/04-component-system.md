
## `docs/04-component-system.md`

```markdown
# Component System

## Design Principles

Public components should be:

- semantic;
- composable;
- typed;
- accessible;
- predictable.

## Naming

Public components should generally use the `RPG` prefix.

Examples:

```text
RPGButton
RPGContainer
RPGPanel
RPGInput
RPGCheckbox
RPGSelect
RPGSlider
````

## Props

Prefer semantic props:

```text
variant
size
disabled
value
defaultValue
min
max
label
animated
```

Avoid exposing implementation details.

## Variants

Variants should represent meaningful visual or semantic differences.

Example:

```tsx
<RPGButton variant="primary" />
<RPGButton variant="secondary" />
<RPGButton variant="danger" />
```

Avoid creating dozens of narrowly differentiated variants.

## Sizes

Components may expose a small predictable size system:

```text
sm
md
lg
```

The exact values should be established by the design system.

## Controlled State

Interactive components should follow React conventions.

Example:

```tsx
<RPGSlider
    value={value}
    onChange={setValue}
/>
```

## Uncontrolled State

Where appropriate:

```tsx
<RPGSlider
    defaultValue={50}
/>
```

## Composition

Prefer composition over configuration.

For example:

```tsx
<RPGPanel>
    <RPGHeading>Inventory</RPGHeading>

    <RPGInventory>
        ...
    </RPGInventory>
</RPGPanel>
```

rather than a single component with many nested configuration props.

## Native Elements

Use native HTML semantics whenever possible.

Visual customization should be layered over correct semantics.

````