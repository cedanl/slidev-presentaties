---
class: text-center
title: Slidev Presentaties Maken met Claude
info: |
  ## Slidev Presentaties Maken met Claude
  Snel professionele presentaties maken met AI
drawings:
  persist: false
transition: slide-left
mdc: true
duration: 30min
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide1.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap');

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

  :deep(.slide) {
    position: relative;
    font-family: 'General Sans', Arial, Helvetica, sans-serif;
    color: #000000;
    background-color: transparent !important;
  }

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
    opacity: 1.0;
  }

  :deep(h1) {
    color: #DD784B !important;
    font-weight: 700;
    font-size: 3rem;
  }

  :deep(h2) {
    color: #DD784B !important;
    font-weight: 600;
    font-size: 2rem;
  }

  :deep(h3), :deep(h4), :deep(h5), :deep(h6) {
    color: #000000 !important;
    font-weight: 600;
  }

  /* Subtitle op title slide - Oranje maar NIET bold */
  .title-subtitle {
    color: #DD784B !important;
    font-weight: 400 !important;
  }

  .title-subtitle strong {
    font-weight: 400 !important;
  }

  :deep(strong) {
    color: #3D68EC;
    font-weight: 700;
  }

  :deep(code) {
    background-color: #f5f5f5;
    padding: 0.2rem 0.4rem;
    border-radius: 0.25rem;
    font-size: 0.9em;
    color: #DD784B;
  }

  :deep(pre) {
    background-color: #f5f5f5 !important;
    padding: 1rem !important;
    border-radius: 0.5rem;
  }

  /* Force alle illustraties volledig zichtbaar */
  img[src*="powerpoint_illustrations"] {
    opacity: 1 !important;
  }
</style>

# Slidev Presentaties

## Snel professionele slides maken met Claude

<div class="mt-8 text-xl title-subtitle">
<strong>CEDA</strong> - Centre for Educational Data Analytics
</div>

<!--
⏱️ Timing: 1 minuut

📌 Key points:
- Verwelkom iedereen
- Korte intro over Slidev en Claude
- Presentatie duurt ongeveer 15 minuten

💡 Opening:
"Welkom! Vandaag laat ik zien hoe we bij CEDA in een paar minuten professionele presentaties maken met Slidev en Claude."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Presentatie door

<div style="max-width: 400px; margin: 2rem auto;">
  <div class="text-center">
    <img src="/ceda_contributors/aslam_tanjung.jpg"
         alt="Aslam Tanjung"
         class="h-56 rounded-lg mx-auto shadow-lg">
    <h3 class="mt-4 text-xl font-bold">Aslam Tanjung</h3>
    <p class="mt-2 text-base font-semibold">Data Scientist @ CEDA</p>
  </div>
</div>

<!--
⏱️ Timing: 30 seconden

📌 Key points:
- Korte persoonlijke intro
- Rol bij CEDA

💡 Script:
"Mijn naam is Aslam Tanjung, ik ben Data Scientist bij CEDA."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide2.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="margin-left: 50%; padding-left: 2rem;">

# Wat is Slidev?

<div class="mt-8">

- Presentaties maken met **Markdown**
- Developer-vriendelijk
- Code highlighting out-of-the-box
- Exporteer naar PDF of PowerPoint
- Hot reload tijdens bewerken

</div>

</div>

<img src="/npuls/powerpoint_illustrations/present.svg"
     style="position: absolute; bottom: 8rem; left: 2rem; width: 160px; height: auto; opacity: 1.0;" />

<!--
⏱️ Timing: 1-2 minuten

📌 Key points:
- Slidev = presentaties in Markdown
- Voor developers super natuurlijk
- Code blocks worden automatisch mooi
- Export naar PDF en PowerPoint mogelijk
- Hot reload: wijzigingen direct zichtbaar

