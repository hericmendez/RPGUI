## `docs/10-npm-publishing.md`

```markdown
# NPM Publishing

## Before Publishing

Verify:

- package name;
- package version;
- package description;
- repository metadata;
- license;
- README;
- exports;
- JavaScript;
- TypeScript declarations;
- CSS;
- assets.

## Clean Installation

Test the generated package in a clean project.

At minimum test:

- npm;
- pnpm;
- Yarn;
- Vite;
- Next.js.

## Versioning

Follow Semantic Versioning.

### PATCH

Bug fixes and backward-compatible corrections.

### MINOR

Backward-compatible functionality.

### MAJOR

Breaking public API changes.

## Package Inspection

Before publishing, inspect the package contents.

Do not publish:

- source artifacts that are not intended for consumers;
- internal tests;
- local configuration;
- credentials;
- `.env` files;
- private assets.

## Security

Never commit or publish:

- npm tokens;
- API keys;
- credentials;
- private registry credentials.

## Release Philosophy

A release should represent a coherent public API.

Do not publish unstable internal experiments merely because the build succeeds.
````