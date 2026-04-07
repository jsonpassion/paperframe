# PaperFrame

> AI paper review thumbnail generator. Pixel art, 16 themes, single HTML.

<p align="center">
  <img src="https://img.shields.io/badge/Single_HTML-blue" alt="Single HTML">
  <img src="https://img.shields.io/badge/Zero_Dependencies-green" alt="Zero Dependencies">
  <img src="https://img.shields.io/badge/No_Server-orange" alt="No Server">
  <img src="https://img.shields.io/github/license/jsonpassion/paperframe" alt="MIT License">
</p>

<p align="center">
  <a href="https://jsonpassion.github.io/paperframe/">Live Demo</a>
</p>

---

## Features

| Feature | Details |
|---|---|
| **Pixel Art 13 types** | MLP, Transformer, Robot, Brain, GPU, Vision Eye, GNN, DNA/Sequence, Tokens/LLM, Diffusion, RL Agent, CNN, VAE |
| **Color Themes 16** | Classic Blue, Deep Teal, Royal Purple, Volcanic, Midnight Slate, Deep Forest, Amber Dusk, Deep Indigo, Cyberpunk, Arctic, Crimson, Tactical Olive, Rose Gold, Ocean Depth, Synthwave, Matcha |
| **BG Code Types 5** | x86 Assembly, Python/PyTorch, Hex Dump, CUDA/C++, Math Notation |
| **Layout Controls** | Window position (left/right/center), pixel size, BG density |
| **Export** | PNG 1200×630 (OG Image / YouTube thumbnail standard) |
| **Randomize** | Re-generate background code pattern |
| **Config JSON** | Copy settings as JSON for reproducibility |

---

## Quick Start

### Option A: Use the live demo

https://jsonpassion.github.io/paperframe/

### Option B: Run locally

```bash
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

Or with a local server:

```bash
python3 -m http.server 8080
# → http://localhost:8080
```

---

## Output

- **1200 × 630 px** — Open Graph Image standard
- Works for YouTube thumbnails, blog covers, GitHub README headers

---

## Customization

### Add pixel art

Add to the `ARTS` array in `index.html`:

```javascript
function artMyTopic(ctx, x, y, w, h, t) {
  ctx.fillStyle = t.accent;
  ctx.fillRect(x, y, w, h);
}

const ARTS = [
  ...existing,
  { id: 'mytopic', name: 'My Topic', fn: artMyTopic },
];
```

### Add color themes

```javascript
const THEMES = [
  ...existing,
  {
    id: 'custom', name: 'Custom Theme',
    bg: '#1a1a2e', bg2: '#16213e', win: '#0f3460',
    text: '#ffffff', accent: '#e94560', dark: '#0a0a15',
  },
];
```

---

## License

MIT — free to use, modify, and distribute.

Built by [Jason Lee](https://www.linkedin.com/in/json-lee) as part of the [PaperGoat](https://papergoat.beehiiv.com/) project.
