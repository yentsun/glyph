# Glyph

**A console-inspired UI theme** — a small React design system rendered entirely in
JetBrains Mono, on a Solarized Light/Dark palette. Square edges, hairline rules, ASCII
meters, `grep`-style prompts, status dots, and an optional CRT scanline overlay.

> **Live design book:** https://yentsun.github.io/glyph
> (enable it under **Settings → Pages → Source: `main`**)

---

## Ideas

Glyph treats the terminal as a design language, not a gimmick:

- **One typeface, everywhere.** JetBrains Mono with ligatures. The mono grid is the point —
  numbers align, ASCII art holds, every surface reads like a console.
- **Solarized, tokenized.** A monochrome base scale carries structure; eight accents carry
  meaning. Nothing hard-codes a hex — components read semantic CSS variables
  (`--bg`, `--rule`, `--text-em`, `--accent`, …) that remap between light and dark.
- **Three independent dials on the root element.** Theme, accent, and density are plain
  `data-*` attributes; set them once and every token cascades.
  - `data-theme` — `light` | `dark`
  - `data-accent` — `blue · cyan · green · yellow · orange · red · magenta · violet`
  - `data-density` — `compact` | *(unset = normal)* | `comfortable`
- **Square and hairline.** No rounded corners, no drop shadows — borders and color do the work.
- **Opt-in flourish.** A CRT scanline + vignette overlay is available but never on by default.

## What's in the book

A single, self-contained `index.html` documents the system with **live React specimens**,
copy-paste **JSX snippets**, and **props tables** for each component:

- **Foundations** — Color (base scale, accents, semantic tokens), Typography, Theming
- **Components** — Buttons · Avatars (`Avatar` / `PersonCell`) · Status badges · Tags ·
  Form elements (search, select, checkbox/radio/switch) · Dropdown · Tabs · KPI tiles ·
  Progress · Tables · Modals · Photo cards

Use the controls in the top bar to flip theme / accent / density / CRT — the whole book
responds exactly as a real app would at runtime.

## Usage

`index.html` is fully self-contained (React + styles inlined). To view it:

```bash
# just open it
open index.html            # macOS
xdg-open index.html        # Linux

# or serve it
python3 -m http.server 8000   # then visit http://localhost:8000
```

No build step, no dependencies, works offline.

## Tokens at a glance

```css
/* reach for semantic tokens — never a raw hex */
.panel {
  background: var(--bg-alt);
  border: 1px solid var(--rule);
  color: var(--text-em);
}
```

| Token | Role |
|---|---|
| `--bg` / `--bg-alt` / `--bg-dim` | page · raised panel · subtle fill |
| `--rule` | borders & grid lines |
| `--text` / `--text-em` / `--text-mut` | body · emphasized · muted |
| `--accent` / `--accent-bg` | active accent · accent wash |

## License

MIT — see [`LICENSE`](LICENSE).
