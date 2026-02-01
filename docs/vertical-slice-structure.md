# Vertical Slice Folder Structure

This repository now uses a vertical slice layout to keep feature logic co-located while centralizing shared utilities.

## Overview

```
src/
  features/
    <feature-name>/
      api/
      commands/
      queries/
      models/
      validators/
      handlers/
      routes/
      index.ts
  shared/
    config/
    constants/
    helpers/
    middleware/
    repositories/
    services/
    types/
    utils/
```

## Guidance

- **features/**: Each feature should contain its own API contracts, handlers, validators, and data access wiring.
- **shared/**: Cross-cutting modules and reusable primitives live here.
  - **constants/**: Shared constant values (enums, error codes, etc.).
  - **helpers/**: Pure functions and utilities that are not tied to infrastructure.
  - **services/**: Cross-feature services (e.g., email, notifications, audit logging).
  - **repositories/**: Shared repository interfaces or base classes (feature-specific repositories should stay in their feature folder).
  - **config/**: Configuration loaders and environment parsing.
  - **middleware/**: HTTP middleware, guards, or interceptors.
  - **types/**: Shared type definitions.
  - **utils/**: Generic utilities.

## Next Steps

1. Move existing modules into the appropriate feature or shared folder.
2. Keep each feature slice self-contained so it can be modified without touching unrelated areas.
3. Add feature-specific `README.md` files as the domain grows.
