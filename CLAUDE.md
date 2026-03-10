# CEDA Slidev Presentations - Documentation

## Project Overview

Dit project bevat meerdere Slidev presentaties voor CEDA (Centre for Educational Data Analytics). Alle presentaties volgen de **Npuls huisstijl** en gebruiken een gedeelde asset structuur.

**Naming Convention**: `YYMMDD_presentation_name.md`
- Voorbeeld: `2603_1CHO_update_Avans_Windesheim.md`
- Voorbeeld: `1504_NFWA_introductie.md`

---

## Project Structuur

```
slidev-presentaties/
├── YYMMDD_presentation_name.md   ← Presentatie bestanden
├── CLAUDE.md                     ← Deze documentatie
├── README.md                     ← Project readme
├── components/                   ← Custom Slidev components (optioneel)
├── snippets/                     ← Herbruikbare code snippets
└── public/                       ← ALLE statische assets
    ├── npuls/                   ← SHARED Npuls branding assets
    │   ├── powerpoint_slides/   ← Slide backgrounds (Slide1.PNG - Slide19.PNG)
    │   ├── powerpoint_illustrations/ ← Illustrations (70+ SVG icons)
    │   ├── npuls_images/        ← 101 template assets (image1.png - image101.png)
    │   ├── npuls_logo.jpg       ← Npuls logo
    │   ├── Npuls_powerpoint-template.potx
    │   ├── Npuls_huisstijlgids_2025.pdf
    │   └── Npuls_lettertype/    ← Font files
    ├── ceda_contributors/       ← CEDA team member photos (SHARED)
    │   ├── aslam_tanjung.jpg
    │   └── tomer_iwan.jpg
    └── presentations/           ← PRESENTATION-SPECIFIC assets
        ├── 2603_1CHO_update_Avans_Windesheim/
        │   └── [project_specific_images].jpg
        └── [andere_presentatie]/
            └── [specifieke_images].jpg
```

---

## Nieuwe Presentatie Maken

### Stap 1: Creëer presentatie bestand

```bash
# Naming convention: YYMMDD_naam.md
touch 0304_new_presentation.md
```

### Stap 2: Creëer asset folder

```bash
mkdir -p public/presentations/0304_new_presentation
```

### Stap 3: Voeg presentatie-specifieke images toe

```bash
cp your_images/* public/presentations/0304_new_presentation/
```

### Stap 4: Start presentatie

```bash
slidev 0304_new_presentation.md --open
```

---

## Npuls Huisstijl / Branding

Alle presentaties volgen de **Npuls huisstijl**. Branding assets zijn beschikbaar in `public/npuls/`:

### Kleuren (Npuls Color Palette)

**Primaire Kleuren:**
```css
--npuls-blue: #3D68EC     /* Hoofdkleur voor titels */
--npuls-orange: #DD784B   /* Accent kleur voor subtitels */
--npuls-black: #000000    /* Tekst kleur */
--npuls-white: #FFFFFF    /* Achtergrond */
```

**Secundaire Kleuren:**
```css
--npuls-green: #00AF81    /* Accent */
--npuls-yellow: #F4D74B   /* Accent */
--npuls-pink: #F4D9DC     /* Accent */
```

### Typografie

**Fonts:**
- **Primair**: General Sans (custom Npuls font in `/npuls/Npuls_lettertype/`)
- **Secundair**: Cooper Light BT (voor quotes/introducties)
- **Fallback**: Arial, Helvetica

**Beschikbare Font Files:**
- `Npuls_lettertype_generalsans_regular.otf` - Regular (400)
- `Npuls_lettertype_generalsans_semibold.otf` - Semi-Bold (600)
- `Npuls_lettertype_cooper_light_bt.ttf` - Light (300)

**Font Weights:**
- Regular (400): Body text
- Semi-Bold (600): H1, H2, H3
- Light (300): Cooper Light voor quotes

**Font Loading in CSS:**
```css
@font-face {
  font-family: 'General Sans';
  src: url('/npuls/Npuls_lettertype/Npuls_lettertype_generalsans_regular.otf') format('opentype');
  font-weight: 400;
  font-style: normal;
}

@font-face {
  font-family: 'General Sans';
  src: url('/npuls/Npuls_lettertype/Npuls_lettertype_generalsans_semibold.otf') format('opentype');
  font-weight: 600;
  font-style: normal;
}

@font-face {
  font-family: 'Cooper Light BT';
  src: url('/npuls/Npuls_lettertype/Npuls_lettertype_cooper_light_bt.ttf') format('truetype');
  font-weight: 300;
  font-style: normal;
}
```

