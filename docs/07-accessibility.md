## `docs/07-accessibility.md`

```markdown
# Accessibility

Accessibility is a core requirement of RPGUI Modern.

The RPG aesthetic must not come at the expense of usable interaction.

## Semantic HTML

Prefer native elements:

```html
<button>
<input>
<select>
<input type="checkbox">
<input type="radio">
<input type="range">
````

when they provide the required behavior.

## Keyboard

Interactive components must support expected keyboard behavior.

Examples:

* buttons: Enter and Space;
* dialogs: Escape;
* sliders: Arrow keys;
* custom lists: expected navigation keys.

## Focus

All interactive controls must have a visible focus state.

Do not remove focus indicators without providing an equivalent.

## Labels

Inputs must have accessible labels.

Prefer:

```tsx
<label>
    Character Name
    <RPGInput />
</label>
```

or an equivalent accessible relationship.

## ARIA

Use ARIA when native semantics are insufficient.

Do not add redundant ARIA.

## Disabled State

Disabled controls must communicate their state both visually and semantically.

## Reduced Motion

Animations must respect:

```css
@media (prefers-reduced-motion: reduce)
```

## Contrast

Text and important interactive states must remain sufficiently distinguishable.

The visual theme should be adjusted when necessary rather than knowingly shipping unreadable text.

## Accessibility and Visual Fidelity

When visual fidelity and accessibility appear to conflict, find a solution that preserves both.

Do not treat accessibility as optional polish.
