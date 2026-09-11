## `docs/08-nextjs-and-ssr.md`

```markdown
# Next.js and SSR

## Objective

RPGUI Modern must be usable in server-rendered React applications.

The primary example is Next.js.

## SSR Safety

Static components should render without browser APIs.

Avoid accessing:

```ts
window
document
navigator
localStorage
````

during server rendering.

## Client Components

Interactive components may require client-side behavior.

Only components that actually require browser-side behavior should become client components.

Do not unnecessarily propagate `"use client"` through the component tree.

## Hydration

Server and client rendering must remain deterministic.

Avoid:

* random IDs generated during render;
* timestamps generated during render;
* viewport-dependent markup during initial render;
* browser-only measurements during server render.

Use React-supported deterministic mechanisms where appropriate.

## Next.js Dependency

Next.js must not become a runtime dependency.

The library remains framework-agnostic.

## Validation

The package should eventually be tested in a real Next.js consumer application.

The test must verify:

* installation;
* CSS loading;
* SSR;
* hydration;
* interactive components;
* assets;
* TypeScript.

````