**Usage:**
```css
:deep(.slide) {
  font-family: 'General Sans', Arial, Helvetica, sans-serif;
}
```

### Logo

Het Npuls logo kan automatisch op elke slide verschijnen via CSS:
- **Locatie**: `/npuls/npuls_logo.jpg`
- **Implementatie**: Via `::after` pseudo-element in CSS (zie voorbeeld presentatie)

---

## Slide Backgrounds - BELANGRIJK! ⚠️

### Het Probleem met Slidev Backgrounds

Slidev voegt **automatisch een donkere overlay** toe over backgrounds wanneer je de `background:` property gebruikt.

### Onze Oplossing

**❌ NIET gebruiken:**
```yaml
---
background: /npuls/powerpoint_slides/Slide1.PNG
---
```

**✅ WEL gebruiken:**
```markdown
---
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide1.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Slide Title
```

### Waarom Deze Aanpak?

1. ✅ Geen overlays
2. ✅ Geen filters
3. ✅ 100% originele Npuls images zichtbaar
4. ✅ Volledige controle over de presentatie

### Beschikbare Background Images

Locatie: `/npuls/powerpoint_slides/`

| Bestand | Gebruik |
|---------|---------|
| `Slide1.PNG` | Titelslide |
| `Slide2.PNG` | Inhoudsopgave / Over Ons | Zet tekst rechts, want er is afbeelding links
| `Slide3.PNG` | Standaard content slide |
| `Slide13.PNG`, `Slide14.PNG`, `Slide15.PNG` | Hoofdstuk slide, wissel af. Geef ook opmaak van tekst (dikker bv) zodat het inderdaad lijkt op hoofdstuk |
| `Slide10.PNG` | Alternatieve content slide |
| `Slide17.PNG` | Afsluiting slide GEEN TEXT|

---

## Asset Paths

### Shared Assets

Deze zijn beschikbaar voor ALLE presentaties:

```markdown
<!-- Background slides -->
<img src="/npuls/powerpoint_slides/Slide1.PNG" />

<!-- Logo -->
background-image: url('/npuls/npuls_logo.jpg');

<!-- Template images (101 stuks) -->
<img src="/npuls/npuls_images/image1.png" />
<img src="/npuls/npuls_images/image42.svg" />

<!-- CEDA Contributors -->
<img src="/ceda_contributors/aslam_tanjung.jpg" />
<img src="/ceda_contributors/tomer_iwan.jpg" />

<!-- Illustrations (70+ SVG icons available) -->
<img src="/npuls/powerpoint_illustrations/Puzzelstuk 3D.svg" />
<img src="/npuls/powerpoint_illustrations/Stopwatch.svg" />
<img src="/npuls/powerpoint_illustrations/laptop.svg" />
```

### Npuls Illustrations

70+ SVG illustraties beschikbaar in `/npuls/powerpoint_illustrations/`

**Categorieën:**
- **Personen**: Dame blauw pak, Man, Laptopman, Man in rolstoel
- **Objecten**: Laptop, Boeken, Pakket, Stopwatch, Lamp
- **Concepten**: Puzzelstuk, Connecties, Blokken stapel, Netwerk
- **Symbolen**: Vaantje met vink, Pijlen, Ster, Document
- **Educatie**: Boeken, Gebouw, Learninganalystics
- **Tech**: Chip, Data, Servers, PC

**Gebruik:**
```html
<!-- Plaats illustratie in hoek (conflicteert niet met tekst) -->
<img src="/npuls/powerpoint_illustrations/Stopwatch.svg"
     style="position: absolute; top: 2rem; right: 2rem; width: 120px; height: auto; opacity: 1.0;"
     alt="Stopwatch" />
```

**Best Practices:**
- ✅ Plaats in hoeken (top/bottom + left/right) om tekst niet te overlappen
- ✅ Gebruik `position: absolute` voor vrijheid in plaatsing
- ✅ Gebruik `opacity: 1.0` - illustraties mogen opvallen en aanwezig zijn
- ✅ Houd illustraties relevant bij slide content
- ✅ Gebruik `width: 120-160px` voor goede balans
- ✅ Plaats illustraties BUITEN content divs
- ❌ Plaats NIET over belangrijke tekst
- ❌ Gebruik NIET te grote illustraties (max 200px)
- ❌ Overlaad slides NIET met te veel illustraties (max 1-2 per slide)

