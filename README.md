<div align="center">

# 🎮 Neon Pulse Tetris

### A Modern Neon Arcade Experience Built with HTML, CSS & Vanilla JavaScript

</div>

<p align="center">
  <strong>⚡ Classic Tetris. Cyberpunk Aesthetics. Zero Frameworks.</strong>
</p>

<p align="center">
  A browser-based Tetris game featuring vibrant neon visuals, glassmorphism UI, synthesized audio effects, particle animations, and responsive touch controls — powered entirely by native web technologies.
</p>

---

## 🌌 Overview

**Neon Pulse Tetris** is a modern reimagining of the classic block-stacking puzzle game. It combines familiar Tetris gameplay with a futuristic neon-inspired interface, smooth canvas rendering, glowing geometric blocks, and immersive visual feedback.

Built using **HTML5, CSS3, and pure JavaScript**, the game requires no frontend frameworks, external game engines, or JavaScript dependencies.

The result is a lightweight, self-contained arcade experience that runs directly in a modern web browser.

### ✨ Highlights

- 🌈 Vibrant neon color palette with glowing, gradient-filled blocks
- 🪟 Glassmorphism interface with translucent cards and subtle borders
- 🎮 Classic Tetris gameplay with all seven tetromino shapes
- 👻 Ghost-piece preview showing the projected landing position
- 🔄 Piece rotation with basic wall-kick handling
- 📦 Hold and next-piece functionality
- 🔊 Procedurally synthesized sound effects using the Web Audio API
- 💥 Particle effects, floating score messages, and screen shake
- 📱 On-screen controls for touch-enabled devices
- ⏸️ Pause, resume, and retry functionality
- 📈 Dynamic scoring, line tracking, and progressive difficulty

---

## 🖥️ Preview

<p align="center">
  <em>Enter the neon arcade — stack blocks, clear lines, and beat your high score.</em>
</p>

> 💡 **Showcase tip:** Add a screenshot or GIF of the running game here to make your GitHub repository more engaging.

```md
![Neon Pulse Tetris Gameplay](./assets/neon-pulse-tetris.png)
```

You can also use an animated gameplay GIF:

```md
![Neon Pulse Tetris Demo](./assets/neon-pulse-tetris-demo.gif)
```

Replace these example paths with your actual screenshot or GIF files.

---

## 🛠️ Technology Stack

| Technology                    | Purpose                                                                                   |
| ----------------------------- | ----------------------------------------------------------------------------------------- |
| **HTML5**                     | Game layout, interface components, canvas elements, buttons, and overlays                 |
| **CSS3**                      | Neon styling, gradients, glassmorphism, responsive layout, transitions, and glow effects  |
| **Vanilla JavaScript (ES6+)** | Game logic, state management, collision detection, scoring, input handling, and animation |
| **HTML5 Canvas API**          | Rendering the game board, tetrominoes, ghost pieces, and visual effects                   |
| **Web Audio API**             | Real-time synthesized sound effects without external audio files                          |
| **Google Fonts**              | Orbitron and Outfit typography for the futuristic interface                               |
| **Browser Animation APIs**    | `requestAnimationFrame()` for the main rendering loop                                     |

### Dependencies

**No JavaScript packages or frontend frameworks are required.**

The game uses native browser APIs and Google Fonts for typography. Google Fonts requires an internet connection; the game can otherwise be run locally without a build step.

---

## 🚀 Getting Started

### Prerequisites

