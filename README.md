# Ephemeral Whirls

**A seed-based generative system for tangled looping line compositions.**

A catalogue of computational textile compositions for fashion, textile and surface design — algorithmically drawn, seed-documented, and ready for production.

---

## Overview

Ephemeral Whirls is a generative design system rather than a single artwork. Each composition is built from two dozen small agents — "loopers" — that wander across the frame in a slowly curving path. Every now and then, a looper decides to loop: it enters a slow spin, completes a full circle, and returns to its wandering. Over two thousand steps, the loopers leave a tangled, coloured field of lines.

The system is designed for:

- **Fashion houses** adapting wandering-line ornament for apparel and accessories
- **Textile studios** developing repeat patterns and yardage
- **Surface designers** working across print, wallpaper, and interior applications

Every composition can be licensed, adapted, or commissioned to a brief.

---

## Concept

A line, when it is *wandering* rather than drawn, becomes a whirl — tangled, patient, quietly yours.

The wandering line — irregular, patient, endlessly variable — has always carried the trace of a body in motion. From the trailing thread of a spider to the meander of a river, the looping stroke is one of the oldest forms of drawn computation we have. Ephemeral Whirls translates that motion into code. Each composition begins with a small set of agents and unfolds through continuous wandering, spontaneous looping, and colour-shifting, until the frame fills with a tangled whirl.

The palette, the number of loopers, the number of steps, and the orientation of the whole field are all derived from a single numeric seed.

Like the other still volumes in this series (Girih, Arachne, Celestial Grove, ChaotiColor, Citrus Mosaic, Crazy Knight Curve, Crazy Knight Line, Crazy Letter, cyPollock, Digital Pollen, Draconic Fractals, Dreamscape Watercolors, Elliott Waves, Ellipses, Enigma Sudoku), **Ephemeral Whirls is a static composition.** The plate, the framed plate, the surfaces, and the archive are all static frames. A whirl is something you read; its character is stillness, not motion.

---

## Features

- **Seed-based generation** — every composition is defined by a numeric seed and can be regenerated exactly
- **Deterministic output** — the same seed always produces the same composition
- **Wandering loopers** — 23 to 24 autonomous agents, each with its own heading, speed, and sin-offset
- **Spontaneous looping** — each looper occasionally enters a slow spin, completing a full circle before continuing
- **Colour-shifting** — each looper picks a colour from a palette; when it exits the frame it re-enters with a new colour
- **Forty-six palettes** — from duotone to eight-colour schemes, tuned for vivid contrast against light backgrounds
- **Twenty-two background tones** — soft, pale fields that let the coloured traces read as threads
- **Orientation rotation** — the entire composition can be rotated 0°, 90°, 180°, or 270° based on the seed
- **Adaptive surfaces** — one seed applied across print, scarf, textile, and wall formats
- **Archive** — eight curated seeds available for immediate loading
- **Download** — export the composition as a high-resolution PNG
- **Keyboard shortcuts** — `R` for new seed, `S` to save

---

## Project Structure

```
.
├── index.html          # Main catalogue page
├── images/
│   ├── fav.svg         # Favicon
│   ├── tote.png        # Mockup: tote bag
│   ├── tee.png         # Mockup: t-shirt
│   └── cushion.png     # Mockup: cushion
└── README.md
```

---

## How It Works

### The Seed

A numeric seed (a large integer) initializes a deterministic pseudo-random generator. From this seed, the system derives:

- Background colour (from a palette of 22 light tones)
- Looper palette (from a set of 46 colour schemes)
- Number of loopers (23 or 24)
- Number of iterations (2,000 to 4,000)
- Orientation (up, down, right, or left)

Because the generator is deterministic, the same seed always produces the same composition — on any device, at any time.

### The Loopers

Each composition runs a small simulation:

