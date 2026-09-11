## `docs/14-development-workflow.md`

````markdown
# Development Workflow

## Before Coding

Before implementing a feature:

1. read `AGENTS.md`;
2. read relevant documentation;
3. inspect the original implementation;
4. understand the desired behavior;
5. identify affected components;
6. identify accessibility requirements;
7. identify SSR requirements;
8. identify package/API implications.

## During Coding

Prefer:

- small changes;
- focused components;
- typed APIs;
- semantic HTML;
- reusable primitives;
- minimal dependencies.

Avoid unrelated refactoring.

## After Coding

Run appropriate:

```text
typecheck
lint
tests
build
````

Then visually verify the component.

## Visual Verification

Check:

* default state;
* hover;
* focus;
* active;
* disabled;
* small;
* medium;
* large;
* responsive behavior;
* high-DPI behavior;
* animations;
* reduced motion.

## Documentation

Update documentation when a change affects:

* public API;
* architecture;
* theme system;
* asset handling;
* package behavior;
* migration;
* design decisions.

## Incremental Development

A good implementation sequence is:

```text
behavior
↓
visual foundation
↓
accessibility
↓
tests
↓
animation
↓
documentation
```

Do not start with animation or advanced abstraction before the basic component is correct.

## Architectural Changes

If a task requires changing:

* package architecture;
* styling architecture;
* theme architecture;
* asset strategy;
* public API;
* build system;

document the decision before implementing it.

## Agent Discipline

OpenCode should not silently redesign unrelated parts of the project.

If a task exposes a broader architectural problem:

1. report it;
2. explain its impact;
3. propose a solution;
4. wait for explicit authorization if it is outside the task scope.

````
