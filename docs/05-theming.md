
## `docs/05-theming.md`

```markdown
# Theming

## Objective

RPGUI Modern must support multiple visual themes without requiring component rewrites.

Themes should control visual tokens rather than component behavior.

## Semantic Tokens

Prefer semantic variables such as:

```css
--rpg-color-primary
--rpg-color-secondary
--rpg-color-background
--rpg-color-surface
--rpg-color-text
--rpg-color-muted
--rpg-color-danger
--rpg-color-success
--rpg-border-width
--rpg-font-body
--rpg-font-heading
````

## Initial Theme

The first theme should reproduce the original RPGUI visual identity as closely as practical.

This theme is the visual reference baseline.

## Future Themes

Potential future themes:

* Classic;
* Golden;
* Stone;
* Wood;
* Dark Fantasy;
* Arcane;
* Sci-Fi.

These themes do not all need to be implemented initially.

## Customization

Future versions may expose:

* custom color tokens;
* typography;
* border styles;
* spacing;
* component variants;
* custom assets.

Customization must not require consumers to fork the library.

## Architecture Rule

Themes must not be hard-coded into component logic.

A component should consume semantic design tokens.

## Provider vs CSS

The project should use the simplest mechanism that satisfies the requirements.

Do not introduce a React provider if CSS variables and classes provide the same functionality cleanly.

````