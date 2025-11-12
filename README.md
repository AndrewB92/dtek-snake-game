# Snake Table Game

A JavaScript-based Snake game that runs directly inside an existing HTML table.  
Originally designed to be played on top of the DTEK electricity outage schedule table, this project converts a static grid into an interactive and dynamic game without altering the original table markup.

---

## Features

- Table-based playfield – the snake moves through real table cells (`<td>`) from an existing HTML structure (`#tableRenderElem table`).
- Wall-wrap movement – the snake reappears on the opposite side when crossing table edges.
- UI Controls – Start, Pause, and Reset buttons are automatically injected before the table.
- Live Score Counter – displays current points (1 per apple eaten).
- Keyboard Support – control using arrow keys or `W`, `A`, `S`, `D`.
- No dependencies – pure vanilla JavaScript and CSS.
- Easy integration – can be added to any webpage containing a table.

---

## How It Works

The script dynamically:
1. Selects the target table under `#tableRenderElem`.
2. Maps all non-header `<td>` elements into a grid.
3. Initializes a snake starting position and places a random apple.
4. Handles movement, growth, and collisions.
5. Updates cell background classes to visually represent:
   - `snake-head` – head of the snake  
   - `snake` – body of the snake  
   - `apple` – collectible item

Game logic is entirely grid-driven, with the table acting as a visual canvas.

---

## Installation

1. Copy the game script into your project and include it **after the table** or inside your existing page footer:
   ```html
   <script src="snake-table-game.js"></script>
   ```
   or paste directly inside:
   ```html
   <script>
     // (insert JS code from snake-table-game.js here)
   </script>
   ```

2. Ensure the table exists under:
   ```html
   <div id="tableRenderElem">
     <table> ... </table>
   </div>
   ```

3. Reload the page. You’ll see:
   - Control panel (Start, Pause, Reset, Score)
   - Snake initialized in the first cells of your table

---

## Controls

| Action | Key |
|--------|-----|
| Move Up | ↑ / W |
| Move Down | ↓ / S |
| Move Left | ← / A |
| Move Right | → / D |
| Start / Resume | Start button |
| Pause | Pause button |
| Reset | Reset button |

---

## Customization

You can tweak several variables in the script:

| Variable | Default | Description |
|-----------|----------|-------------|
| `speed` | `180` | Snake movement speed in milliseconds |
| `rows`, `cols` | Derived from table | Table-based playfield size |
| `snake` | `[{r: 0, c: 0}]` | Initial snake segment |
| `apple` | `null` | Randomly placed apple each round |

You can also customize colors and styling in the injected CSS section.

---

## Technical Overview

- The snake’s position is stored as an array of `{r, c}` coordinates.
- Each game tick moves the head based on current direction.
- When the head’s position matches the apple’s — the snake grows, and a new apple spawns.
- If the head’s position overlaps with any other segment, the game ends.
- Wall edges wrap around using modular arithmetic:
  ```js
  r = (r + rows) % rows;
  c = (c + cols) % cols;
  ```

---

## File Structure Example

```
project/
├── index.html
├── snake-table-game.js
└── README.md
```

---

## Demo Integration Example

Here’s how it looks inside a DTEK-like structure:

```html
<section id="snake-section" class="discon_schedule schedule-desktop">
  <div id="tableRenderElem">
    <table>
      <thead> ... </thead>
      <tbody> ... </tbody>
    </table>
  </div>
</section>
<script src="snake-table-game.js"></script>
```

---

## Author

Andrew Bielous  
Frontend & WordPress Developer  
Building interactive experiences from everyday elements.  

---

## License

This project is licensed under the MIT License — feel free to use, modify, and distribute.
# Snake Table Game

A JavaScript-based Snake game that runs directly inside an existing HTML table.  
Originally designed to be played on top of the DTEK electricity outage schedule table, this project converts a static grid into an interactive and dynamic game without altering the original table markup.

---

## Features

- Table-based playfield – the snake moves through real table cells (`<td>`) from an existing HTML structure (`#tableRenderElem table`).
- Wall-wrap movement – the snake reappears on the opposite side when crossing table edges.
- UI Controls – Start, Pause, and Reset buttons are automatically injected before the table.
- Live Score Counter – displays current points (1 per apple eaten).
- Keyboard Support – control using arrow keys or `W`, `A`, `S`, `D`.
- No dependencies – pure vanilla JavaScript and CSS.
- Easy integration – can be added to any webpage containing a table.

---

## How It Works

The script dynamically:
1. Selects the target table under `#tableRenderElem`.
2. Maps all non-header `<td>` elements into a grid.
3. Initializes a snake starting position and places a random apple.
4. Handles movement, growth, and collisions.
5. Updates cell background classes to visually represent:
   - `snake-head` – head of the snake  
   - `snake` – body of the snake  
   - `apple` – collectible item

Game logic is entirely grid-driven, with the table acting as a visual canvas.

---

## Installation

1. Copy the game script into your project and include it **after the table** or inside your existing page footer:
   ```html
   <script src="snake-table-game.js"></script>
   ```
   or paste directly inside:
   ```html
   <script>
     // (insert JS code from snake-table-game.js here)
   </script>
   ```

2. Ensure the table exists under:
   ```html
   <div id="tableRenderElem">
     <table> ... </table>
   </div>
   ```

3. Reload the page. You’ll see:
   - Control panel (Start, Pause, Reset, Score)
   - Snake initialized in the first cells of your table

---

## Controls

| Action | Key |
|--------|-----|
| Move Up | ↑ / W |
| Move Down | ↓ / S |
| Move Left | ← / A |
| Move Right | → / D |
| Start / Resume | Start button |
| Pause | Pause button |
| Reset | Reset button |

---

## Customization

You can tweak several variables in the script:

| Variable | Default | Description |
|-----------|----------|-------------|
| `speed` | `180` | Snake movement speed in milliseconds |
| `rows`, `cols` | Derived from table | Table-based playfield size |
| `snake` | `[{r: 0, c: 0}]` | Initial snake segment |
| `apple` | `null` | Randomly placed apple each round |

You can also customize colors and styling in the injected CSS section.

---

## Technical Overview

- The snake’s position is stored as an array of `{r, c}` coordinates.
- Each game tick moves the head based on current direction.
- When the head’s position matches the apple’s — the snake grows, and a new apple spawns.
- If the head’s position overlaps with any other segment, the game ends.
- Wall edges wrap around using modular arithmetic:
  ```js
  r = (r + rows) % rows;
  c = (c + cols) % cols;
  ```

---

## File Structure Example

```
project/
├── index.html
├── snake-table-game.js
└── README.md
```

---

## Demo Integration Example

Here’s how it looks inside a DTEK-like structure:

```html
<section id="snake-section" class="discon_schedule schedule-desktop">
  <div id="tableRenderElem">
    <table>
      <thead> ... </thead>
      <tbody> ... </tbody>
    </table>
  </div>
</section>
<script src="snake-table-game.js"></script>
```

---

## Author

Andrew Bielous  
Frontend & WordPress Developer  
Building interactive experiences from everyday elements.  

---

## License

This project is licensed under the MIT License — feel free to use, modify, and distribute.