# Software

This directory contains all implementation work for the product runtime, app layer, SDK, and platform services.

## Suggested structure

- `apps/` — user-facing product applications and demo experiences
- `core/` — engine, scene, interaction, workspace manager, and runtime services
- `sdk/` — public APIs and integration tools for developers
- `plugins/` — platform adapters, sensor integration, and extension points

## Principles

- Keep the runtime modular and abstraction-friendly.
- Keep the first implementation small and testable.
- Separate product UX from lower-level platform concerns.
