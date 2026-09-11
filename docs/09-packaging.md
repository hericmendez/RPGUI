
## `docs/09-packaging.md`

```markdown
# Packaging

## Intended Package

The intended package name is:

```text
@rpgui/react
````

The name must be verified before publishing.

## Installation

Consumers should be able to use:

```bash
npm install @rpgui/react
```

```bash
pnpm add @rpgui/react
```

```bash
yarn add @rpgui/react
```

## Package Contents

The package should contain:

* JavaScript;
* TypeScript declarations;
* CSS;
* required assets;
* package metadata;
* README;
* license.

## Exports

Use an explicit `exports` map.

Only intended public APIs should be exposed.

Internal modules should not become public accidentally.

## Tree Shaking

The package should support tree shaking.

Avoid unnecessary module-level side effects.

## React

React should normally be a peer dependency rather than bundled into the library.

The exact dependency strategy must be confirmed during package setup.

## Styles

The CSS distribution mechanism must be predictable.

A consumer should not need to copy CSS manually into their project.

## Assets

Assets must resolve correctly when the package is installed externally.

Do not rely on repository-relative paths that only work inside the source repository.

## Clean Consumer Test

Before release, install the package into a clean project and verify that it works as an external dependency.

````
