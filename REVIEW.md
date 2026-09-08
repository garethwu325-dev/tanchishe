# HTML Snake Game — Review Profile

**Project:** Single-file HTML5 Canvas Snake Game (`index.html`)
**Tech Stack:** HTML5 + CSS3 + Vanilla JavaScript (ES6+), zero external dependencies
**Architecture:** Single HTML file with embedded `<style>` and `<script>`

## Project-Specific Review Gates

### Gate 1: Spec Compliance
- Grid: 20×20 cells, 20px per cell → `GRID_SIZE=20`, `CELL_SIZE=20`
- Initial snake: length 3, horizontal rightward → `INIT_SNAKE_LENGTH=3`, direction `'RIGHT'`
- Food: random, no overlap with snake body
- Controls: Arrow keys only, no reverse (e.g. RIGHT → LEFT)
- Collision: wall or self → game over
- Score: +10 per food item, snake length +1
- Game speed: 150ms/step constant

### Gate 2: Rendering Correctness
- Canvas 2D API rendering at 400×400px
- Snake head distinct from body (color/shape)
- Eyes on snake head reflect direction
- Game-over overlay when game ends

### Gate 3: Code Quality
- No external dependencies
- No `TBD`/`TODO`/placeholder code
- Keyboard event `preventDefault()` to prevent scrolling
- `clearInterval` on restart to avoid timer leaks

### Gate 4: Edge Cases
- Snake fills entire grid → win condition
- Rapid key presses before game tick → direction queuing (nextDirection pattern)
- Food spawn after all non-snake cells exhausted → win