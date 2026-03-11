# CEDA Slidev Presentaties

Presentatie repository voor CEDA (Centre for Educational Data Analytics) met **Npuls huisstijl**.

## 📋 Inhoudsopgave

- [Over dit project](#over-dit-project)
- [Slidev Installatie](#slidev-installatie)
- [Project Structuur](#project-structuur)
- [Nieuwe Presentatie Maken](#nieuwe-presentatie-maken)
- [Presentatie Uitvoeren](#presentatie-uitvoeren)
- [Exporteren](#exporteren)
- [Werken met Claude](#werken-met-claude)
- [Npuls Huisstijl](#npuls-huisstijl)
- [Documentatie](#documentatie)

---

## 🎯 Over dit project

Dit project bevat meerdere Slidev presentaties die de Npuls huisstijl volgen. Alle presentaties delen dezelfde branding assets maar hebben hun eigen specifieke content en afbeeldingen.

**Naming Convention**: `YYMMDD_presentatie_naam.md`
- Voorbeeld: `260310_slidev_claude.md`

---

## ⚡ Quick Start

```bash
# 1. Clone repository
git clone https://github.com/cedanl/slidev-presentaties.git
cd slidev-presentaties

# 2. Installeer Slidev
npm install -g @slidev/cli

# 3. Start een presentatie
slidev 260310_slidev_claude.md --open

# 4. Maak presentatie met Claude Code
claude
> "Maak een presentatie over [onderwerp] volgens CEDA Npuls huisstijl"
```

### 📌 Belangrijkste Commando's

| Commando | Beschrijving |
|----------|--------------|
| `slidev presentatie.md --open` | Start presentatie met hot reload |
| `slidev export presentatie.md` | Export naar PDF |
| `slidev export presentatie.md --format pptx` | Export naar PowerPoint |
| Druk `P` tijdens presentatie | Presenter mode met notes |

---

## 🚀 Snel Aan De Slag

### Stap 1: Clone de Repository

```bash
git clone https://github.com/cedanl/slidev-presentaties.git
cd slidev-presentaties
```

### Stap 2: Installeer Slidev

**Optie A: Global Installatie (Aanbevolen) ⭐**

```bash
npm install -g @slidev/cli
```

✅ Eén keer installeren, overal gebruiken

**Optie B: NPX (Geen installatie nodig)**

```bash
npx @slidev/cli --version
```

✅ Geen installatie, altijd laatste versie

### Stap 3: Start een Presentatie

```bash
# Met global installatie:
slidev 260310_slidev_claude.md --open

# Met npx:
npx @slidev/cli 260310_slidev_claude.md --open
```

Browser opent automatisch op `http://localhost:3030` 🎉

---

## 📝 Slidev Gebruiken

### Markdown Basis

Slidev presentaties worden geschreven in **Markdown**:

```markdown
# H1 Titel (grootste - oranje)
## H2 Ondertitel (oranje)
### H3 Sectie titel (zwart)

- Bullet point
- Nog een bullet

**Bold text** en *italic text*
```

### Slides Scheiden

Elke slide eindigt met drie streepjes:

```markdown
# Slide 1

Content hier...

---

# Slide 2

Content hier...
```

### Backgrounds Toevoegen

**❌ NIET zo** (voegt overlay toe):
```yaml
---
background: /npuls/powerpoint_slides/Slide1.PNG
---
```

**✅ WEL zo** (originele kleuren behouden):
```markdown
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG"
       style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Jouw Slide Titel
```

**Beschikbare backgrounds:**
- `Slide1.PNG` - Titelslide
- `Slide3.PNG` - Standaard content
- `Slide13.PNG`, `Slide14.PNG`, `Slide15.PNG` - Hoofdstuk dividers
- `Slide17.PNG` - Afsluiting (geen tekst)

### Eigen Afbeeldingen Toevoegen

#### Optie 1: Laat Claude het doen ⭐ (Aanbevolen)

```
"Voeg deze afbeelding toe aan mijn presentatie:
~/Downloads/team_foto.jpg

Plaats hem op de 'Over Ons' slide met rounded corners en shadow"
```

**Claude doet automatisch:**
1. ✅ Maakt `public/presentations/YYMMDD_naam/` folder aan
2. ✅ Kopieert de afbeelding naar de juiste locatie
3. ✅ Voegt `<img>` tag toe aan de slide
4. ✅ Past Tailwind styling toe (rounded, shadow, height)
5. ✅ Gebruikt correct pad: `/presentations/YYMMDD_naam/afbeelding.jpg`

#### Optie 2: Handmatig

**Stap 1: Maak folder**
```bash
mkdir -p public/presentations/260310_jouw_presentatie
```

**Stap 2: Kopieer images**
```bash
cp je_foto.jpg public/presentations/260310_jouw_presentatie/
```

**Stap 3: Gebruik in presentatie**
```markdown
<img src="/presentations/260310_jouw_presentatie/je_foto.jpg"
     alt="Beschrijving"
     class="h-56 rounded-lg shadow-lg" />
```

### Hot Reload

Wijzigingen worden **automatisch** zichtbaar - geen refresh nodig! 🔥

---

## 📁 Project Structuur

```
slidev-presentaties/
├── 2603_1CHO_update_Avans_Windesheim.md  ← Presentaties (YYMMDD_naam.md)
├── CLAUDE.md                              ← Uitgebreide documentatie
├── README.md                              ← Dit bestand
├── .gitignore
├── components/                            ← Custom Vue components
├── snippets/                              ← Herbruikbare code snippets
└── public/                                ← ALLE statische assets
    ├── npuls/                            ← SHARED Npuls branding
    │   ├── powerpoint_slides/            ← Slide backgrounds
    │   ├── npuls_images/                 ← Template assets
    │   ├── npuls_logo.jpg
    │   ├── Npuls_huisstijlgids_2025.pdf
    │   └── Npuls_lettertype/
    └── presentations/                    ← Per-presentatie assets
        └── YYMMDD_naam/
            └── [specifieke images].jpg
```

---

## ✨ Nieuwe Presentatie Maken

### Optie 1: Met Claude Code ⭐ (Aanbevolen)

```bash
# Open Claude Code in je project
claude
```

**Vraag Claude:**
```
Maak een nieuwe Slidev presentatie over [onderwerp]
voor [doelgroep].

Onderwerpen:
- [Punt 1]
- [Punt 2]
- [Punt 3]

Gebruik de CEDA Npuls huisstijl.
Presentatie datum: [datum]
Duur: ongeveer [X] minuten
```

**Claude doet automatisch:**
- ✅ Maakt presentatie bestand aan (`YYMMDD_onderwerp.md`)
- ✅ Creëert asset folder (`public/presentations/YYMMDD_onderwerp/`)
- ✅ Voegt Npuls styling toe (kleuren, fonts, CSS)
- ✅ Kiest juiste backgrounds (Slide1, Slide3, etc.)
- ✅ Voegt illustraties toe uit de bibliotheek
- ✅ Schrijft presenter notes
- ✅ Volgt alle CLAUDE.md richtlijnen

**Tijdsbesparing: 5 minuten vs 2 uur handmatig werk!**

---

### Optie 2: Handmatig

#### Stap 1: Creëer presentatie bestand

```bash
touch 0304_mijn_presentatie.md
```

#### Stap 2: Creëer asset folder

```bash
mkdir -p public/presentations/0304_mijn_presentatie
```

#### Stap 3: Voeg images toe

```bash
# Kopieer je specifieke afbeeldingen
cp ~/Downloads/grafiek.png public/presentations/0304_mijn_presentatie/
```

#### Stap 4: Start met template

Kopieer de structuur van een bestaande presentatie of begin met:

```markdown
---
class: text-center
title: Mijn Presentatie Titel
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide1.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap');

  :root {
    --npuls-orange: #DD784B;
    --npuls-blue: #3D68EC;
  }

  :deep(h1) {
    color: #DD784B !important;
    font-weight: 700;
  }
  :deep(h2) {
    color: #DD784B !important;
    font-weight: 600;
  }

  /* Subtitle op title slide - Oranje maar NIET bold */
  .title-subtitle {
    color: #DD784B !important;
    font-weight: 400 !important;
  }
</style>

# Mijn Presentatie Titel

## Ondertitel

---

# Volgende Slide

Content hier...
```

---

## ▶️ Presentatie Uitvoeren

### Development Mode (met hot-reload)

```bash
slidev 2603_1CHO_update_Avans_Windesheim.md --open
```

**Automatisch opent:**
- 🌐 Browser op `http://localhost:3030`
- 🔄 Hot-reload bij wijzigingen

### Presenter Mode

Druk op `P` tijdens presentatie of navigeer naar:
```
http://localhost:3030/presenter
```

**Features:**
- 📝 Speaker notes zichtbaar
- ⏭️ Volgende slide preview
- ⏱️ Timer

### Keyboard Shortcuts

| Toets | Actie |
|-------|-------|
| `Space` / `→` | Volgende slide |
| `Shift+Space` / `←` | Vorige slide |
| `F` | Fullscreen |
| `P` | Presenter mode |
| `D` | Dark mode toggle |
| `G` | Ga naar slide (type nummer) |
| `O` | Overview mode |

---

## 📤 Exporteren

### Export naar PDF

```bash
slidev export 2603_1CHO_update_Avans_Windesheim.md
```

Output: `2603_1CHO_update_Avans_Windesheim.pdf`

### Export naar PowerPoint

```bash
slidev export 2603_1CHO_update_Avans_Windesheim.md --format pptx
```

Output: `2603_1CHO_update_Avans_Windesheim.pptx`

### Export naar PNG (per slide)

```bash
slidev export 2603_1CHO_update_Avans_Windesheim.md --format png
```

### Export met custom range

```bash
# Alleen slides 1-10
slidev export presentatie.md --range 1-10
```

---

## 🤖 Werken met Claude Code

### Hele Presentaties Maken met Claude

Claude kan **complete presentaties** genereren met de juiste Npuls huisstijl. Tijdsbesparing: **5 minuten vs 2 uur** handmatig werk.

### Claude Code Workflow

#### 1. Open Project in Claude Code

```bash
cd slidev-presentaties
claude
```

#### 2. Vraag om een Presentatie

**Voorbeeld prompt:**
```
Maak een Slidev presentatie over Data Visualisatie
voor een technische doelgroep.

Onderwerpen:
- Waarom visualisatie belangrijk is
- Populaire tools (Python, R, Tableau)
- Best practices
- Voorbeelden

Gebruik de CEDA Npuls huisstijl.
Presentatie datum: 15 maart 2026
Duur: ongeveer 20 minuten
```

#### 3. Claude Leest Automatisch CLAUDE.md

Claude gebruikt alle richtlijnen uit `CLAUDE.md`:
- ✅ Npuls kleuren en fonts
- ✅ Juiste backgrounds (Slide1.PNG voor titel, etc.)
- ✅ Illustraties uit de bibliotheek
- ✅ Correcte styling en CSS
- ✅ Presenter notes

#### 4. Review & Itereer

Claude kan alles aanpassen:

```
"Voeg een slide toe over interactieve visualisaties"

"Maak de intro korter - max 2 minuten"

"Voeg presenter notes toe aan alle slides"

"Verander de volgorde: begin met voorbeelden"

"Gebruik meer code voorbeelden voor Python"
```

#### 5. Start Presentatie

```bash
slidev YYMMDD_jouw_presentatie.md --open
```

### Wat Claude Automatisch Doet

- ✅ **Correcte bestandsnaam**: `YYMMDD_onderwerp.md` format
- ✅ **Npuls styling**: Oranje titels, juiste fonts, kleuren
- ✅ **Backgrounds**: Slide1 voor titel, Slide3 voor content, Slide17 voor afsluiting
- ✅ **Illustraties**: Kiest passende SVG icons uit de bibliotheek
- ✅ **Asset folders**: Maakt `public/presentations/YYMMDD_naam/` aan
- ✅ **Presenter notes**: Timing, key points, scripts
- ✅ **Consistentie**: Volgt altijd CLAUDE.md richtlijnen

### Tips voor Beste Resultaten

**✅ Geef duidelijke context:**
- Onderwerp en doelgroep
- Belangrijkste punten
- Gewenste duur
- Presentatie datum

**✅ Specificeer niveau:**
```
"Maak een technische presentatie voor developers"
"Maak een toegankelijke presentatie voor management"
```

**✅ Vraag om specifieke elementen:**
```
"Voeg code voorbeelden toe"
"Gebruik twee-kolom layouts waar mogelijk"
"Voeg een demo slide toe"
```

**✅ Itereer stapsgewijs:**
- Eerst basis structuur
- Daarna content verfijnen
- Als laatste presenter notes toevoegen

### Claude Code Skills

Het project kan **Claude Code Skills** bevatten in `.claude/skills/`. Deze skills helpen bij:
- ✅ Automatisch presentaties genereren
- ✅ Consistente styling toepassen
- ✅ Asset management

Vraag Claude om een skill te maken als je repetitieve taken hebt.

---

## 🎨 Npuls Huisstijl

### Kleuren

```css
/* Primair */
--npuls-orange: #DD784B    /* H1 en H2 titels */
--npuls-blue: #3D68EC      /* Accenten en links */
--npuls-black: #000000     /* Tekst */
--npuls-white: #FFFFFF     /* Achtergrond */

/* Secundair */
--npuls-green: #00AF81     /* Accent */
--npuls-yellow: #F4D74B    /* Accent */
--npuls-pink: #F4D9DC      /* Accent */
```

**Styling:**
- H1: Oranje (#DD784B), bold (700)
- H2: Oranje (#DD784B), semi-bold (600)
- Subtitle op titelslide: Oranje, **niet** bold (400)

### Fonts

- **Primair**: Poppins (via Google Fonts)
- **Weights**: 400 (regular), 500 (medium), 600 (semi-bold), 700 (bold)

### Assets Locaties

```markdown
<!-- Slide backgrounds -->
/npuls/powerpoint_slides/Slide1.PNG    (titelslide)
/npuls/powerpoint_slides/Slide2.PNG    (inhoudsopgave)
/npuls/powerpoint_slides/Slide16.PNG   (section break)

<!-- Logo -->
/npuls/npuls_logo.jpg

<!-- Template images (101 stuks) -->
/npuls/npuls_images/image1.png
/npuls/npuls_images/image42.svg

<!-- Presentatie-specifieke images -->
/presentations/YYMMDD_naam/foto.jpg
```

### Background Implementatie

**❌ NIET zo:**
```yaml
---
background: /npuls/powerpoint_slides/Slide1.PNG
---
```

**✅ WEL zo:**
```html
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide1.PNG"
       style="width: 100%; height: 100%; object-fit: cover;" />
</div>
```

**Reden:** Slidev voegt automatisch een overlay toe bij `background:` property.

---

## 📚 Documentatie

### Uitgebreide Docs

Zie **[CLAUDE.md](./CLAUDE.md)** voor:
- Volledige CSS styling voorbeelden
- Slide structuur templates
- Troubleshooting
- Best practices
- Content richtlijnen

### Externe Links

- 📖 [Slidev Documentatie](https://sli.dev/)
- 🎨 [Npuls Huisstijlgids](./public/npuls/Npuls_huisstijlgids_2025.pdf)
- 💻 [Slidev GitHub](https://github.com/slidevjs/slidev)

---

## 🤝 Contributing

### Voor nieuwe presentaties:

1. Branch maken: `git checkout -b 0304-nieuwe-presentatie`
2. Presentatie maken volgens structuur hierboven
3. Assets toevoegen aan `public/presentations/0304_nieuwe_presentatie/`
4. Testen: `slidev 0304_nieuwe_presentatie.md --open`
5. Commit en push
6. Pull request maken

### Naming Conventions

- **Presentaties**: `YYMMDD_beschrijvende_naam.md`
- **Asset folders**: `public/presentations/YYMMDD_beschrijvende_naam/`
- **Branches**: `YYMMDD-beschrijvende-naam`

---

## 📞 Support

**CEDA Team**
- Voor vragen over presentaties: Tomer Iwan & Aslam Tanjung
- Voor technische issues: Zie CLAUDE.md troubleshooting sectie
- Voor Npuls branding: Raadpleeg huisstijlgids in `public/npuls/`

---

## 📄 Licentie

Npuls branding assets zijn eigendom van Npuls. Gebruik alleen binnen CEDA context.

---

**Happy presenting! 🎉**
