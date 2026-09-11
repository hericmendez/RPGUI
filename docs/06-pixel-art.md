## `docs/06-pixel-art.md`

```markdown
# Pixel Art

## Why This Matters

Pixel art is not decorative polish in RPGUI Modern.

It is part of the product identity.

A technically correct component that renders blurry pixel art is considered visually incorrect.

## Rendering Principles

Pay attention to:

- source image dimensions;
- rendered dimensions;
- integer scaling;
- device pixel ratio;
- CSS transforms;
- fractional positions;
- background scaling;
- interpolation;
- sprite dimensions.

## `image-rendering`

Where appropriate, use:

```css
image-rendering: pixelated;
````

or another appropriate browser-supported strategy.

However, this property alone does not guarantee perfect rendering.

## Avoid Fractional Scaling

Be careful with:

```css
transform: scale(1.25);
```

or dimensions that produce fractional pixel boundaries.

Pixel assets should preferably be rendered at integer-friendly scales.

## Frames

Frame rendering may use:

* border-image;
* layered backgrounds;
* pseudo-elements;
* nine-slice-like techniques;
* dedicated frame primitives.

The implementation should be chosen based on visual quality and maintainability.

## Testing

Pixel-art components should be visually checked at:

* 100% browser zoom;
* browser zoom levels;
* high-DPI displays;
* responsive widths;
* small and large component sizes.

## Important

Do not replace pixel-art assets with generic CSS gradients merely because the CSS implementation is easier.

The visual language is a core requirement.

````
