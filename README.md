# CEDA Slidev Presentaties

Presentation repository for CEDA (Centre for Educational Data Analytics) using the Npuls house style.

---

## Getting started

**Prerequisites:** Node.js 18+

```bash
# Clone the repo
git clone https://github.com/cedanl/slidev-presentaties.git
cd slidev-presentaties

# Install dependencies
npm install
```

That's it. No global installs needed — Slidev is included as a dev dependency.

---

## Running a presentation

```bash
npx slidev 260311_clidev.md --open
```

This starts a local dev server at `http://localhost:3030` with hot reload.

**Useful keyboard shortcuts during presentation:**

| Key | Action |
|-----|--------|
| Space / Arrow right | Next slide |
| Shift+Space / Arrow left | Previous slide |
| P | Presenter mode (shows notes + next slide) |
| O | Overview / slide grid |
| F | Fullscreen |

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

## Adding a new presentation

### 1. Create the file

Name it `YYMMDD_topic.md` (e.g. `260320_new_topic.md`).

```bash
touch 260320_new_topic.md
mkdir -p public/presentations/260320_new_topic
```

The `public/presentations/260320_new_topic/` folder is where you put any images or assets specific to this presentation.

### 2. Start from the title slide template

```markdown
---
theme: default
class: text-center
title: Your Presentation Title
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
    display: none !important;
    content: none !important;
  }

  :deep(.slide)::after {
    content: '';
    position: absolute;
    bottom: 1.2rem;
    right: 1.2rem;
    width: 85px;
    height: 28px;
    background-image: url('/npuls/npuls_logo.jpg');
    background-size: contain;
    background-repeat: no-repeat;
    opacity: 0.9;
  }
</style>

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide1.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Your Title

## Your subtitle

<div class="mt-8 title-subtitle">
**CEDA** - Centre for Educational Data Analytics
</div>

---

# First content slide

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div class="mt-4" style="font-size: 0.85rem; line-height: 1.5;">

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

### 3. Run and preview

```bash
npx slidev 260320_new_topic.md --open
```

### 4. Key rules to avoid overflow

- Wrap content in `<div style="font-size: 0.85rem; line-height: 1.5;">` — the default font size is too large
- Max 3-4 bullet points per slide; split into two slides if you need more
- Never use the `background:` frontmatter property for backgrounds — always use the `<img>` approach shown above
- Spacing: use `mt-2` or `mt-4`, never `mt-6` or larger

See `CLAUDE.md` for the full set of styling rules and templates.

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

## Using Claude Code

Open the project in Claude Code and ask it to create or update presentations. Claude reads `CLAUDE.md` automatically and applies the correct Npuls styling, backgrounds, illustrations, and presenter notes.

```bash
claude
```

Then just describe what you need:

```
Make a presentation about [topic] for [audience].
Duration: ~20 minutes. Date: 26 March 2026.
Use the CEDA Npuls house style.
```

---

## Project structure

```
slidev-presentaties/
├── YYMMDD_topic.md              # Presentations
├── package.json
├── CLAUDE.md                    # Styling rules + templates for Claude
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