💡 Extra context:
"Slidev is een framework waarmee je presentaties schrijft in Markdown. Voor developers is dat heel natuurlijk - je schrijft je presentatie zoals je documentatie schrijft."

🎯 Interactie:
"Wie gebruikt hier regelmatig Markdown?" [wacht op response]

🔄 Transitie:
"Laten we kijken hoe je aan de slag gaat..."
-->

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide13.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="font-weight: 700; font-size: 3.5rem;">

# Setup

</div>

<div style="font-weight: 600; font-size: 2rem; margin-top: 1rem;">

## In 3 stappen aan de slag

</div>

<!--
⏱️ Timing: 15 seconden

📌 Key points:
- Setup is super simpel
- Slechts 3 stappen nodig

💡 Script:
"De setup is verrassend simpel - slechts 3 stappen."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Stap 1: Clone de Repository

```bash
# Clone het project
git clone https://github.com/cedanl/slidev-presentaties.git
cd slidev-presentaties
```

<img src="/npuls/powerpoint_illustrations/laptop.svg"
     style="position: absolute; bottom: 2rem; right: 2rem; width: 140px; height: auto; opacity: 1.0;" />

<!--
⏱️ Timing: 1 minuut

📌 Key points:
- Stap 1 is simpel: git clone
- Repository bevat alle Npuls branding assets
- Eenmalige setup

💡 Extra context:
"Eerste stap: clone de repository. Deze bevat alle Npuls branding, fonts en assets die je nodig hebt."

🔄 Transitie:
"Nu we de repository hebben, installeren we Slidev..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Stap 2: Installeer Slidev

```bash
# Installeer Slidev globally
npm install -g @slidev/cli

# Of gebruik npx (geen installatie nodig)
npx slidev --version
```

<!--
⏱️ Timing: 1 minuut

📌 Key points:
- Twee opties: global install of npx
- npx = geen installatie nodig
- Global install = handiger bij regelmatig gebruik

💡 Extra context:
"Twee opties: installeer Slidev globally met npm, of gebruik npx. Met npx hoef je niks te installeren - handig voor eenmalige gebruik."

🔄 Transitie:
"En dan de laatste stap: je presentatie starten..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Stap 3: Start een Presentatie

```bash
# Start development server
slidev YYMMDD_presentation_name.md --open

# Bijvoorbeeld:
slidev 260310_slidev_claude.md --open

# Browser opent automatisch op localhost:3030
```

<img src="/npuls/powerpoint_illustrations/Vaantje geel met vink.svg"
     style="position: absolute; bottom: 2rem; right: 2rem; width: 120px; height: auto; opacity: 1.0;" />

<!--
⏱️ Timing: 1 minuut

📌 Key points:
- Simpel commando: slidev [filename] --open
- Browser opent automatisch
- Localhost:3030
- Hot reload: wijzigingen direct zichtbaar

💡 Extra context:
"Laatste stap: draai het commando 'slidev' met je bestandsnaam. Browser opent automatisch. Elke wijziging die je maakt in het Markdown bestand zie je direct terug - geen refresh nodig."

🎯 Demo suggestie:
"Als tijd: laat kort zien hoe hot reload werkt"

🔄 Transitie:
"Voordat we naar de voordelen gaan, laten we eerst kijken naar de repository structuur..."
-->

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide15.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="font-weight: 700; font-size: 3.5rem;">

# Repository Structuur

</div>

<div style="font-weight: 600; font-size: 2rem; margin-top: 1rem;">

## Hoe zit het project in elkaar?

</div>

<!--
⏱️ Timing: 15 seconden

📌 Key points:
- Begrijp de repository structuur
- Waar vind je wat

💡 Script:
"Laten we eerst kijken hoe de repository is gestructureerd..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Project Structuur

<div class="mt-4 text-sm">