1. **Initialize.** Each looper starts at the left edge of the frame at a random y-position. It gets its own speed, its own sin-offset (for the wobble), its own looping speed, and its own colour from the palette.
2. **Wander.** On each step, the looper updates its heading with a small random perturbation, then moves one step forward in the direction of its heading.
3. **Loop (occasionally).** If the looper is past 25% of the frame width, there is a 1% chance per step that it will enter a "looping" state. In that state, its heading advances steadily, so it spins through a full circle.
4. **Exit loop.** Once a looping looper has passed through π radians and comes back near 0 or 2π, it exits the loop and resumes wandering.
5. **Re-enter.** If a looper drifts off the edge of the frame, it respawns at the left edge with a new colour.

Over 2,000 to 4,000 steps, the loopers collectively leave thousands of small line segments — a dense, tangled trace across the frame.

### The Palette

Two colour systems meet in every composition:

- **Twenty-two background tones** — soft, pale fields: white smoke, electric blue, magic mint, tea green, light orange, neon yellow, sage, cotton candy, rose quartz, pastel violet, powder pink, cornsilk, robin egg blue, and more.
- **Forty-six looper palettes** — each palette is a small family of two to eight vivid colours, tuned for maximum contrast against the light background. Palettes range from duotone pairs to full eight-colour rainbows.

Each looper picks one colour from the palette and draws its segment in that colour. When it respawns after leaving the frame, it picks a new colour — so the composition reads as a woven field of threads, each thread contributing one colour of the whole.

### The Orientation

Every composition has an orientation, chosen by the seed:

| Side  | Rotation      |
|-------|---------------|
| 0     | 90° clockwise |
| 1     | 90° counterclockwise |
| 2     | 180°          |
| 3     | 0° (natural)  |

This small variation gives each composition its own sense of direction — some read as horizontal fields, others as vertical.

### The Surfaces

The same seed is rendered across four surface formats. These are static frames — they represent the print-ready composition.

| Surface  | Aspect | Material          |
|----------|--------|-------------------|
| Print    | 1 : 1  | Cotton rag        |
| Scarf    | 3 : 1  | Twill silk        |
| Textile  | 4 : 3  | Fabric yardage    |
| Wall     | 2 : 3  | Wallpaper         |

Each surface uses the same underlying seed and structural logic — only the repeat, orientation, and scale change.

### Stillness

Like the rest of the still volumes, Ephemeral Whirls does not animate. The plate is a single frozen frame — the composition is complete the moment it is generated.

This is a deliberate design choice. A whirl is not a swarm. It is not a rotation. It is a trace, laid down once and left. Its stillness is what makes it print-ready in the strictest sense: what you see is what you get.

---

## Usage

### In the browser

1. Open `index.html` in any modern browser.
2. Click **New Seed** to generate a new composition.
3. Click **Download** to save the composition as a PNG.
4. Scroll to the **Archive** section and click any plate to load it into Plate 001.

### Keyboard shortcuts

| Key | Action          |
|-----|-----------------|
| `R` | New seed        |
| `S` | Save as PNG     |

### Reproducing a composition

Each composition is identified by an 8-digit seed label displayed in the metadata panel. To reproduce a specific composition, note the seed and regenerate it programmatically:

```js
const rng = new RandomGenerator(seed);
const features = buildFeatures(rng);
renderComposition(canvas, features, rng);
```

Because the generator is deterministic, this will produce the identical composition on any device.

---

## Technical Notes

- **No build step.** The system is a single HTML file with inline CSS and JavaScript.
- **No dependencies.** All drawing is done with the native Canvas 2D API.
- **Deterministic.** The `RandomGenerator` class uses a xorshift-based PRNG seeded by an integer, so identical seeds produce identical outputs.
- **Static rendering.** Every canvas renders a single frame. There is no animation loop. The whole simulation (2,000–4,000 steps) runs inside a single render pass.
- **Feature isolation.** Cover, framed plate, surfaces, and archive thumbnails each derive their own feature set from their own local RNG, without disturbing the main plate's state.
- **Clean RNG passing.** Each `Looper` receives its own RNG reference, so simulations never share state. Every canvas runs its own independent whirl.
- **Bounded wandering.** Loopers respawn when they leave the frame, so no looper can escape or run indefinitely.
- **Responsive.** The layout adapts from large desktop down to very small mobile devices (tested at 360px viewport width).
- **Accessible.** Supports `prefers-reduced-motion`. Pinch-zoom is enabled.

