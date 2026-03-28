# Contributing to Asteroids Improved

Thank you for contributing.

This repository contains a browser game implemented as a single-file HTML application. The codebase is compact in deployment form, but it includes several tightly connected subsystems such as input handling, state management, rendering, collisions, particles, audio synthesis, HUD updates, overlay state, and runtime settings. Contributors should therefore treat changes as **system changes**, not isolated line edits. The current implementation structure is evident in the uploaded source, where most gameplay and UI responsibilities are colocated in one document. fileciteturn3file0turn3file4

## Project Principles

1. Preserve playability first
2. Keep frame updates predictable
3. Prefer clarity over cleverness
4. Avoid hidden side effects
5. Separate mechanics changes from refactors where possible
6. Keep UI text and runtime behaviour aligned
7. Document balancing changes explicitly

## What We Welcome

- bug fixes
- performance improvements
- documentation improvements
- refactors that reduce coupling without changing gameplay unexpectedly
- accessibility improvements
- balancing changes with rationale
- test scaffolding for deterministic logic
- modularization work that preserves parity with the current game

## What Requires Extra Care

The following areas are tightly coupled and should be changed carefully:

- `CONFIG` balancing values
- `state` layout and lifecycle
- collision rules
- spawn safety logic
- player damage and respawn flow
- hyperspace rules
- shield economy
- saucer aggression and projectile logic
- audio event triggering
- HUD synchronization
- overlay state transitions

These are all central gameplay systems visible in the current source file. fileciteturn3file4

## Branching and Commit Style

Use focused branches and small commits.

Recommended branch naming:

```text
feature/<short-description>
fix/<short-description>
refactor/<short-description>
docs/<short-description>
```

Recommended commit style:

```text
feat: add persistent settings state
fix: prevent unsafe respawn near boss meteor
refactor: extract collision helpers into module
docs: expand architecture overview
```

## Pull Request Expectations

Each pull request should include:

- a clear summary of what changed
- why the change was needed
- whether gameplay behaviour changed
- whether balancing changed
- whether UI text changed
- a note on regression risk
- screenshots or recordings for visible changes

For mechanic changes, include before/after behaviour.

## Development Guidance

### 1. Do not mix refactors with balance tuning

A refactor PR should not silently modify thrust, cooldowns, gravity, aggression, scoring, or spawn counts. If a value under `CONFIG` changes, call it out directly.

### 2. Keep delta-time handling stable

The game loop clamps raw frame delta and then applies a user-controlled speed multiplier before update execution. Any changes here affect the entire runtime model and should be reviewed with exceptional care. fileciteturn3file4

### 3. Treat state transitions as contract boundaries

The game currently uses `intro`, `running`, `paused`, and `gameover` as state gates. Changes to these transitions can break overlays, audio, input handling, or HUD synchronization. fileciteturn3file4

### 4. Maintain gameplay readability

The project is an arcade title. Responsiveness, legibility, and consistency matter more than visual complexity.

### 5. Preserve public-browser compatibility

Prefer standard browser APIs and avoid introducing heavy tooling unless there is a clear maintenance advantage.

## Testing Checklist

Before opening a pull request, validate the following manually:

- game starts from intro correctly
- pause and resume work correctly
- restart works correctly
- ship movement still feels responsive
- bullets wrap and expire correctly
- asteroid splitting still follows intended size chain
- boss meteor still requires multiple hits
- shield activates only at full threshold
- hyperspace cooldown is displayed correctly
- saucers spawn, fire, and despawn correctly
- level progression still triggers
- high score persists correctly
- audio still resumes after user interaction
- settings panel still reflects runtime values

All of these behaviours exist in the current source and should be preserved unless the PR intentionally changes them. fileciteturn3file2turn3file4

## Coding Guidelines

- Use descriptive function names
- Keep helper functions pure when possible
- Prefer explicit entity fields over implicit mutation
- Avoid magic numbers outside `CONFIG`
- Add JSDoc when introducing non-trivial structures
- Keep rendering functions free of gameplay-side mutations
- Keep update functions deterministic relative to current state and input
- Escape user-facing dynamic HTML if DOM injection is involved

## Documentation Guidelines

If you add or remove a system, update:

- `README.md`
- `CHANGELOG.md`
- technical documentation under `docs/`
- control legend or HUD labels if needed

## Reporting Bugs

A good bug report includes:

- browser and version
- operating system
- reproduction steps
- expected result
- actual result
- screenshot or recording if relevant
- whether the issue is deterministic or intermittent

## Security and Safety Notes

This is a client-side browser game. Even so:

- avoid unsafe HTML insertion
- avoid unnecessary storage of user data
- preserve `escapeHtml()` style protections around overlay content
- document any future networked features separately before introduction

The current source explicitly escapes overlay strings before injecting HTML. fileciteturn3file4

## First Good Issues

Suggested starter tasks:

- extract constants into separate modules
- add settings persistence
- add mute toggle
- add debug overlay for entity counts and frame timing
- add JSDoc typedefs for player, asteroid, saucer, and bullet entities
- add screenshot assets and repository badges
