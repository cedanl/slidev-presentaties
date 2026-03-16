# CEDA Clidev Presentations

Presentation repository for CEDA (Centre for Educational Data Analytics) using the Npuls house style. Built on [Slidev](https://sli.dev) with an AI-assisted workflow via Claude Code.

---

## Prerequisites

**Node.js 18+** is the only hard requirement.

| OS | Install |
|----|---------|
| macOS | `brew install node` or download from [nodejs.org](https://nodejs.org) |
| Windows | `winget install OpenJS.NodeJS` or download from [nodejs.org](https://nodejs.org) |
| Linux (Debian/Ubuntu) | `sudo apt install nodejs npm` |
| Linux (other) | Use [nvm](https://github.com/nvm-sh/nvm): `nvm install 18` |

Verify: `node --version` should print `v18.x` or higher.

---

## Setup

```bash
git clone https://github.com/cedanl/clidev-presentations.git
cd clidev-presentations
npm install
```

No global installs needed — Slidev is included as a dev dependency.

---

## Running a presentation

```bash
npx slidev 260311_clidev.md --open
```

Opens at `http://localhost:3030` with hot reload.

**Keyboard shortcuts during presentation:**

| Key | Action |
|-----|--------|
| Space / Arrow right | Next slide |
| Shift+Space / Arrow left | Previous slide |
| `P` | Presenter mode (notes + next slide preview) |
| `O` | Slide overview |
| `F` | Fullscreen |

---

## Available presentations

| File | Topic |
|------|-------|
| `260311_clidev.md` | Clidev — Slidev + Claude Code workflow |
| `260311_1cijferho_update.md` | 1CijferHO update |
| `260312_assistentie.md` | Assistentie |
| `260310_claude_code_skills.md` | Claude Code skills |
| `2603_1CHO_update_Avans_Windesheim.md` | 1CHO update Avans & Windesheim |

---

## Claude Code setup (recommended)

Claude Code lets you create and edit presentations with natural language. It reads `CLAUDE.md` automatically and applies the correct Npuls styling.

**1. Install Claude Code**

| OS | Install |
|----|---------|
| macOS / Linux | `npm install -g @anthropic-ai/claude-code` |
| Windows | `npm install -g @anthropic-ai/claude-code` (run in PowerShell or Git Bash) |

**2. Install the required skills**

Skills give Claude Code knowledge about Slidev and the CEDA house style:

```bash
npx skills add slidevjs/slidev
```

**3. Open the project in Claude Code**

```bash
claude
```

Then describe what you need:

```
Make a 20-minute presentation about learning analytics for institutional staff.
Date: 26 March 2026. Use the CEDA Npuls house style.
```

---

## Adding a new presentation

**1. Create the file and asset folder**

```bash
touch 260320_new_topic.md
mkdir -p public/presentations/260320_new_topic
```

Files are named `YYMMDD_topic.md`. Put any presentation-specific images in the matching `public/presentations/` folder.

**2. Start from the title slide template**

```markdown
---
theme: default
class: text-center
title: Your Title
---

<style>
  @font-face {
    font-family: 'General Sans';
    src: url('/npuls/Npuls_lettertype/Npuls_lettertype_generalsans_regular.otf') format('opentype');
    font-weight: 400;
  }
  @font-face {
    font-family: 'General Sans';
    src: url('/npuls/Npuls_lettertype/Npuls_lettertype_generalsans_semibold.otf') format('opentype');
    font-weight: 600;
  }
  :deep(.slide) { font-family: 'General Sans', Arial, sans-serif; }
  :deep(h1), :deep(h2) { color: #DD784B !important; font-weight: 600; }
  :deep(h3), :deep(h4) { color: #000000 !important; }
  :deep(strong) { color: #3D68EC; }
  .title-subtitle { color: #000000 !important; font-weight: 400 !important; }
  #slide-content, .slidev-layout, [class*="slide"] {
    background-color: transparent !important;
    box-shadow: none !important;
  }
  #slide-content::before, #slide-content::after,
  .slidev-layout::before, .slidev-layout::after,
  [class*="slide"]::before, [class*="slide"]::after {
    display: none !important; content: none !important;
  }
  :deep(.slide)::after {
    content: '';
    position: absolute;
    bottom: 1.2rem; right: 1.2rem;
    width: 85px; height: 28px;
    background-image: url('/npuls/npuls_logo.jpg');
    background-size: contain; background-repeat: no-repeat;
    opacity: 0.9;
  }
</style>

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide1.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Your Title

## Your subtitle

<div class="mt-8 title-subtitle">
<strong>CEDA</strong> - Centre for Educational Data Analytics
</div>

---

# First content slide

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div class="mt-2" style="font-size: 0.85rem; line-height: 1.5;">

- Point one
- Point two
- Point three

</div>

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide17.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>
```

**3. Key rules to avoid overflow**

- Always wrap content in `<div style="font-size: 0.85rem; line-height: 1.5;">` — the default is too large
- Max 3-4 bullet points per slide; split if you need more
- Never use `background:` in frontmatter — always use the `<img>` method shown above
- Use `mt-2` or `mt-4` spacing; never `mt-6` or larger

See `CLAUDE.md` for the complete set of templates and rules.

---

## Exporting

```bash
# PDF
npx slidev export 260311_clidev.md

# PowerPoint
npx slidev export 260311_clidev.md --format pptx

# PNG per slide
npx slidev export 260311_clidev.md --format png
```

---

## Project structure

```
clidev-presentations/
├── YYMMDD_topic.md              # Presentations
├── package.json
├── CLAUDE.md                    # Styling rules for Claude Code
└── public/
    ├── npuls/
    │   ├── powerpoint_slides/   # Slide backgrounds (Slide1-19.PNG)
    │   ├── powerpoint_illustrations/  # 70+ SVG icons
    │   ├── npuls_logo.jpg
    │   └── Npuls_lettertype/    # Custom fonts
    ├── ceda_contributors/       # Team photos
    └── presentations/
        └── YYMMDD_topic/        # Per-presentation assets
```
