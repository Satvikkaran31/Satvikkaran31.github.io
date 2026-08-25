# Satvik Karan — Portfolio

A single-file, zero-dependency portfolio site. Dark "neural lab" theme with a live
interactive node-graph background (a nod to the graph/link-prediction work), a bento
project grid, a terminal-style about panel, and a full light theme.

Everything lives in **`index.html`** — no build step, no framework, no external requests.
It works offline and deploys anywhere that serves a static file.

## Run it locally

Just open the file:

```bash
xdg-open index.html      # Linux
```

Or serve it (nicer for testing):

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Deploy

- **GitHub Pages** — push this folder to a repo, enable Pages on the `main` branch (root). Done.
- **Netlify / Vercel / Cloudflare Pages** — drag-and-drop the folder, or point it at the repo. No build command; publish directory is the root.

## Things to personalize (search `index.html` for these)

| What | Where / current value |
|------|-----------------------|
| GitHub link | `https://github.com/Satvikkaran31` (set) |
| LinkedIn link | `https://www.linkedin.com/in/satvik-karan/` (set) |
| Location | `Based in` → `India` (edit if wrong) |
| Email | `satvikkaran312003@gmail.com` (already set) |
| Availability | the `Available` status pill in the hero readout |

The email is used for the "Get in touch" and contact buttons.

## Project links

Each project card links to its source. Verified public links wired in:

| Project | Link(s) |
|---------|---------|
| Swadhyay Coaching Platform | [Live](https://swadhyay.co) · [Code](https://github.com/Satvikkaran31/Swadhyay) |
| Deepfake & Fake-News Detector | [Code](https://github.com/Satvikkaran31/ASLINAKLI_DEEPFAKE_DETECTOR) |
| Hinglish Hate-Speech Detection | [Code](https://github.com/Satvikkaran31/HINGLISH_HATE_SPEECH_DETECTION_) |
| Employee Attrition on Hadoop | [Code](https://github.com/Satvikkaran31/EMPLOYEE_ATTRITION_ANALYSIS_USING_HADOOP) |
| AI Resume Generator | [Code](https://github.com/Satvikkaran31/RESUME_GENERATOR_APP-not-finished-) |
| MUGAMMA | 🔒 Private client repo (no public link) |

## Editing content

- **Projects** live in the `<section id="work">` bento grid — each is an `<article class="card">`.
  Sizing classes: `c-4` (large hero), `c-2t` (2-wide, tall), `c-2`, `c-3`.
- **Stack** chips are in `<section id="stack">`.
- **Colors** are CSS custom properties at the top of the `<style>` block — light palette on
  `:root`, dark palette repeated under the `prefers-color-scheme` media query and
  `[data-theme="dark"]`. The graph canvas reads `--accent` / `--accent-2` automatically.

## Interactions (things to try)

- **Boot sequence** on first load (skippable; shown once per browser session).
- **Decoding text** — the name and every section heading scramble into place.
- **Signal packets** travel along the graph edges continuously.
- **Click the background** anywhere to fire a shockwave that ripples through the nodes.
- **Cursor wiring** — nodes near your pointer wire themselves to it.
- **Tilt + spotlight cards** — project cards tilt in 3D and light up under the cursor.
- **Live uptime clock** in the footer.
- **Hidden easter egg** — the Konami code (`↑ ↑ ↓ ↓ ← → ← → B A`) toggles "overclock" mode: faster mesh, denser links, hot-pink/gold palette. Enter it again to restore.

## Accessibility & behavior

- Respects `prefers-reduced-motion` (static graph, no boot, no cursor trail, no tilt, instant reveals).
- Theme toggle persists to `localStorage`; default follows the OS setting.
- Custom cursor only activates on fine-pointer (mouse) devices.