**Overlap Voorkomen - Strategieën:**

1. **Plaats illustraties BUITEN de content div:**
```html
<!-- GOED: Illustratie na de content -->
<div class="mt-8">
  <h1>Slide Title</h1>
  <p>Content here...</p>
</div>

<img src="/npuls/powerpoint_illustrations/example.svg"
     style="position: absolute; bottom: 2rem; right: 2rem;
            width: 140px; opacity: 0.5;" />

<!-- FOUT: Illustratie binnen content div -->
<div class="mt-8">
  <img src="..." style="position: absolute..." />
  Content gets pushed around...
</div>
```

2. **Gebruik volledige opacity (1.0):**
```html
<!-- Illustraties mogen opvallen en zichtbaar zijn -->
<img src="/npuls/powerpoint_illustrations/example.svg"
     style="position: absolute; bottom: 1rem; right: 2rem;
            width: 140px; opacity: 1.0;" />
```

3. **Kleinere illustraties (120-160px):**
```html
<!-- Compact = meer ruimte voor tekst -->
<img src="/npuls/powerpoint_illustrations/example.svg"
     style="width: 140px; opacity: 1.0;" />
```

4. **Strategische plaatsing:**
- **Bottom corners**: Vaak minste tekst
- **Top right**: Meestal vrij
- **Center (alleen voor kleine accenten)**: Gebruik kleine illustraties + verschuif content
- **Let op bij code blocks**: Nemen veel ruimte

**Voorbeeld: Gecentreerde illustratie met content shift:**
```html
<!-- Kleine pijl in center -->
<img src="/npuls/powerpoint_illustrations/Pijlen rechts grafisch.svg"
     style="position: absolute; top: 50%; left: 42%;
            transform: translate(-50%, -50%); width: 80px; opacity: 1.0; z-index: 0;" />

<!-- Content iets naar rechts -->
<div class="grid grid-cols-2 gap-8" style="margin-left: 3rem; position: relative; z-index: 1;">
  Content hier
</div>
```

5. **Test altijd in development mode:**
```bash
slidev presentation.md --open
```
- Check verschillende slides
- Resize venster om responsive gedrag te zien
- Test op beamer/projector als mogelijk

### Presentation-Specific Assets

Voor presentatie `YYMMDD_naam.md`, plaats images in `public/presentations/YYMMDD_naam/`:

```markdown
<!-- Voorbeeld voor presentatie 2603_1CHO_update_Avans_Windesheim.md -->
<img src="/presentations/2603_1CHO_update_Avans_Windesheim/screenshot.png" />
<img src="/presentations/2603_1CHO_update_Avans_Windesheim/diagram.jpg" />

<!-- CEDA contributors gebruik je vanuit de shared folder -->
<img src="/ceda_contributors/aslam_tanjung.jpg" />
```

---

## Slide Structuur

### Frontmatter

Elke slide begint met een YAML frontmatter block:

```yaml
---
class: text-center        # Optioneel: styling classes
layout: default          # Optioneel: layout type
---
```

**Belangrijke regels:**
- ❌ Gebruik GEEN `theme:` property (zorgt voor overlays)
- ❌ Gebruik GEEN `layout: cover` (voegt overlays toe)
- ❌ Gebruik GEEN `background:` property (voegt overlays toe)
- ✅ Gebruik alleen `class:` voor styling

### Section Breaks

Voor grote sectie-overgangen:

```markdown
---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide16.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Section Title

## Subtitle
```

### Content Slides

Normale slides zonder background:

```markdown
---
---

# Slide Title

### Subsection

Content here...
```

---

## Slide Templates

### Template: Title Slide (Slide1.PNG)

```markdown
---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide1.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Presentatie Titel

## Ondertitel

<div class="mt-8 text-xl">
<strong>CEDA</strong> - Centre for Educational Data Analytics
</div>
```

### Template: Agenda/Over Ons (Slide2.PNG)

**⚠️ Belangrijk: Tekst RECHTS plaatsen (afbeelding is links)**

```markdown
---
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide2.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="margin-left: 50%; padding-left: 2rem;">

# Agenda

<div class="mt-8">

- Onderwerp 1
- Onderwerp 2
- Onderwerp 3

</div>

</div>
```