- A modern web browser such as Google Chrome, Microsoft Edge, Firefox, or Safari
- A code editor such as Visual Studio Code (optional)
- A local web server (optional, but recommended for development)

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/neon-pulse-tetris.git
```

Replace `YOUR_USERNAME` with your GitHub username and adjust the repository name if necessary.

### 2. Navigate to the project directory

```bash
cd neon-pulse-tetris
```

### 3. Launch the game

If the HTML file is named `index.html`, you can open it directly in your browser.

Alternatively, use the VS Code Live Server extension, or run a simple Python HTTP server:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

No compilation, package installation, or bundling is necessary.

---

## 🎯 How to Play

The objective is simple: arrange falling tetrominoes to form complete horizontal lines. Completed lines disappear, increasing your score and making room for additional pieces.

The game ends when newly spawned pieces can no longer fit on the board.

### 🕹️ Keyboard Controls

| Key             | Action                                  |
| --------------- | --------------------------------------- |
| `←` Left Arrow  | Move the active piece left              |
| `→` Right Arrow | Move the active piece right             |
| `↑` Up Arrow    | Rotate the active piece clockwise       |
| `↓` Down Arrow  | Soft drop — move the piece down one row |
| `Space`         | Hard drop — instantly place the piece   |
| `C`             | Hold or swap the active piece           |
| `Shift`         | Hold or swap the active piece           |
| `P`             | Pause or resume the game                |
| `Esc`           | Pause or resume the game                |

### 📱 Touch Controls

The interface includes dedicated on-screen buttons for mobile and touch-enabled devices.

| Button             | Action                              |
| ------------------ | ----------------------------------- |
| **HOLD**           | Store or swap the current tetromino |
| **↻**              | Rotate the piece                    |
| **⚡**             | Hard drop                           |
| **←**              | Move left                           |
| **↓**              | Soft drop                           |
| **→**              | Move right                          |
| **PAUSE / RESUME** | Toggle the paused state             |

### 🔊 Audio

Use the **AUDIO** button in the header to enable or mute sound effects.

The sound engine synthesizes effects in real time, including movement tones, rotation feedback, hard-drop sounds, line-clear melodies, and a game-over sequence.

No separate audio assets are needed.

---

## 🧩 Gameplay Features

### 1. Seven-Bag Tetromino Generator

The game implements a randomized **7-bag generator** containing all seven standard tetromino types:

- `I` — Cyan
- `O` — Yellow
- `T` — Purple
- `S` — Green
- `Z` — Pink/Red
- `J` — Blue
- `L` — Orange

Each bag is shuffled before its pieces are consumed. This ensures every group of seven generated pieces contains one of each type.

### 2. Collision Detection

The collision system checks whether a tetromino would overlap occupied grid cells or exceed the horizontal and bottom boundaries of the board.

Invalid movement and rotation are rejected, preventing pieces from moving through existing blocks.

### 3. Rotation and Wall Kicks

Pieces rotate clockwise using a matrix transformation.

When a rotated piece collides with an obstacle, the game attempts horizontal offsets of `0`, `-1`, `+1`, `-2`, and `+2` columns.

This provides basic wall-kick behavior, although it is not a full implementation of the official Super Rotation System (SRS).

### 4. Ghost Piece

A translucent ghost piece indicates where the active tetromino will land if hard-dropped in its current position.

It improves spatial awareness and helps players plan placements more accurately.

### 5. Hold and Next Queue

The **HOLD** panel lets players save a tetromino and swap it with the active piece.

The **NEXT** panel previews the upcoming tetromino.

The hold operation is limited to once per piece placement, following a familiar Tetris-style mechanic.

### 6. Scoring System

The game awards points for clearing lines and performing hard drops.

| Lines Cleared       | Base Points |
| ------------------- | ----------: |
| Single              |         100 |
| Double              |         300 |
| Triple              |         500 |
| Tetris — Four lines |         800 |

Line-clear points are multiplied by the current level.

Hard drops award **2 points per row dropped**.

### 7. Progressive Difficulty

The level increases after every ten lines cleared.

The automatic drop interval decreases as the level rises, making the game progressively faster.

The current implementation starts with a 1,000 ms drop interval and reduces it by 90 ms per level, down to a minimum of 90 ms.

### 8. Visual Feedback

The rendering system includes:

- Gradient-filled blocks with glossy highlights
- Color-matched neon glows
- Subtle board grid lines
- Screen shake after hard drops and line clears
- Particle bursts when rows disappear
- Floating score and line-clear messages
- Dark backgrounds with cyan, pink, purple, and blue ambient lighting

These effects are rendered directly on the canvas without a separate graphics library.

---

## 🎨 UI and Visual Design

Neon Pulse Tetris follows a futuristic arcade design language.

### Design Principles

- **Cyberpunk-inspired palette:** Deep navy backgrounds contrasted with electric cyan, hot pink, purple, yellow, and green.
- **Glassmorphism:** Semi-transparent interface cards, backdrop blur, subtle borders, and layered shadows.
- **Typography:** Orbitron provides a technical, futuristic appearance for headings and statistics, while Outfit improves general readability.
- **Micro-interactions:** Button hover states, active feedback, transitions, and glowing accents.
- **Visual hierarchy:** The central game board receives the most attention, with score statistics and piece previews positioned alongside it.

### Layout Components

| Component       | Responsibility                                                |
| --------------- | ------------------------------------------------------------- |
| Header          | Game title and audio toggle                                   |
| Hold panel      | Displays the stored tetromino                                 |
| Score panel     | Displays the current score                                    |
| Level panel     | Displays the current difficulty level                         |
| Lines panel     | Displays total lines cleared                                  |
| Main board      | Renders gameplay and visual effects                           |
| Next panel      | Previews the upcoming tetromino                               |
| Overlay         | Displays the start screen, paused state, and game-over screen |
| Touch controls  | Provides buttons for movement and game actions                |
| Keyboard legend | Shows desktop control mappings                                |

---

## 🏗️ Project Architecture

The project uses a lightweight, browser-native architecture without a framework or build system.

```text
neon-pulse-tetris/
│
├── index.html          # HTML structure, CSS styles, and JavaScript logic
├── README.md           # Project documentation
│
└── assets/             # Optional screenshots and gameplay GIFs
    ├── neon-pulse-tetris.png
    └── neon-pulse-tetris-demo.gif
