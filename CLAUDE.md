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
    │   ├── npuls_images/        ← 101 template assets (image1.png - image101.png)
    │   ├── npuls_logo.jpg       ← Npuls logo
    │   ├── Npuls_powerpoint-template.potx
    │   ├── Npuls_huisstijlgids_2025.pdf
    │   └── Npuls_lettertype/    ← Font files
    └── presentations/           ← PRESENTATION-SPECIFIC assets
        ├── 2603_1CHO_update_Avans_Windesheim/
        │   ├── tomer_iwan.jpg
        │   └── aslam_tanjung.jpg
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
- **Primair**: Poppins (via Google Fonts)
- **Secundair**: Cooper Light (voor quotes/introducties)
- **Fallback**: Arial, Helvetica

**Font Weights:**
- Regular (400): Body text
- Medium (500): Subheadings
- Semi-Bold (600): H2, H3
- Bold (700): H1

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
| `Slide2.PNG` | Inhoudsopgave / Over Ons |
| `Slide3.PNG` | Standaard content slide |
| `Slide6.PNG` | Hoofdstuk slide |
| `Slide10.PNG` | Alternatieve content slide |
| `Slide16.PNG` | Section break |
| `Slide17.PNG` | Afsluiting slide |
| `Slide18.PNG` | Grote afbeelding slide |
| `Slide19.PNG` | Quote slide |

*Andere slides (4-5, 7-9, 11-15) zijn ook beschikbaar voor variatie.*

---

## Asset Paths

### Shared Npuls Assets

Deze zijn beschikbaar voor ALLE presentaties:

```markdown
<!-- Background slides -->
<img src="/npuls/powerpoint_slides/Slide1.PNG" />

<!-- Logo -->
background-image: url('/npuls/npuls_logo.jpg');

<!-- Template images (101 stuks) -->
<img src="/npuls/npuls_images/image1.png" />
<img src="/npuls/npuls_images/image42.svg" />
```

### Presentation-Specific Assets

Voor presentatie `YYMMDD_naam.md`, plaats images in `public/presentations/YYMMDD_naam/`:

```markdown
<!-- Voorbeeld voor presentatie 2603_1CHO_update_Avans_Windesheim.md -->
<img src="/presentations/2603_1CHO_update_Avans_Windesheim/tomer_iwan.jpg" />
<img src="/presentations/2603_1CHO_update_Avans_Windesheim/screenshot.png" />
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

## CSS Styling

Custom styling plaats je in een `<style>` block aan het begin van je presentatie bestand.

### Npuls Kleuren Toepassen

```css
<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap');

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
    <img src="/presentations/YOUR_PRESENTATION/presenter1.jpg"
         alt="Presenter 1"
         class="h-56 rounded-lg mx-auto shadow-lg">
    <h3 class="mt-4 text-xl font-bold">Naam Presenter</h3>
    <p class="mt-2 text-base font-semibold">Functie @ CEDA</p>
    <p class="mt-3 text-sm leading-relaxed">Korte beschrijving</p>
  </div>
  <div class="text-center">
    <!-- Tweede presenter -->
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
