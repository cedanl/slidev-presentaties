# CEDA Clidev Presentations

Presentation repository for CEDA (Centre for Educational Data Analytics) using the Npuls house style, built on [Slidev](https://sli.dev).

---

## Prerequisites

**Node.js 18+**

| OS | Install |
|----|---------|
| macOS | `brew install node` or [nodejs.org](https://nodejs.org) |
| Windows | `winget install OpenJS.NodeJS` or [nodejs.org](https://nodejs.org) |
| Linux (Debian/Ubuntu) | `sudo apt install nodejs npm` |
| Linux (other) | `nvm install 18` via [nvm](https://github.com/nvm-sh/nvm) |

Check with `node --version` — needs to be v18 or higher.

---

## Setup

```bash
git clone https://github.com/cedanl/clidev-presentations.git
cd clidev-presentations
npm install
```

Slidev is included as a dev dependency, nothing to install globally.

---

## Running a presentation

```bash
npx slidev YYMMDD_topic.md --open
```

Opens at `http://localhost:3030` with hot reload.

| Key | Action |
|-----|--------|
| Space / Arrow right | Next slide |
| Shift+Space / Arrow left | Previous slide |
| `P` | Presenter mode |
| `O` | Slide overview |
| `F` | Fullscreen |

---

## Creating with Claude Code (recommended)

Claude Code reads `CLAUDE.md` automatically and applies the correct Npuls styling, backgrounds, and illustrations.

**1. Install Claude Code**

```bash
npm install -g @anthropic-ai/claude-code
```

**2. Install the Slidev skill**

```bash
npx skills add slidevjs/slidev
```

**3. Open the project and describe what you need**

```bash
cd clidev-presentations
claude
```

```
Make a 20-minute presentation about learning analytics for institutional staff.
Date: 26 March 2026.
```

---

## Adding a presentation manually

```bash
touch YYMMDD_topic.md
mkdir -p public/presentations/YYMMDD_topic
```

Name files `YYMMDD_topic.md` (e.g. `260320_new_topic.md`). See `CLAUDE.md` for templates, slide rules, and the full list of available backgrounds and illustrations.

---

## Exporting

```bash
npx slidev export YYMMDD_topic.md             # PDF
npx slidev export YYMMDD_topic.md --format pptx
npx slidev export YYMMDD_topic.md --format png
```

---

## Project structure

```
clidev-presentations/
├── YYMMDD_topic.md              # Presentations
├── CLAUDE.md                    # Templates and styling rules
└── public/
    ├── npuls/
    │   ├── powerpoint_slides/   # Backgrounds (Slide1-19.PNG)
    │   ├── powerpoint_illustrations/  # 70+ SVG icons
    │   ├── npuls_logo.jpg
    │   └── Npuls_lettertype/    # Custom fonts
    ├── ceda_contributors/       # Team photos
    └── presentations/
        └── YYMMDD_topic/        # Per-presentation assets
```