```
slidev-presentaties/
├── YYMMDD_presentation_name.md  ← Je presentatie bestanden
├── CLAUDE.md                    ← Documentatie & richtlijnen
├── README.md
└── public/                      ← ALLE assets hier
    ├── npuls/                  ← Gedeelde Npuls assets
    │   ├── powerpoint_slides/  ← Backgrounds (19 stuks)
    │   ├── powerpoint_illustrations/ ← 70+ SVG icons
    │   ├── npuls_logo.jpg
    │   └── Npuls_lettertype/   ← Fonts
    ├── ceda_contributors/      ← Team foto's
    └── presentations/          ← Jouw specifieke images
        └── YYMMDD_naam/
```

</div>

<img src="/npuls/powerpoint_illustrations/Document.svg"
     style="position: absolute; bottom: 2rem; right: 2rem; width: 120px; height: auto; opacity: 1.0;" />

<!--
⏱️ Timing: 2 minuten

📌 Key points:
- Presentaties in root: YYMMDD_naam.md format
- CLAUDE.md = alle documentatie
- public/ = alle assets
- npuls/ = gedeelde branding (19 backgrounds, 70+ illustraties)
- presentations/ = jouw specifieke images per presentatie

💡 Extra context:
"De structuur is simpel. Je presentatie bestanden staan in de root met datum prefix. Alle assets in public folder."

"In npuls folder vind je gedeelde assets: 19 background slides, 70+ illustraties, logo en fonts. Deze deel je met iedereen."

"Voor presentatie-specifieke images: maak een folder in presentations/ met je presentatie naam."

🔄 Transitie:
"Laten we kijken hoe je Slidev gebruikt..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Slidev Gebruiken

<div class="mt-6">

### Schrijven in Markdown

```markdown
# Slide Titel

- Bullet point 1
- Bullet point 2

**Bold text** en *italic text*
```

### Slides Scheiden

```markdown
---
```

Een slide eindigt met `---` en de volgende begint.

</div>

<!--
⏱️ Timing: 2 minuten

📌 Key points:
- Markdown syntax: # voor titels, - voor bullets
- Slides scheiden met ---
- Bold met **, italic met *

💡 Extra context:
"Je schrijft in pure Markdown. Hashtag voor titels, streepjes voor bullets, sterretjes voor bold."

"Elke slide eindig je met drie streepjes. Dan begint de volgende slide."

🔄 Transitie:
"Hoe voeg je backgrounds toe?"
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide2.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="margin-left: 50%; padding-left: 2rem;">

# Backgrounds Toevoegen

<div class="mt-8">

```markdown
---
---

<div style="position: absolute;
     top: 0; left: 0;
     width: 100%; height: 100%;
     z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG"
       style="width: 100%; height: 100%;
              object-fit: cover;" />
</div>

# Je Slide Titel
```

**Beschikbaar**: Slide1.PNG t/m Slide19.PNG

</div>

</div>

<img src="/npuls/powerpoint_illustrations/Laptop met beeld.svg"
     style="position: absolute; bottom: 8rem; left: 2rem; width: 140px; height: auto; opacity: 1.0;" />

<!--
⏱️ Timing: 2 minuten

📌 Key points:
- NIET de background: property gebruiken (voegt overlay toe)
- WEL absolute positioned img gebruiken
- 19 backgrounds beschikbaar (Slide1 t/m Slide19)
- z-index: -1 is belangrijk!

💡 Extra context:
"Belangrijk: gebruik NIET Slidev's background property - die voegt een donkere overlay toe."

"Gebruik in plaats daarvan een absolute positioned image met z-index -1. Zo blijft de originele Npuls background volledig zichtbaar."

"Er zijn 19 backgrounds beschikbaar: Slide1 voor titel, Slide3 voor content, Slide17 voor afsluiting, etc."

🔄 Transitie:
"En hoe voeg je je eigen afbeeldingen toe?"
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Eigen Afbeeldingen Toevoegen

<div class="mt-8">

### Stap 1: Maak folder voor je presentatie

```bash
mkdir -p public/presentations/260310_jouw_presentatie
```

