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
- Voorbeeld: `2603_1CHO_update_Avans_Windesheim.md`

---

## 🚀 Slidev Installatie

Je hebt **3 opties** om Slidev te gebruiken:

### Optie 1: Global Installatie (Aanbevolen) ⭐

```bash
npm install -g @slidev/cli
```

**Voordelen:**
- ✅ Eén keer installeren, overal gebruiken
- ✅ Geen `node_modules/` of `package.json` per project
- ✅ Meest lightweight

**Gebruik:**
```bash
slidev presentatie.md --open
```

### Optie 2: NPX (Geen installatie)

```bash
npx @slidev/cli presentatie.md --open
```

**Voordelen:**
- ✅ Geen installatie nodig
- ✅ Gebruikt altijd de laatste versie

**Nadelen:**
- ❌ Download bij elke run (trager)

### Optie 3: Lokale Project Installatie

```bash
npm init -y
npm install @slidev/cli
```

**Voordelen:**
- ✅ Vaste versie per project
- ✅ Team gebruikt zelfde versie

**Nadelen:**
- ❌ `node_modules/` folder per project
- ❌ Meer disk space

**Gebruik:**
```bash
npx slidev presentatie.md --open
# Of in package.json scripts
```

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

### Stap 1: Creëer presentatie bestand

```bash
touch 0304_mijn_presentatie.md
```

### Stap 2: Creëer asset folder

```bash
mkdir -p public/presentations/0304_mijn_presentatie
```

### Stap 3: Voeg images toe

```bash
# Kopieer je specifieke afbeeldingen
cp ~/Downloads/grafiek.png public/presentations/0304_mijn_presentatie/
```

### Stap 4: Start met template

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
    --npuls-blue: #3D68EC;
    --npuls-orange: #DD784B;
  }

  :deep(h1) { color: #3D68EC !important; }
  :deep(h2) { color: #DD784B !important; }
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

## 🤖 Werken met Claude

### Claude Code voor Presentaties

**Claude kan helpen met:**
- ✅ Nieuwe slides schrijven
- ✅ Content structureren
- ✅ Npuls kleuren toepassen
- ✅ Layouts maken (two-column, grids)
- ✅ CSS styling fixes
- ✅ Images toevoegen en positioneren

### Best Practices met Claude

**1. Refereer naar CLAUDE.md:**
```
"Maak een nieuwe slide volgens de structuur in CLAUDE.md"
```

**2. Specificeer Npuls huisstijl:**
```
"Gebruik Npuls blue (#3D68EC) voor de titel"
```

**3. Geef context over assets:**
```
"Voeg de afbeelding toe uit /presentations/2603_1CHO_update_Avans_Windesheim/grafiek.png"
```

**4. Vraag om specifieke layouts:**
```
"Maak een two-column layout met links tekst en rechts een afbeelding"
```

### Claude Commando's

```bash
# Claude kan deze commands voor je uitvoeren:
slidev 2603_1CHO_update_Avans_Windesheim.md --open

# Of nieuwe presentaties maken:
mkdir -p public/presentations/0304_nieuwe_presentatie
touch 0304_nieuwe_presentatie.md
```

### Voorbeeld Prompts

**Nieuwe slide toevoegen:**
```
"Voeg een slide toe met titel 'Resultaten Q1' en een bullet list met 3 punten"
```

**Layout aanpassen:**
```
"Verander deze slide naar een two-column layout met links de tekst
en rechts het logo"
```

**Npuls background toevoegen:**
```
"Voeg Slide16.PNG als background toe aan deze section break slide"
```

**CSS fixes:**
```
"De titel is niet zichtbaar op de blauwe achtergrond, fix de text-shadow"
```

---

## 🎨 Npuls Huisstijl

### Kleuren

```css
/* Primair */
--npuls-blue: #3D68EC      /* Titels */
--npuls-orange: #DD784B    /* Subtitels */
--npuls-black: #000000     /* Tekst */
--npuls-white: #FFFFFF     /* Achtergrond */

/* Secundair */
--npuls-green: #00AF81     /* Accent */
--npuls-yellow: #F4D74B    /* Accent */
--npuls-pink: #F4D9DC      /* Accent */
```

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
