# PRD: trexrunner

## Overview
A JavaScript browser recreation of the Chrome offline T-Rex dinosaur runner game. The player controls a dino that jumps over cacti and ducks under pterodactyls. Built in vanilla HTML/CSS/JavaScript as a fun browser game exercise.

## Goals
- Recreate the Chrome dino runner game in vanilla JavaScript
- Player controls: jump (Space/Up), duck (Down)
- Obstacle types: cacti, pterodactyls
- Score tracking and increasing difficulty over time
- Game over + restart flow

## Non-Goals
- Mobile touch controls
- Online leaderboard
- Extension to Chrome's built-in game
- AI bot (see chromedino repo)

## Tech Stack
- **Language**: JavaScript (vanilla), HTML, CSS
- **Runtime**: Browser

## Architecture
```
trexrunner/
├── index.html    # Game container
├── index.js      # Game engine + rendering loop
├── index.css     # Styling
└── assets/       # Sprite images
```

**Game loop:**
- `requestAnimationFrame` render loop
- Entity classes: `Dino`, `Cactus`, `Pterodactyl`, `ScoreBoard`
- Collision detection via AABB (axis-aligned bounding box)
- Speed increases with score

## Features (detailed)

### Player Controls
- `Space` / `ArrowUp` → jump
- `ArrowDown` → duck
- `Space` (when dead) → restart

### Obstacles
- Cacti: stationary ground obstacles, random height
- Pterodactyls: flying obstacles at various heights

### Scoring + Difficulty
- Score increments with distance
- Game speed increases gradually
- High score persisted in memory (not localStorage)

## Deployment / Run
```bash
# Open index.html in any browser
# Or serve locally:
python -m http.server
```

## Constraints & Notes
- **Vanilla JS**: no frameworks or bundlers — runs directly in browser
- **No mobile**: no touch event handlers
- **Assets**: sprite images in `assets/` must match expected filenames in `index.js`