### Stap 2: Voeg images toe

```bash
cp je_afbeelding.jpg public/presentations/260310_jouw_presentatie/
```

### Stap 3: Gebruik in presentatie

```markdown
<img src="/presentations/260310_jouw_presentatie/je_afbeelding.jpg"
     alt="Beschrijving"
     class="h-56 rounded-lg" />
```

</div>

<!--
⏱️ Timing: 2 minuten

📌 Key points:
- Maak folder in public/presentations/ met je presentatie naam
- Kopieer images daarheen
- Gebruik pad: /presentations/YYMMDD_naam/image.jpg
- Geen ../ of absolute paths nodig

💡 Extra context:
"Voor je eigen afbeeldingen: maak een folder in public/presentations met je presentatie naam - gebruik dezelfde YYMMDD prefix."

"Kopieer je images daarheen. In je Markdown gebruik je dan gewoon /presentations/jouw-naam/image.jpg"

"Handig: je kunt Tailwind classes gebruiken voor styling, zoals h-56 voor height, rounded-lg voor afgeronde hoeken."

🎯 Tip:
"Voor team foto's gebruik je /ceda_contributors/ - die zijn gedeeld."

🔄 Transitie:
"Nu je weet hoe je Slidev gebruikt, wat zijn de voordelen?"
-->

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide14.PNG" style="width: 100%; height: 100%; z-index: -1; object-fit: cover;" />
</div>

<div style="font-weight: 700; font-size: 3.5rem;">

# Voordelen

</div>

<div style="font-weight: 600; font-size: 2rem; margin-top: 1rem;">

## Waarom Slidev?

</div>

<!--
⏱️ Timing: 10 seconden

📌 Key points:
- Voordelen voor developers én CEDA

💡 Script:
"Laten we kijken waarom Slidev zo handig is..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Waarom Slidev?

<div class="mt-8">

### Voor Developers

- ✅ **Markdown** - Schrijf zoals je documentatie schrijft
- ✅ **Git-vriendelijk** - Track changes, branches, pull requests
- ✅ **Code blocks** - Syntax highlighting voor alle talen
- ✅ **Hot reload** - Zie wijzigingen direct

</div>

<div class="mt-8">

### Voor CEDA

- ✅ **Consistente huisstijl** - Npuls branding automatisch
- ✅ **Herbruikbare assets** - Illustraties en backgrounds delen
- ✅ **Snel** - Van idee naar presentatie in minuten

</div>

<!--
⏱️ Timing: 2 minuten

📌 Key points:
VOOR DEVELOPERS:
- Markdown = natuurlijke workflow
- Git = versiecontrole, samenwerken, PR reviews
- Code blocks = automatisch syntax highlighting
- Hot reload = productiviteit

VOOR CEDA:
- Npuls branding consistent
- Assets herbruikbaar
- Snelheid: van idee naar presentatie in minuten

💡 Extra context:
"Voor developers is Markdown heel natuurlijk. Je schrijft je presentatie zoals je documentatie schrijft. En omdat het plain text is, kun je git gebruiken - versiecontrole, branches, pull requests."

"Voor CEDA betekent het: consistente Npuls huisstijl, herbruikbare assets, en vooral: snelheid."

🔄 Transitie:
"En dan komt Claude in beeld..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Claude Gebruiken

<div class="mt-8">

**Claude kan je hele presentatie maken:**

1. **Geef context**: "Maak een presentatie over X"
2. **Claude genereert**: Complete Markdown met Npuls styling
3. **Review & tweak**: Pas aan waar nodig
4. **Klaar!**

</div>

<div class="mt-8">

**Voordeel:**
- Snelheid: 5 minuten vs 2 uur
- Consistentie: Volgt altijd CLAUDE.md richtlijnen
- Kwaliteit: Professioneel vanaf eerste versie

</div>