### Template: Standaard Content (Slide3.PNG)

```markdown
---
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Slide Titel

<div class="mt-8">

### Subsectie

- Bullet point 1
- Bullet point 2
- Bullet point 3

</div>
```

### Template: Hoofdstuk Slide (Slide13/14/15.PNG)

**⚠️ Belangrijk: Gebruik DIKKE tekstopmaak (bold/thick) zodat het als hoofdstuk herkenbaar is**

**⚠️ Wissel af tussen Slide13.PNG, Slide14.PNG, Slide15.PNG**

```markdown
---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide13.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="font-weight: 700; font-size: 3.5rem;">

# Hoofdstuk Titel

</div>

<div style="font-weight: 600; font-size: 2rem; margin-top: 1rem;">

## Ondertitel

</div>
```

### Template: Presenter Slide

```markdown
---
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Presentatie door

<div class="grid grid-cols-2 gap-8 mt-8">
  <div class="text-center">
    <img src="/ceda_contributors/aslam_tanjung.jpg"
         alt="Aslam Tanjung"
         class="h-56 rounded-lg mx-auto shadow-lg">
    <h3 class="mt-4 text-xl font-bold">Aslam Tanjung</h3>
    <p class="mt-2 text-base font-semibold">Data Scientist @ CEDA</p>
    <p class="mt-3 text-sm leading-relaxed">Korte beschrijving</p>
  </div>
  <div class="text-center">
    <img src="/ceda_contributors/tomer_iwan.jpg"
         alt="Tomer Iwan"
         class="h-56 rounded-lg mx-auto shadow-lg">
    <h3 class="mt-4 text-xl font-bold">Tomer Iwan</h3>
    <p class="mt-2 text-base font-semibold">Data Engineer @ CEDA</p>
    <p class="mt-3 text-sm leading-relaxed">Korte beschrijving</p>
  </div>
</div>
```

### Template: Closing Slide (Slide17.PNG)

**⚠️ KRITIEK: GEEN TEKST op deze slide - alleen de background!**

```markdown
---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide17.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>
```

---

## CSS Styling

Custom styling plaats je in een `<style>` block aan het begin van je presentatie bestand.

### Npuls Kleuren Toepassen

```css
<style>
  /* Npuls Custom Fonts */
  @font-face {
    font-family: 'General Sans';
    src: url('/npuls/Npuls_lettertype/Npuls_lettertype_generalsans_regular.otf') format('opentype');
    font-weight: 400;
    font-style: normal;
  }

  @font-face {
    font-family: 'General Sans';
    src: url('/npuls/Npuls_lettertype/Npuls_lettertype_generalsans_semibold.otf') format('opentype');
    font-weight: 600;
    font-style: normal;
  }

  @font-face {
    font-family: 'Cooper Light BT';
    src: url('/npuls/Npuls_lettertype/Npuls_lettertype_cooper_light_bt.ttf') format('truetype');
    font-weight: 300;
    font-style: normal;
  }

  /* Npuls Branding Colors */
  :root {
    --npuls-blue: #3D68EC;
    --npuls-orange: #DD784B;
    --npuls-green: #00AF81;
    --npuls-yellow: #F4D74B;
    --npuls-pink: #F4D9DC;
    --npuls-black: #000000;
    --npuls-white: #FFFFFF;
  }

  /* Headings met Npuls kleuren */
  :deep(h1) { color: #3D68EC !important; }      /* Blauw */
  :deep(h2) { color: #DD784B !important; }      /* Oranje */
  :deep(h3), :deep(h4), :deep(h5), :deep(h6) {
    color: #000000 !important;                  /* Zwart */
  }

  /* Links */
  :deep(a) { color: #3D68EC; }
  :deep(a:hover) { color: #DD784B; }

  /* Strong/Bold tekst */
  :deep(strong) { color: #3D68EC; }
</style>
```

### Overlay Removal CSS

**KRITIEK - NIET VERWIJDEREN:**

```css
/* AGGRESSIVE OVERLAY REMOVAL */
* {
  box-shadow: none !important;
}

#slide-content,
.slidev-layout,
.slide-container,
[class*="slide"],
[id*="slide"] {
  background-color: transparent !important;
  box-shadow: none !important;
  filter: none !important;
}

/* Remove ALL pseudo-elements that could be overlays */
#slide-content::before,
#slide-content::after,
.slidev-layout::before,
.slidev-layout::after,
.slide-container::before,
.slide-container::after,
[class*="slide"]::before,
[class*="slide"]::after,
[class*="cover"]::before,
[class*="cover"]::after,
[class*="background"]::before,
[class*="background"]::after {
  display: none !important;
  content: none !important;
  opacity: 0 !important;
}
```

