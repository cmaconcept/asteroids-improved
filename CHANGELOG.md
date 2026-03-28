# Changelog

All notable changes to this project should be documented in this file.

The format is based on Keep a Changelog principles and uses semantic-style release labels where practical.

## [Unreleased]

### Added
- Placeholder for upcoming modularization work
- Placeholder for persistent settings support
- Placeholder for repository automation and test scaffolding

### Changed
- Placeholder for architectural cleanup entries

### Fixed
- Placeholder for gameplay and runtime bug fixes

## [0.1.0] - 2026-03-28

### Added
- Initial public repository release of **Asteroids Improved**
- Single-file HTML deployment model with integrated markup, styling, runtime logic, and audio synthesis
- Canvas-based arcade gameplay loop using `requestAnimationFrame`
- Intro overlay and game-state flow for intro, running, paused, and game-over modes
- Player movement with rotation, thrust, drag, wrap-around, speed cap, and projectile cooldown
- Player bullets and enemy saucer bullets
- Asteroid split progression across large, medium, and small variants
- Boss meteor encounter with hit points, custom visuals, score reward, and stronger gravity profile
- Asteroid gravity system affecting player movement near large threats
- Saucer enemy spawning, drifting, firing, and configurable aggression
- Shield system with score-driven recharge and full-energy activation requirement
- Hyperspace jump with cooldown and safe-position search attempts
- Particle effects for engine thrust, impacts, explosions, and screen flashes
- Screen shake system with runtime multiplier
- HUD for score, high score, lives, level, jump cooldown, shield, status, UFO count, aggression, gravity, and boss count
- Settings panel exposing game speed, screen shake, UFO aggression, meteor gravity, and title display toggle
- `localStorage` high score persistence
- Web Audio fallback synthesizer for gameplay and UI effects

### Notes
- This release is functionally rich, but architecturally monolithic
- Public maintenance should prioritize modularization, typed documentation, and testability improvements
- Technical documentation was produced from the uploaded source file and aligned with the current implementation structure. fileciteturn3file0turn3file2turn3file4
