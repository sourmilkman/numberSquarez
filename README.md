# Number Squares

A mobile-first puzzle game featuring **Magic Squares** and **Latin Squares**, built as a **Progressive Web App (PWA)**.

## Game Modes

### Magic Squares
Fill the grid so every row, column, and diagonal sums to the same magic number. Uses rule-based validation — any valid magic square arrangement is accepted, not just one specific solution.

### Latin Squares
Place numbers so each appears exactly once in every row and column.

## Features

- **Grid sizes:** 4×4, 5×5, 6×6 with unlockable 7×7 and 8×8
- **Difficulty levels:** Easy, Medium, Hard (controls how many cells are pre-filled)
- **Drag & drop input** — drag from the number tray onto the grid, or drag placed tiles between cells
- **Undo system** — full move history with undo for placements, removals, hints, clears, and grid moves
- **Scoring system** — base points scaled by grid size and difficulty, with penalties for time, hints, extra checks, and extra moves
- **Star rating** — 1 to 3 stars based on score percentage
- **Per-mode stats** — separate best scores, wins, and star counts for Magic and Latin modes
- **Unlock progression** — 7×7 unlocks at 2,500+ score or Hard 6×6 with no hints; 8×8 unlocks similarly on 7×7
- **Auto-completion detection** — automatically triggers win screen when the last tile completes a valid solution
- **Dark theme** — toggle with persistent preference
- **ASMR sound effects** — satisfying tactile audio for every action (Web Audio API, synthesized inline)
- **Tile animations** — pop-in, hint glow, error shake, and diagonal win ripple
- **Fully responsive** — dynamic layout adapts to any screen size without scrolling
- **Offline support** — full PWA with service worker caching
- **Installable** — add to home screen on iOS, Android, or desktop

## PWA Installation

### Desktop (Chrome/Edge)
Visit the site, then click the install icon in the address bar.

### iOS (Safari)
Tap the share button → "Add to Home Screen".

### Android (Chrome)
Tap the menu → "Install app" or "Add to Home Screen".

## File Structure

```
numberSquares/
├── index.html          # Main game (HTML + CSS + JS, all-in-one)
├── manifest.json       # PWA manifest
├── service-worker.js   # Offline caching service worker
├── icon192.png         # 192×192 PWA icon
└── icon512.png         # 512×512 PWA icon
```

## Technical Details

- **Single-file core** — all game code in `index.html`, zero build step
- **Inline service worker fallback** — registers an external SW, falls back to a Blob URL inline SW if that fails
- **No dependencies** — pure vanilla HTML/CSS/JS
- **Magic square generation** — Siamese method (odd orders), diagonal flip (doubly even), Strachey method (singly even)
- **Latin square generation** — cyclic construction with row/column/symbol shuffling
- **Touch & mouse support** — custom drag implementation with ghost element, no native drag API
- **Web Audio API** — all sound effects synthesized inline (no audio files)
- **Persistence** — `localStorage` for scores, stats, unlocks, theme, and sound preferences

## How to Play

1. Open `index.html` in a browser (or install as a PWA)
2. Choose Magic Squares or Latin Squares
3. Select grid size and difficulty
4. Drag numbers from the tray into empty cells
5. Drag placed tiles to rearrange them, or drag them back to the tray
6. Hit Check to validate, or let the game auto-detect completion

## Hosting

Works as a static site. For GitHub Pages: push these files to the repo root, enable Pages in Settings → Pages → Source: main branch. Visit `https://<username>.github.io/<repo>/`.

## License

MIT