Deze CSS zorgt ervoor dat Slidev geen overlays toevoegt over je backgrounds.

### Npuls Logo op Elke Slide

```css
/* Npuls Logo on every slide */
:deep(.slide)::after {
  content: '';
  position: absolute;
  bottom: 1.2rem;
  right: 1.2rem;
  width: 85px;
  height: auto;
  background-image: url('/npuls/npuls_logo.jpg');
  background-size: contain;
  background-repeat: no-repeat;
  opacity: 0.9;
}
```

---

## Content Richtlijnen

### Slides die te vol zijn

Als een slide te veel content heeft:
1. ✅ Split de slide in meerdere slides
2. ✅ Gebruik `---` om een nieuwe slide te maken
3. ✅ Gebruik two-column layouts waar mogelijk

**Voorbeeld Two-Column:**
```html
<div class="grid grid-cols-2 gap-8">
  <div>
    Left column content
  </div>
  <div>
    Right column content
  </div>
</div>
```

### Text Readability

Op slides met backgrounds:
- Gebruik **duidelijke, grote fonts**
- Houd tekst **gecentreerd** waar mogelijk
- Vermijd te veel tekst per slide
- Gebruik **witruimte** effectief

### Presenter Cards Voorbeeld

```html
<div class="grid grid-cols-2 gap-8 mt-8">
  <div class="text-center">
    <img src="/ceda_contributors/aslam_tanjung.jpg"
         alt="Aslam Tanjung"
         class="h-56 rounded-lg mx-auto shadow-lg">
    <h3 class="mt-4 text-xl font-bold">Aslam Tanjung</h3>
    <p class="mt-2 text-base font-semibold">Data Scientist @ CEDA</p>
    <p class="mt-3 text-sm leading-relaxed">Gespecialiseerd in data pipelines en R packages</p>
  </div>
  <div class="text-center">
    <img src="/ceda_contributors/tomer_iwan.jpg"
         alt="Tomer Iwan"
         class="h-56 rounded-lg mx-auto shadow-lg">
    <h3 class="mt-4 text-xl font-bold">Tomer Iwan</h3>
    <p class="mt-2 text-base font-semibold">Data Engineer @ CEDA</p>
    <p class="mt-3 text-sm leading-relaxed">Expert in educational data analytics</p>
  </div>
</div>
```

---

## Development Workflow

### Start Development Server

**Vereiste**: Slidev globally geïnstalleerd
```bash
npm install -g @slidev/cli
```

**Start een presentatie:**
```bash
slidev 2603_1CHO_update_Avans_Windesheim.md --open
```

Server draait standaard op: `http://localhost:3030`

### Hot Reload

Slidev heeft hot-reload - wijzigingen in je `.md` bestand worden automatisch herladen.

### Keyboard Shortcuts

- `Space` / `→` : Volgende slide
- `Shift+Space` / `←` : Vorige slide
- `F` : Fullscreen
- `P` : Presenter mode (met notities)
- `D` : Dark mode toggle
- `G` : Go to slide (type slide number)
- `O` : Overview mode

### Export naar PDF

```bash
slidev export YYMMDD_presentation_name.md
```

**Export naar PowerPoint:**
```bash
slidev export YYMMDD_presentation_name.md --format pptx
```

---

## Creating Claude Code Skills

### Wat is een Claude Code Skill?

Een skill is een herbruikbare AI-prompt die Claude helpt om specifieke taken uit te voeren. Skills leven in `.claude/skills/` als Markdown bestanden en kunnen aangeroepen worden met `/skill-name`.

### Workflow: Van Voorbeeld naar Skill

**Stap 1: Verzamel voorbeelden**

Voordat je een skill maakt, verzamel eerst goede voorbeelden van de taak. Voor Slidev presentaties:
- Maak eerst handmatig 1-2 presentaties die de Npuls huisstijl perfect volgen
- Documenteer alle patronen en conventies in CLAUDE.md
- Test grondig om problemen te vinden (zoals de overlay issue)

**Stap 2: Toon Claude het "voor" en "na"**

