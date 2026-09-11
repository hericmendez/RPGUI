## `docs/11-testing.md`

````markdown
# Testing

## Test Framework

The project should use Vitest.

## Philosophy

Tests should verify observable behavior rather than implementation details.

Prefer:

```text
user can activate button
keyboard navigation works
value changes correctly
disabled state prevents interaction
accessible name exists
````

over:

```text
private function was called
specific internal state exists
specific internal class exists
```

## Component Tests

Public interactive components should have tests covering relevant:

* rendering;
* props;
* controlled state;
* uncontrolled state;
* keyboard interaction;
* disabled state;
* boundary values;
* accessibility behavior.

## Progress Components

Test:

* minimum values;
* maximum values;
* values above maximum;
* values below minimum;
* percentage calculation;
* labels;
* animation configuration;
* reduced motion behavior.

## SSR

Static components should be tested in SSR-compatible conditions.

## Visual Regression

Visual regression testing may be introduced later.

Before doing so, establish stable reference cases for:

* themes;
* component sizes;
* states;
* pixel-art rendering.

## Consumer Tests

Eventually maintain a small external consumer fixture.

It should test the actual published package shape rather than importing source files directly.

````