<img src="/npuls/powerpoint_illustrations/kunstmatigeintelligentie.svg"
     style="position: absolute; bottom: 2rem; right: 2rem; width: 160px; height: auto; opacity: 1.0;" />

<!--
⏱️ Timing: 2-3 minuten

📌 Key points:
- Claude kan hele presentatie genereren
- 4-stappen proces
- Enorme tijdsbesparing: 5 min vs 2 uur
- Consistentie door CLAUDE.md richtlijnen
- Direct professioneel resultaat

💡 Extra context:
"Het mooie is: Claude kan je hele presentatie maken. Je geeft context, Claude genereert complete Markdown met Npuls styling, jij past aan waar nodig, klaar."

"Resultaat: 5 minuten werk in plaats van 2 uur. En door de CLAUDE.md richtlijnen is het altijd consistent en professioneel."

🎯 Voorbeeld:
"Bijvoorbeeld deze presentatie - volledig gemaakt door Claude in een paar minuten."

🔄 Transitie:
"Laten we kijken hoe je Claude Code precies vraagt..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Hoe Claude Code Vragen?

<div class="mt-6">

### Voorbeeld Prompt

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
```

</div>

<div class="mt-6">

### Wat gebeurt er?

Claude leest **CLAUDE.md** en maakt een complete presentatie met juiste styling, backgrounds, en illustraties.

</div>

<!--
⏱️ Timing: 2 minuten

📌 Key points:
- Geef duidelijke context: onderwerp, doelgroep
- Noem belangrijkste onderwerpen
- Vraag expliciet om Npuls huisstijl
- Geef presentatie datum mee (voor bestandsnaam)

💡 Extra context:
"Je vraagt Claude simpelweg om een presentatie te maken. Geef context: onderwerp, doelgroep, belangrijkste punten."

"Claude leest automatisch CLAUDE.md en gebruikt alle richtlijnen: juiste backgrounds, fonts, kleuren, illustraties."

🎯 Tip:
"Hoe specifieker je prompt, hoe beter het resultaat."

🔄 Transitie:
"En wat als je iets wilt aanpassen?"
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Itereren met Claude

<div class="mt-8">

### Claude kan alles aanpassen

```
"Voeg een slide toe over interactieve visualisaties"

"Maak de intro korter - max 2 minuten"

"Voeg presenter notes toe aan alle slides"

"Verander de volgorde: begin met voorbeelden"

