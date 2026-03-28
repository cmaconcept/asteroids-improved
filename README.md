# Asteroids Improved

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Platform: HTML5](https://img.shields.io/badge/Platform-HTML5-orange.svg)
![Rendering: Canvas](https://img.shields.io/badge/Rendering-Canvas-black.svg)
![Audio: Web Audio API](https://img.shields.io/badge/Audio-Web%20Audio%20API-blue.svg)
![Status: Public Build](https://img.shields.io/badge/Status-Public%20Build-brightgreen.svg)

A modern single-file HTML5 reinterpretation of the Atari classic **Asteroids**, expanded with hostile saucers, asteroid gravity, hyperspace jumps, shield energy, boss meteors, particle effects, screen shake, high-score persistence, and fallback synth audio.

## Why this project exists

This project shows how far a compact browser game can be pushed in a single self-contained HTML file without external dependencies. It is both a playable retro arcade game and a useful reference for developers interested in canvas rendering, arcade physics, finite game states, procedural effects, and lightweight browser audio.

## Core features

- Single-file deployment with HTML, CSS, and JavaScript in one artifact
- Canvas-based render loop driven by `requestAnimationFrame`
- Classic ship controls with rotation, thrust, drag, speed cap, and wrap-around movement
- Asteroid split chain across large, medium, and small variants
- Hostile saucers with movement drift, configurable aggression, and enemy projectiles
- Asteroid gravity that influences player movement near large threats
- Hyperspace jump with cooldown and safe-position search
- Shield mechanic that recharges through score gain
- Boss meteor encounter with hit points and stronger gravitational pull
- Particle effects for engine thrust, collisions, flashes, and explosions
- Screen shake system with adjustable intensity
- Intro, pause, running, and game-over states
- Local high-score persistence via `localStorage`
- Fallback Web Audio synth for gameplay and UI feedback
- In-game runtime tuning panel for speed, shake, aggression, gravity, and title display

## Controls

- `←` / `→` rotate ship
- `↑` thrust
- `Space` fire and start the game from intro
- `Shift` hyperspace jump
- `P` pause or resume
- `R` restart
- `Enter` start from intro
- Mouse click focuses the canvas and resumes audio context

## Quick start

### Run directly

Open the HTML file in a modern browser.

```bash
open INDEX.html
```

### Run from a local server

```bash
python3 -m http.server 8080
```

Then open:

```text
http://localhost:8080/INDEX.html
```

## Screenshots

Add repository screenshots to `assets/screenshots/` and update the image paths below.

### Gameplay

![Gameplay screenshot](assets/screenshots/gameplay-main.png)

### Boss meteor encounter

![Boss meteor screenshot](assets/screenshots/boss-meteor.png)

### Settings panel

![Settings screenshot](assets/screenshots/settings-panel.png)

If the screenshots are not added yet, GitHub will simply show broken image placeholders until the files are committed.

## Architecture at a glance

The current public build is intentionally monolithic.

```text
INDEX.html
├── HTML structure
├── CSS presentation layer
├── DOM references and UI wiring
├── runtime CONFIG object
├── input state
├── game state
├── update systems
├── collision systems
├── rendering systems
├── persistence helpers
└── fallback audio manager
```

This makes the project easy to distribute and inspect, but less ideal for long-term scaling. The next logical engineering step is modularization.

## Recommended repository layout

```text
.
├── INDEX.html
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── Asteroids_Improved_Technical_Documentation.md
└── assets/
    └── screenshots/
```

## Documentation

- [Technical Documentation](Asteroids_Improved_Technical_Documentation.md)
- [Contributing Guide](CONTRIBUTING.md)
- [Changelog](CHANGELOG.md)

## Engineering assessment

The game is feature-rich, readable, and strong as a public showcase. It is already beyond throwaway prototype level, but it still carries the maintenance costs of a single-file architecture. Future work should focus on:

- extracting modules for config, state, systems, rendering, audio, and UI
- isolating balancing values from gameplay logic
- improving testability of collision and spawn logic
- introducing deterministic simulation hooks where practical
- separating visual effects from gameplay state transitions

## Roadmap

- [ ] Split runtime systems into modules
- [ ] Add persistent settings storage
- [ ] Add lightweight automated regression checks
- [ ] Add mobile control layer
- [ ] Add screenshot assets and gameplay GIF
- [ ] Add release workflow and repository badges tied to real CI

## Repository badge upgrade path

The current badges are static and safe to publish immediately. Once the repository exists on GitHub, you can replace or extend them with live badges for:

- GitHub Actions build status
- latest release
- open issues
- pull requests
- code size
- last commit

## License

This project is released under the [MIT License](LICENSE).
