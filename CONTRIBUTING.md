# Contributing Guidelines

Thanks for considering contributing!

## Workflow
- Fork the repo and create feature branches from `main`.
- Follow Conventional Commits:
  - `feat: ...`, `fix: ...`, `chore: ...`, `docs: ...`, `refactor: ...`
- Add tests if applicable. Keep PRs focused and small.
- Ensure PHP 7.4–8.3 compatibility.

## Coding style
- PHP: PSR-12 (tabs/spaces per `.editorconfig`).
- No direct `.htaccess` writes from PHP.
- Avoid introducing UI or telemetry.

## Releasing
- Use semantic versioning tags `vX.Y.Z`.
- Update `CHANGELOG.md`.