```markdown
Ik wil een skill maken voor het genereren van Slidev presentaties.

VOOR (input):
- User geeft titel en inhoud van presentatie
- User geeft datum

NA (gewenste output):
- Volledig YYMMDD_naam.md bestand
- Correcte frontmatter
- Custom fonts (@font-face declarations)
- Overlay removal CSS
- Npuls branding kleuren
- Backgrounds zonder overlays
- Alle slides correct gestructureerd

Bekijk deze voorbeelden:
- 2603_1CHO_update_Avans_Windesheim.md
- 260310_claude_code_skills.md
- CLAUDE.md (voor alle conventies)

Maak een skill die dit automatisch kan genereren.
```

**Stap 3: Itereer en verfijn**

Claude's eerste versie is NIET perfect. Waarom niet?

⚠️ **Claude is non-deterministisch** - dezelfde prompt kan verschillende outputs geven:
- Eerste run: gebruikt Google Fonts (fout!)
- Tweede run: gebruikt custom fonts (goed!)
- Derde run: vergeet overlay removal CSS (fout!)

**Daarom:**
1. Test de skill meerdere keren
2. Vind patronen in de fouten
3. Voeg expliciete instructies toe:
   ```markdown
   **IMPORTANT:** NEVER use Google Fonts. ALWAYS use custom Npuls fonts.
   **CRITICAL:** ALWAYS include overlay removal CSS.
   ```
4. Herhaal tot de skill consistent werkt

**Stap 4: Maak de skill file**

Plaats in `.claude/skills/slidev-npuls.md`:

```markdown
---
description: Create Slidev presentations following Npuls branding
dependencies: []
---

# Slidev Npuls Presentation Generator

You are a specialist in creating Slidev presentations...

## Your Responsibilities
1. Generate Slidev presentations from user content
2. Apply Npuls branding consistently
3. Follow CLAUDE.md conventions

## File Naming Convention
Always use: YYMMDD_presentation_name.md

## Required Structure
[Gedetailleerde instructies hier...]

## Validation Checklist
Before delivering:
- ✅ Custom fonts loaded
- ✅ Overlay removal CSS included
- ✅ Backgrounds use <img> method
...
```

### Best Practices voor Skills

**DO ✅**
- Verzamel eerst goede voorbeelden
- Documenteer alle patronen in een CLAUDE.md bestand
- Test de skill 5-10x om non-determinisme te vangen
- Gebruik expliciete "NEVER" en "ALWAYS" statements
- Voeg validation checklists toe
- Laat de skill naar CLAUDE.md verwijzen voor details

**DON'T ❌**
- Probeer NIET alles in de skill te stoppen (verwijs naar docs)
- Test NIET slechts 1x (Claude is non-deterministisch!)
- Vergeet NIET edge cases (wat als user geen datum geeft?)
- Maak GEEN skills voor één-keer taken

### Testing een Skill

```bash
# Test de skill meerdere keren
/slidev-npuls "Maak presentatie over AI in education"
# Check output...

# Test opnieuw (andere output?)
/slidev-npuls "Maak presentatie over AI in education"
# Check output...

# Test met edge case
/slidev-npuls "Maak presentatie" # Geen titel?
# Hoe reageert de skill?
```

### Skill Maintenance

Skills moeten onderhouden worden:
- Update wanneer conventies veranderen
- Voeg nieuwe features toe (bijv. nieuwe background slides)
- Fix bugs die je tegenkomt in productie
- Versie beheer via git

**Voorbeeld:** Toen we ontdekten dat Slide6.PNG vervangen moest worden door Slide6/13/14/15, moesten we:
1. CLAUDE.md updaten
2. Skill updaten
3. Bestaande presentaties updaten

---

## Troubleshooting

### Probleem: Donkere overlay over backgrounds

**Oorzaak**: Slidev's `background:` property voegt automatisch overlays toe.

**Oplossing**: Gebruik de `<img>` methode zoals gedocumenteerd in "Slide Backgrounds" sectie.

### Probleem: Backgrounds niet zichtbaar

**Check:**
1. Is het img element aanwezig op de slide?
2. Is `z-index: -1` ingesteld?
3. Is het pad naar de image correct?
4. Bestaat het bestand in `public/npuls/powerpoint_slides/`?

### Probleem: Presentation-specific images niet zichtbaar

**Check:**
1. Bestaat de folder `public/presentations/YYMMDD_naam/`?
2. Staat de image in die folder?
3. Klopt het pad in je markdown? `/presentations/YYMMDD_naam/image.jpg`