### Browser support

Tested in current versions of:

- Chrome / Edge
- Firefox
- Safari (desktop and iOS)

---

## Licensing

All Ephemeral Whirls compositions are **seed-documented** and available for licensing across textile, surface, and print applications.

- **Standard licenses** cover single-product production runs.
- **Commercial use, custom editions, or exclusive rights** are available on request.

Each license is issued against a specific seed ID. Regeneration of the same seed produces the identical composition — ensuring reproducibility between artist, studio, and manufacturer.

For licensing enquiries: [reyhanehdaneshdoost@gmail.com](mailto:reyhanehdaneshdoost@gmail.com)

---

## Commission

Ephemeral Whirls is a generative design system, not a fixed artwork. It can be adapted for specific briefs:

| Service     | Description                                                       |
|-------------|-------------------------------------------------------------------|
| Licensing   | Existing seeds from the archive, licensed for production use      |
| Commission  | New compositions designed to your palette, repeat, and product    |
| Systems     | A private generative tool built for your studio's ongoing use     |

To begin a conversation: [reyhanehdaneshdoost@gmail.com](mailto:reyhanehdaneshdoost@gmail.com)

---

## Series

Ephemeral Whirls is part of a computational textile series. Each volume approaches ornament from a different structural angle:

| Volume                     | Structure                    | Motion                     |
|----------------------------|------------------------------|----------------------------|
| Girih 1                    | Islamic geometric            | Static                     |
| Arachne                    | Rotating rings               | Static                     |
| Baroque Me Baby            | Baroque frames               | Static                     |
| Bezier 1                   | Concentric curves            | Static                     |
| Bezier 2                   | Single rotating curve        | Animated (plate)           |
| Brownian Graphe            | Graph networks               | Animated + interactive     |
| Celestial Grove            | Recursive branch trees       | Static                     |
| ChaotiColor                | Cellular automata            | Static                     |
| Citrus Mosaic              | Arc-and-triangle tiles       | Static                     |
| Crazy Knight Curve         | Knight's-tour smooth path    | Static                     |
| Crazy Knight Line          | Knight's-tour gradient       | Static                     |
| Crazy Letter               | Framed wavy lines            | Static                     |
| cyPollock                  | Scattered branch field       | Static                     |
| Digital Pollen             | Noise-driven texture         | Static                     |
| Draconic Fractals          | Tiled dragon curve           | Static                     |
| Dreamscape Watercolors     | Layered watercolor blooms    | Static                     |
| Elliott Waves              | Financial chart              | Static                     |
| Ellipses                   | Concentric elliptical rings  | Static                     |
| Enigma Sudoku              | Playable 9×9 puzzle          | Interactive (plate)        |
| **Ephemeral Whirls**       | **Wandering looper field**   | **Static**                 |

The series is designed as a coherent whole — same page structure, same seed logic, same licensing and commission terms — so that each volume can be presented individually or as part of a larger body of work.

---

## Credits

- **Design & Generative System** — Reyhaneh Daneshdoost
- **Typefaces** — Cormorant Garamond · DM Mono
- **Platform** — Reyrove Studio
- **Edition** — Ephemeral Whirls, Autumn 2026

### On AI tools

Where technical obstacles were encountered, AI tools were used for debugging and code optimization. Every structural, aesthetic, and conceptual decision remained the artist's own.

---

## Links

- Website — [reyrove.github.io](https://reyrove.github.io/)
- Instagram — [@rey._.rove](https://www.instagram.com/rey._.rove/)
- LinkedIn — [Reyhaneh Daneshdoost](https://www.linkedin.com/in/reyhaneh-daneshdoost-730481160/)
- X — [@reyrove](https://x.com/reyrove)

---

© Ephemeral Whirls · All compositions reproducible by seed · Computational Textile Design