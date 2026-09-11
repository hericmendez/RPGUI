## `docs/12-migration-from-rpgui.md`

```markdown
# Migration from Original RPGUI

## Philosophy

Migration is primarily visual and conceptual.

RPGUI Modern is not intended to be a drop-in replacement for the original CSS/JavaScript API.

## Original Usage

The original library uses global CSS classes and JavaScript behavior.

RPGUI Modern uses React components.

Conceptually:

```html
<div class="rpgui-container framed">
    ...
</div>
````

becomes:

```tsx
<RPGContainer variant="framed">
    ...
</RPGContainer>
```

## Do Not Copy Legacy Initialization

Consumers should not need:

```js
RPGUI.init()
```

or equivalent global initialization.

## CSS Classes

Original CSS classes should not become the primary public API.

React props and composition should replace them.

## Assets

Asset migration must respect:

* original provenance;
* licensing;
* attribution;
* visual requirements.

## Migration Documentation

As components are implemented, this document should contain a mapping table.

Example:

| Original RPGUI     | RPGUI Modern       |
| ------------------ | ------------------ |
| `.rpgui-container` | `RPGContainer`     |
| `.framed`          | `variant="framed"` |
| `.framed-golden`   | theme/variant      |
| `.rpgui-button`    | `RPGButton`        |
| `.rpgui-progress`  | `RPGProgressBar`   |

The final mapping must be based on the actual original implementation.

````