"Voeg meer code voorbeelden toe voor Python"
```

</div>

<div class="mt-8">

**Claude begrijpt context** en past de presentatie aan terwijl alle styling behouden blijft.

</div>

<!--
⏱️ Timing: 2 minuten

📌 Key points:
- Claude kan presentatie iteratief aanpassen
- Slides toevoegen/verwijderen
- Volgorde wijzigen
- Content aanpassen
- Presenter notes toevoegen
- Styling blijft consistent

💡 Extra context:
"Het mooie is: je kunt iteratief werken. Niet tevreden? Vraag Claude om aanpassingen."

"Voeg slides toe, verander volgorde, pas content aan, voeg presenter notes toe - Claude snapt de context en houdt alles consistent."

🎯 Voorbeeld:
"Voor deze presentatie: eerst basis gemaakt, toen extra slides over repository structuur toegevoegd, daarna presenter notes aan alle slides."

🔄 Transitie:
"Hoe weet Claude wat de juiste stijl is?"
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Claude Code Workflow

<div class="mt-6">

### 1. Open project in Claude Code

```bash
cd slidev-presentaties
claude
```

### 2. Vraag om presentatie

```
Maak een presentatie over [onderwerp]
volgens de CEDA Npuls huisstijl
```

### 3. Claude leest CLAUDE.md

Automatisch: alle richtlijnen, templates, kleuren, backgrounds

### 4. Review & iterate

```
"Voeg toe...", "Pas aan...", "Verwijder..."
```

### 5. Start presentatie

```bash
slidev YYMMDD_naam.md --open
```

</div>

<!--
⏱️ Timing: 2-3 minuten

📌 Key points:
- Open project in Claude Code CLI
- Vraag om presentatie met duidelijke context
- Claude leest CLAUDE.md automatisch
- Itereer tot je tevreden bent
- Start Slidev om te bekijken

💡 Extra context:
"De workflow is super simpel. Open je project in Claude Code CLI, vraag om een presentatie, Claude leest alle richtlijnen uit CLAUDE.md."

"Je kunt iteratief aanpassen tot je tevreden bent. En dan start je Slidev om het resultaat te bekijken."

🎯 Live demo suggestie:
"Als tijd: laat kort zien in Claude Code CLI"

🔄 Transitie:
"Dus wat zit er in dat CLAUDE.md bestand?"
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Pro Tip: CLAUDE.md

<div class="mt-8">

Het project heeft een **CLAUDE.md** bestand met:

- ✅ Npuls huisstijl regels
- ✅ Background slide gebruik
- ✅ Font en kleur instellingen
- ✅ Illustratie bibliotheek
- ✅ Slide templates

</div>

<div class="mt-8">

**Resultaat:** Claude maakt presentaties die direct goed zijn 🎯

</div>

<!--
⏱️ Timing: 1-2 minuten

📌 Key points:
- CLAUDE.md = instructies voor Claude
- Bevat alle Npuls richtlijnen
- Templates, kleuren, fonts, illustraties
- Resultaat: consistent en professioneel

💡 Extra context:
"De kracht zit in het CLAUDE.md bestand. Dit bevat alle Npuls huisstijl regels, welke backgrounds te gebruiken, font instellingen, illustratie bibliotheek, en ready-to-use templates."

"Hierdoor maakt Claude presentaties die direct goed zijn - geen handmatige styling meer nodig."

🔄 Transitie:
"En als je klaar bent, kun je exporteren..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Export

<div class="mt-8">

### Naar PDF

```bash
slidev export presentation.md
```

### Naar PowerPoint

```bash
slidev export presentation.md --format pptx
```

### Presenter Mode

```bash
# In browser: druk op 'P'
# Toont notities en volgende slide
```

</div>

<!--
⏱️ Timing: 1-2 minuten

📌 Key points:
- Export naar PDF: standaard commando
- Export naar PowerPoint: --format pptx
- Presenter mode: druk 'P' in browser
- Presenter mode toont notes + volgende slide

💡 Extra context:
"Als je presentatie klaar is, kun je exporteren. Naar PDF met simpel export commando, of naar PowerPoint met --format pptx."

"En tijdens presenteren: druk op P voor presenter mode. Dan zie je je notities en een preview van de volgende slide."

🔄 Transitie:
"Dus samenvattend..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Aan de Slag!

<div class="mt-8">

### Repository

```
https://github.com/cedanl/slidev-presentaties
```

### Documentatie

Lees `CLAUDE.md` voor alle richtlijnen

### Hulp Nodig?

Vraag Claude: *"Maak een Slidev presentatie over [onderwerp] volgens de CEDA Npuls huisstijl"*

</div>

<!--
⏱️ Timing: 1 minuut

📌 Key points:
- Repository link
- CLAUDE.md documentatie
- Hoe Claude te vragen

💡 Extra context:
"Ga aan de slag! Clone de repository, lees de CLAUDE.md voor alle richtlijnen."

"En als je hulp nodig hebt: vraag Claude gewoon om een presentatie te maken volgens de CEDA Npuls huisstijl."

🎯 Call to action:
"Probeer het uit! Wie gaat vandaag nog een presentatie maken?"

🔄 Transitie:
"Dat was het! Vragen?"
-->

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide17.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<!--
⏱️ Timing: Sluitend

📌 Key points:
- Bedank publiek
- Open voor vragen

💡 Script:
"Dank je wel! Zijn er nog vragen?"
-->
