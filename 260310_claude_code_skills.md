---
class: text-center
title: Claude Code Skills - Automated Refactoring & Standards Compliance
info: |
  ## Claude Code Skills voor Geautomatiseerde Workflows
  Presentatie over herbruikbare AI-prompts voor specifieke ontwikkeltaken

  - Wat zijn Claude Code Skills?
  - R Package Refactoring in actie
  - Skills Ecosystem & Cross-Referencing
  - Best Practices & Voorbeelden
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

  /* Make backgrounds more prominent */
  :deep(.slidev-layout) {
    background-size: cover !important;
    background-position: center !important;
    background-repeat: no-repeat !important;
  }

  /* Add text shadow for better readability on backgrounds */
  :deep(.text-shadow h1),
  :deep(.text-shadow h2),
  :deep(.text-shadow h3) {
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
  }

  /* Headings with Npuls colors */
  :deep(h1) {
    color: #DD784B !important;
    font-weight: 700;
    font-size: 3rem;
    margin-bottom: 1rem;
  }

  :deep(h2) {
    color: #DD784B !important;
    font-weight: 600;
    font-size: 2rem;
    margin-top: 1.5rem;
    margin-bottom: 1rem;
  }

  :deep(h3),
  :deep(h4),
  :deep(h5),
  :deep(h6) {
    color: #000000 !important;
    font-weight: 600;
  }

  :deep(h3) {
    font-size: 1.5rem;
  }

  /* Subtitle op title slide - Oranje maar NIET bold */
  .title-subtitle {
    color: #DD784B !important;
    font-weight: 400 !important;
  }

  .title-subtitle strong {
    font-weight: 400 !important;
  }

  /* Links */
  :deep(a) {
    color: #3D68EC;
    text-decoration: underline;
  }

  :deep(a:hover) {
    color: #DD784B;
  }

  /* Strong/Bold text */
  :deep(strong) {
    color: #3D68EC;
    font-weight: 700;
  }

  /* Lists */
  :deep(ul),
  :deep(ol) {
    font-size: 1.1rem;
    line-height: 1.8;
    margin-left: 1.5rem;
  }

  :deep(li) {
    margin-bottom: 0.5rem;
  }

  /* Code blocks */
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
    margin: 1rem 0;
    overflow-x: auto;
  }

  :deep(pre code) {
    background-color: transparent;
    color: #000000;
    padding: 0;
  }

  /* Paragraphs */
  :deep(p) {
    font-size: 1.1rem;
    line-height: 1.6;
    margin-bottom: 1rem;
  }

  /* Grid layouts */
  :deep(.grid) {
    display: grid;
  }

  :deep(.grid-cols-2) {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  :deep(.gap-8) {
    gap: 2rem;
  }

  /* Utility classes */
  .text-shadow {
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
  }

  .mt-8 {
    margin-top: 2rem;
  }

  .mt-4 {
    margin-top: 1rem;
  }

  .text-center {
    text-align: center;
  }

  /* Force alle illustraties volledig zichtbaar */
  img[src*="powerpoint_illustrations"] {
    opacity: 1 !important;
  }

  img[src*="powerpoint_illustrations"] * {
    opacity: 1 !important;
  }
</style>

# Slidev Presentaties

## Snel professionele slides maken met Claude

<div class="mt-8 text-xl">
<strong>CEDA</strong> - Centre for Educational Data Analytics
</div>

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Presentatie door

<div class="grid grid-cols-1 gap-8 mt-8" style="max-width: 400px; margin-left: auto; margin-right: auto;">
  <div class="text-center">
    <img src="/ceda_contributors/aslam_tanjung.jpg"
         alt="Aslam Tanjung"
         class="h-56 rounded-lg mx-auto shadow-lg">
    <h3 class="mt-4 text-xl font-bold">Aslam Tanjung</h3>
    <p class="mt-2 text-base font-semibold">Data Scientist @ CEDA</p>
    <p class="mt-3 text-sm leading-relaxed">Gespecialiseerd in data pipelines en R package development</p>
  </div>
</div>

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide2.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="margin-left: 50%; padding-left: 2rem;">

# Wat zijn Claude Code Skills?

## Herbruikbare AI-prompts voor specifieke taken

<div class="mt-8">

**Wat zijn skills?**
- Herbruikbare AI-instructies voor specifieke taken
- Staan opgeslagen in `.claude/skills/` als Markdown bestanden
- Roep je aan met `/skill-naam` (bijvoorbeeld `/r-package-refactor`)

</div>

</div>

<img src="/npuls/powerpoint_illustrations/Puzzelstuk 3D.svg"
     style="position: absolute; bottom: 8rem; left: 2rem; width: 160px; height: auto; opacity: 1.0;"
     alt="Puzzle piece" />

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# CEDA Skills Ecosystem

<div class="mt-8">

### Beschikbare Skills bij CEDA

- 📦 `/r-package-refactor` - Zet R scripts om naar volwaardige packages
- ✅ `/check-style` - Controleer code volgens CEDA standaarden
- 🏗️ `/init-repo` - Maak nieuwe projecten aan met juiste structuur
- 🔄 `/migrate-cookiecutter` - Migreer oude Python projecten
- 📝 `/write-issue` - Beheer GitHub issues en pull requests

</div>

<div class="mt-8">

**Voordeel:** Consistentie tussen projecten en snellere inwerkperiode

</div>

<img src="/npuls/powerpoint_illustrations/Blokken stapel.svg"
     style="position: absolute; bottom: 2rem; right: 2rem; width: 140px; height: auto; opacity: 1.0;"
     alt="Building blocks" />

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide14.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="font-weight: 700; font-size: 3.5rem;">

# R Package Refactoring

</div>

<div style="font-weight: 600; font-size: 2rem; margin-top: 1rem;">

## Van Scripts naar Package

</div>

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Transformatie Voorbeeld

<img src="/npuls/powerpoint_illustrations/Pijlen rechts grafisch.svg"
     style="position: absolute; top: 50%; left: 42%; transform: translate(-50%, -50%); width: 80px; height: auto; opacity: 1.0; z-index: 0;"
     alt="Transformation arrows" />

<div class="grid grid-cols-2 gap-8 mt-8" style="position: relative; z-index: 1; margin-left: 3rem;">
  <div>
    <h3>VOOR:</h3>
    <pre><code>scripts/
├── helpers.R
├── download.R
├── process.R
├── analyze.R
└── config.yml</code></pre>
  </div>

  <div>
    <h3>NA:</h3>
    <pre><code>pkgname/
├── R/
│   ├── ingest_data.R
│   ├── transform_data.R
│   ├── run_pipeline.R
│   └── run_app.R
├── inst/
│   ├── app/
│   └── metadata/
├── DESCRIPTION
└── tests/</code></pre>
  </div>
</div>

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Het Refactoring Proces

<img src="/npuls/powerpoint_illustrations/Pakket compact.svg"
     style="position: absolute; bottom: 2rem; right: 2rem; width: 150px; height: auto; opacity: 1.0;"
     alt="Package" />

<div class="mt-8">

### Stap-voor-stap aanpak

1. **Ontdekken** - Analyseer de huidige code (automatisch)
2. **Extraheren** - Zet scripts om naar functies (stap voor stap)
3. **Verpakken** - Voeg DESCRIPTION en NAMESPACE toe
4. **Interactief** - Maak een Shiny app (`run_app()`)
5. **Valideren** - Draai `/check-style` om CEDA standaarden te controleren

</div>

<div class="mt-8">

**Hoe skills samenwerken:**
- `/r-package-refactor` doet het zware werk
- `/check-style` controleert het resultaat
- Beide verwijzen naar dezelfde `standards/` documentatie

</div>

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide13.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="font-weight: 700; font-size: 3.5rem;">

# Technische Architectuur

</div>

<div style="font-weight: 600; font-size: 2rem; margin-top: 1rem;">

## Hoe Skills Samenwerken

</div>

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Onderlinge Verwijzingen

<div class="mt-8">

```markdown
# In r-package-refactor/SKILL.md
Gebruik `/check-style` om te controleren na refactoring
Gebruik `/init-repo` voor referentie structuur
Zie `standards/r-style.md` voor richtlijnen

# In check-style/SKILL.md
Lees `standards/r-style.md` voor validatie regels
Controleer tegen `standards/principles.md`

# Resultaat: Eén bron van waarheid
- Standaarden documenten = definities
- Skills = automatisering van die standaarden
- Geen dubbel werk!
```

</div>

<img src="/npuls/powerpoint_illustrations/Connecties.svg"
     style="position: absolute; top: 2rem; right: 2rem; width: 140px; height: auto; opacity: 1.0;"
     alt="Connections" />

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Ontwikkelaar Ervaring

<div class="mt-8">

### Werkwijze

1. Ontwikkelaar draait: `/r-package-refactor`
2. Skill analyseert code → stelt plan voor → voert stap voor stap uit
3. Aan het einde: "Draai `/check-style` om te controleren"
4. Ontwikkelaar draait: `/check-style` → directe feedback

</div>

<div class="mt-8">

### Cijfers

- R-package skill: 1.265 regels refactoring instructies
- Na deduplicatie: **-127 regels** (verwijst naar standaarden)
- Check-style skill: 108 regels voor validatie
- Samen: Compleet werkproces zonder dubbel werk

</div>

<img src="/npuls/powerpoint_illustrations/laptop.svg"
     style="position: absolute; bottom: 1.5rem; right: 2rem; width: 140px; height: auto; opacity: 1.0;"
     alt="Laptop" />

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Waarom Dit Belangrijk Is

<div class="mt-8">

## Het Probleem

- Verschillende ontwikkelaars, verschillende stijlen
- Oude projecten met verouderde conventies
- Nieuwe medewerkers moeten standaarden leren

</div>

<div class="mt-8">

## De Oplossing met Skills

- ✅ Vastgelegde beste werkwijzen
- ✅ Snelle inwerkperiode voor nieuwe ontwikkelaars
- ✅ Automatische controle van standaarden

</div>

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Tijdsbesparing

<img src="/npuls/powerpoint_illustrations/Stopwatch.svg"
     style="position: absolute; top: 2rem; right: 2rem; width: 120px; height: auto; opacity: 1.0;"
     alt="Stopwatch" />

<div class="grid grid-cols-2 gap-8 mt-8">
  <div>
    <h3>Oude Manier:</h3>
    <p><strong>Handmatig refactoren (2-3 dagen)</strong></p>
    <ol>
      <li>Lees documentatie</li>
      <li>Uitproberen en fouten maken bij package structuur</li>
      <li>Los namespace problemen op</li>
      <li>Voeg Shiny app toe</li>
      <li>Hoop dat je niks vergeten bent</li>
    </ol>
  </div>

  <div>
    <h3>Nieuwe Manier:</h3>
    <p><strong>Met skills (2-3 uur)</strong></p>
    <ol>
      <li>Draai <code>/r-package-refactor</code></li>
      <li>Beantwoord 5 configuratie vragen</li>
      <li>Keur het transformatie plan goed</li>
      <li>Kijk hoe de skill stap voor stap werkt</li>
      <li>Draai <code>/check-style</code></li>
      <li>Klaar! ✅</li>
    </ol>
  </div>
</div>

<div class="mt-8 text-center">

**Tijdsbesparing:** ongeveer 80-90% minder tijd nodig

</div>

---
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Volgende Stappen

<img src="/npuls/powerpoint_illustrations/Vaantje geel met vink.svg"
     style="position: absolute; bottom: 2rem; right: 2rem; width: 140px; height: auto; opacity: 1.0;"
     alt="Success flag" />

<div class="mt-8">

### Heb je een R script project dat professioneler moet?

- Probeer `/r-package-refactor` uit
- Draag verbeteringen bij aan de skills
- Maak nieuwe skills voor andere werkprocessen

</div>

<div class="mt-8">

**Repository:** https://github.com/cedanl/.github

</div>

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide17.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