### Probleem: CSS werkt niet

**Check:**
1. Is de `<style>` block aanwezig in je presentatie bestand?
2. Staan er conflicterende inline styles?
3. Is de dev server opnieuw gestart na CSS wijzigingen?

### Probleem: Tekst overlapped met logo

Het Npuls logo (rechtsonder) heeft een `::after` pseudo-element. Als tekst overlapped:
- Voeg padding toe aan de slide
- Gebruik `class` om positionering aan te passen
- Of pas de logo grootte aan in CSS

---

## Best Practices

### DO ✅

- Gebruik Npuls kleuren consequent
- Houd slides simpel en overzichtelijk
- Test op een beamer/projector voor leesbaarheid
- Gebruik de naming convention: `YYMMDD_naam.md`
- Plaats presentation-specific assets in eigen folder
- Volg de gedocumenteerde background methode
- Splits te volle slides in meerdere slides
- Gebruik shared Npuls assets waar mogelijk

### DON'T ❌

- Gebruik NIET Slidev's `background:` property
- Gebruik NIET `layout: cover` voor backgrounds
- Voeg GEEN extra themes toe
- Verwijder NIET de overlay-removal CSS
- Maak slides NIET te vol met tekst
- Gebruik GEEN andere kleuren dan Npuls palette
- Plaats GEEN shared assets in presentation-specific folders
- Dupliceer GEEN Npuls assets

---

## Validation Checklist

Voordat je een presentatie als "klaar" beschouwt, controleer het volgende:

### Bestandsnamen & Structuur
- ✅ Filename volgt `YYMMDD_name.md` conventie
- ✅ Title slide aanwezig
- ✅ Closing slide aanwezig (Slide17.PNG zonder tekst)

### CSS & Styling
- ✅ Complete CSS block met custom fonts (@font-face declarations)
- ✅ Overlay removal CSS aanwezig (CRITICAL!)
- ✅ Npuls kleuren consistent gebruikt (blue voor h1, orange voor h2)
- ✅ Npuls logo verschijnt op alle slides (via CSS ::after)

### Backgrounds
- ✅ Alle slides gebruiken `<img>` methode (NIET `background:` property)
- ✅ Section dividers gebruiken **alleen** Slide13/14/15.PNG (wissel af, NIET Slide6.PNG)
- ✅ Hoofdstuk slides hebben **dikke tekstopmaak** (bold styling)
- ✅ Slide2.PNG heeft tekst RECHTS (niet gecentreerd - afbeelding is links)
- ✅ Tekst overlapt NIET met figuren op section divider slides
- ✅ Slide17.PNG (closing) heeft GEEN TEKST - alleen background

### Content
- ✅ Geen enkele slide heeft meer dan 7 bullet points
- ✅ Te volle slides zijn gesplitst in meerdere slides
- ✅ Tekst is leesbaar op alle backgrounds

### Assets
- ✅ Asset paths zijn correct:
  - `/npuls/` voor Npuls branding
  - `/ceda_contributors/` voor team foto's
  - `/presentations/YYMMDD_name/` voor presentatie-specifieke assets
- ✅ Contributor foto's gebruiken shared `/ceda_contributors/` folder

### Testen
- ✅ Presentatie bekeken in slidev development mode
- ✅ Getest op beamer/projector als mogelijk
- ✅ Alle backgrounds tonen correct (geen overlays!)
- ✅ Logo zichtbaar op alle slides

---

## Referentie Materialen

Alle Npuls branding documenten zijn beschikbaar in `public/npuls/`:

- **Huisstijlgids**: `public/npuls/Npuls_huisstijlgids_2025.pdf`
- **PowerPoint Template**: `public/npuls/Npuls_powerpoint-template.potx`
- **Fonts**: `public/npuls/Npuls_lettertype/`

Raadpleeg deze voor:
- Kleurgebruik
- Typografie regels
- Logo placement
- Design guidelines

---

## Voorbeeld Presentatie

Bekijk `2603_1CHO_update_Avans_Windesheim.md` voor een volledig voorbeeld van:
- Correcte frontmatter setup
- Background image implementatie
- CSS styling met Npuls kleuren
- Overlay removal
- Two-column layouts
- Presenter cards
- Asset path structuur

---

**Laatste update**: 2 maart 2026
**Versie**: 2.0
**Maintainer**: CEDA Team
