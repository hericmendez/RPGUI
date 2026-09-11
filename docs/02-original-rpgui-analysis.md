## `docs/02-original-rpgui-analysis.md`

````markdown
# Original RPGUI Analysis

## Purpose

This document defines how the original RPGUI implementation should be analyzed before modern equivalents are implemented.

The original source is located at:

```text
original/RPGUI/
````

It is the primary local reference for the project's historical behavior and visual identity.

## Analysis Rules

For every significant original feature, determine:

1. What does the feature do?
2. What visual characteristics define it?
3. Which assets does it use?
4. Which DOM elements does it expect?
5. Which JavaScript behavior does it require?
6. Does it depend on global state?
7. Does it depend on imperative initialization?
8. How does it behave responsively?
9. What accessibility problems exist?
10. What should the modern React equivalent look like?

## Feature Classification

Each feature should be classified as one of:

### Preserve

The behavior and visual result should remain substantially unchanged.

### Modernize

The behavior remains, but the implementation changes.

### Redesign API

The concept remains, but the API becomes React-oriented.

### Conceptual Evolution

The original concept is expanded for modern use cases.

### Legacy Detail

An implementation detail that should not be reproduced.

### Legacy Defect

A known limitation or bug that should not be preserved.

### Future Enhancement

A useful concept that belongs to a later phase.

## Analysis Matrix

A feature analysis should eventually be recorded using a matrix similar to:

| Original Feature | Modern Component | Visual Fidelity | Behavior | API Strategy           | Classification       |
| ---------------- | ---------------- | --------------- | -------- | ---------------------- | -------------------- |
| Container        | RPGContainer     | High            | Preserve | React props            | Modernize            |
| Framed container | RPGFrame         | High            | Preserve | React composition      | Modernize            |
| Button           | RPGButton        | High            | Preserve | Native button          | Redesign API         |
| Slider           | RPGSlider        | High            | Preserve | Native range semantics | Modernize            |
| Progress bar     | RPGProgressBar   | High            | Expand   | React props            | Conceptual Evolution |

The exact mapping must be based on the actual contents of `original/RPGUI/`.

## Important Rule

Do not begin by copying the original CSS or JavaScript.

First understand the intended result.

Then determine how that result should be implemented using modern web technologies.

````