```

The `assets/` directory is optional and is only needed if you add screenshots or GIFs.

### Core JavaScript Modules

Although the current implementation is contained in one HTML file, its logic is organized into distinct functional sections.

| Module               | Key Functions / Components                   | Responsibility                                  |
| -------------------- | -------------------------------------------- | ----------------------------------------------- |
| Audio engine         | `SoundEngine`                                | Synthesizes sound effects                       |
| Board initialization | `createGrid()`                               | Creates the 10 × 20 game grid                   |
| Piece generation     | `getNextBagPiece()`                          | Generates shuffled tetrominoes                  |
| Collision system     | `collide()`                                  | Detects invalid piece positions                 |
| Rotation             | `rotateMatrix()`, `playerRotate()`           | Rotates pieces and attempts wall kicks          |
| Movement             | `playerMove()`, `playerDrop()`               | Handles horizontal and vertical movement        |
| Hard drop            | `playerHardDrop()`                           | Drops a piece and awards points                 |
| Hold system          | `playerHold()`                               | Stores and swaps pieces                         |
| Piece placement      | `merge()`, `lockPiece()`                     | Locks pieces into the grid                      |
| Line clearing        | `clearLines()`                               | Removes complete rows and updates scoring       |
| Rendering            | `drawModernBlock()`, `render()`              | Draws blocks, previews, and effects             |
| Game loop            | `update()`                                   | Advances automatic piece dropping and rendering |
| Game lifecycle       | `resetGame()`, `gameOver()`, `togglePause()` | Manages game states                             |
| Input handling       | Keyboard and button event listeners          | Processes player input                          |

---

## ⚙️ Technical Implementation

### Game Board

The game uses a logical grid consisting of 10 columns and 20 rows.

```javascript
const COLS = 10;
const ROWS = 20;
const BLOCK_SIZE = 26;
```

The main canvas measures 260 × 520 pixels, corresponding to 10 × 20 blocks at 26 pixels per block.

### Tetromino Representation

Each piece is represented as a two-dimensional matrix.

```javascript
const SHAPES = {
  I: [
    [0, 0, 0, 0],
    [1, 1, 1, 1],
    [0, 0, 0, 0],
    [0, 0, 0, 0],
  ],
  O: [
    [1, 1],
    [1, 1],
  ],
};
```

The full implementation defines all seven standard tetrominoes. Matrix values indicate occupied and empty cells.

### Rendering Pipeline

The rendering loop uses `requestAnimationFrame()` to synchronize updates with the browser's rendering cycle.

Each frame draws the background, grid, locked pieces, ghost piece, active piece, particles, and floating text.

### Audio Generation

The `SoundEngine` uses `AudioContext`, oscillators, and gain nodes to synthesize sound effects.

Different oscillator waveforms and frequencies provide distinct sounds for movement, rotation, dropping, line clearing, and game over.

Audio initialization occurs in response to user interaction to accommodate browser autoplay restrictions.

---

## 📈 Scoring and Level Progression

The game maintains three primary statistics:

- **Score:** Total points accumulated from line clears and hard drops.
- **Lines:** Total number of completed rows cleared.
- **Level:** Current difficulty level.

The level is calculated as:

```javascript
level = Math.floor(lines / 10) + 1;
```

The automatic drop interval is calculated as:

```javascript
dropInterval = Math.max(90, 1000 - (level - 1) * 90);
```

These formulas make the game increasingly challenging as players clear more lines.

---

## 📱 Browser Compatibility

The game is designed for modern browsers supporting:

- HTML5 Canvas
- CSS gradients and backdrop filters
- JavaScript ES6+ syntax
- `requestAnimationFrame()`
- Web Audio API
- `CanvasRenderingContext2D.roundRect()`

Desktop keyboard input and on-screen controls are supported. The layout includes mobile-oriented controls and viewport settings.

**Note:** The game has not been independently tested across every browser or device. Visual behavior may vary depending on browser support, screen dimensions, and device capabilities.

---

## 🔮 Future Improvements

Potential enhancements for future releases include:

- [ ] Persistent high scores using `localStorage`
- [ ] A leaderboard with a backend API
- [ ] Difficulty selection and customizable starting levels
- [ ] Multiple themes and color palettes
- [ ] Improved responsive layout for narrow screens
- [ ] Continuous movement when holding directional buttons
- [ ] Touch swipe and gesture controls
- [ ] Official SRS rotation and kick tables
- [ ] Advanced combo and back-to-back scoring
- [ ] A proper countdown and pause-state indicator
- [ ] Accessibility improvements and reduced-motion support
- [ ] Automated tests for collision detection, rotation, and scoring
- [ ] Separate HTML, CSS, and JavaScript files for maintainability
- [ ] Optional PWA support for installable, offline gameplay

These are proposed enhancements, not features currently implemented.

---

## 🤝 Contributing

Contributions, bug reports, and feature suggestions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Test the game in a modern browser.
5. Submit a pull request describing your changes.

For larger changes, consider opening an issue first to discuss the proposed implementation.

---

## 📄 License

No license has been specified in the provided project code.

If you intend to publish the project publicly, consider adding a `LICENSE` file. An MIT License is a common option for open-source projects, provided you are comfortable with its terms and have the rights to license all included assets and code.

---

## 👨‍💻 Author

**RAJDEEP CHAKRABORTY**

- GitHub: [https://github.com/nemesisrc]
- Portfolio: [https://nemesisrc.github.io/portfolio-2026/rajdeep-chakraborty.html]

Replace these placeholders with your actual profile links before publishing.

---

<p align="center">
  <strong>⚡ Stack smart. Clear lines. Chase the high score. ⚡</strong>
</p>

<p align="center">
  Built with ❤️ using HTML, CSS, and Vanilla JavaScript.
</p>
