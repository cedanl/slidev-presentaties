---
class: text-center
title: CEDA Projecten Update Sessie
info: |
  ## Interactieve Update Sessie
  Presentatie van updates op 1CijferHO en introductie van No Fairness Without Awareness (NFWA)

  - 1CijferHO: Nieuwe decodeerfuncties en verbeteringen
  - NFWA: Kansengelijkheidsanalyse in het hoger onderwijs
drawings:
  persist: false
transition: slide-left
mdc: true
duration: 60min
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
    opacity: 0.9;
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

  /* Cover layout with prominent background */
  :deep(.layout-cover) {
    background-size: cover !important;
  }

  :deep(.layout-cover h1),
  :deep(.layout-cover h2) {
    text-shadow: 1px 1px 2px rgba(255, 255, 255, 0.9);
  }

  /* Ensure backgrounds show through clearly */
  :deep([style*="background"]) {
    filter: none !important;
    opacity: 1 !important;
  }

  /* H1 - Primary titles (Npuls Blue) */
  :deep(h1) {
    color: #3D68EC !important;
    font-weight: 700 !important;
    font-size: 3.2rem !important;
    letter-spacing: -0.5px;
  }

  /* H2 - Subtitles (Npuls Orange) */
  :deep(h2) {
    color: #DD784B !important;
    font-weight: 600 !important;
    font-size: 1.8rem !important;
  }

  /* H3 - Section headers (Black) */
  :deep(h3) {
    color: #000000 !important;
    font-weight: 600 !important;
    font-size: 1.4rem !important;
  }

  /* H4-H6 - Subsections (Black) */
  :deep(h4), :deep(h5), :deep(h6) {
    color: #000000 !important;
    font-weight: 500 !important;
  }

  /* Section slides */
  :deep(.layout-section h1) {
    color: #3D68EC !important;
    font-size: 3.8rem !important;
    font-weight: 700;
  }

  :deep(.layout-section h2) {
    color: #DD784B !important;
    font-size: 2rem !important;
    font-weight: 600;
  }

  /* Links in Npuls Blue */
  :deep(a) {
    color: #3D68EC !important;
    font-weight: 600;
  }

  :deep(a:hover) {
    color: #DD784B !important;
  }

  /* Strong/Bold text in Npuls Blue */
  :deep(strong) {
    color: #3D68EC !important;
    font-weight: 700;
  }

  /* Code blocks with Npuls accent */
  :deep(pre) {
    background-color: #F9F9F9 !important;
    border-left: 5px solid #3D68EC !important;
    border-radius: 4px;
  }

  :deep(code) {
    color: #000000 !important;
  }

  /* Table styling with Npuls colors */
  :deep(table) {
    border-collapse: collapse;
    width: 100%;
  }

  :deep(table thead) {
    background-color: #3D68EC !important;
    color: white !important;
  }

  :deep(table thead th) {
    padding: 12px;
    font-weight: 600;
  }

  :deep(table tbody tr) {
    border-bottom: 1px solid #E8E8E8;
  }

  :deep(table tbody tr:hover) {
    background-color: #F4D9DC !important;
  }

  :deep(table td) {
    padding: 10px 12px;
    color: #000000;
  }

  /* List items */
  :deep(li) {
    color: #000000;
    line-height: 1.8;
  }

  /* Top border accent for section breaks */
  :deep(.top-border-blue) {
    border-top: 4px solid #3D68EC !important;
  }

  :deep(.top-border-orange) {
    border-top: 4px solid #DD784B !important;
  }

  :deep(.top-border-green) {
    border-top: 4px solid #00AF81 !important;
  }

  /* Centered text styling */
  :deep(.text-center) {
    color: #000000;
  }

  /* Emphasis box */
  :deep(.emphasis-box) {
    background-color: #F4D9DC;
    border-left: 4px solid #DD784B;
    padding: 1rem;
    border-radius: 4px;
    color: #000000;
  }
</style>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; z-index: 1; padding: 2rem 4rem;">

<h1 style="color: #DD784B !important;">CEDA Projecten Update</h1>

<div class="grid grid-cols-2 gap-8 mt-2">
  <div>
    <h3>1CijferHO</h3>
    <p>Updates & Nieuwe Functies</p>
  </div>
  <div>
    <h3>NFWA</h3>
    <p>Introductie Kansengelijkheid</p>
  </div>
</div>

</div>

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide2.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div class="grid grid-cols-2 gap-8 mt-8">
  <div class="text-center">
    <img src="/ceda_contributors/tomer_iwan.jpg" alt="Tomer Iwan" class="h-56 rounded-lg mx-auto shadow-lg">
    <h3 class="mt-4 text-xl font-bold">Tomer Iwan</h3>
    <p class="mt-2 text-base font-semibold">Data Engineer @ CEDA</p>
    <p class="mt-3 text-sm leading-relaxed">Verantwoordelijk voor data pipelines, verwerking en kwaliteit van onderwijsgegevens</p>
  </div>
  <div class="text-center">
    <img src="/ceda_contributors/aslam_tanjung.jpg" alt="Aslam Tanjung" class="h-56 rounded-lg mx-auto shadow-lg">
    <h3 class="mt-4 text-xl font-bold">Aslam Tanjung</h3>
    <p class="mt-2 text-base font-semibold">Data Scientist @ CEDA</p>
    <p class="mt-3 text-sm leading-relaxed">Specialisatie in machine learning, fairness analysis en onderwijsonderzoek</p>
  </div>
</div>

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# 1CijferHO Updates

## Wat jullie hebben gevraagd

---

# Over 1CijferHO

Een hulpmiddel dat het verwerken van 1CHO onderwijsgegevens automatiseert:
- **Fixed-width ASCII-bestanden** met onduidelijke scheidingen
- **Ongestructureerde metadata** in .txt-formaat

### Belangrijkste Voordelen
- ⏱️ Verwerk gigabytes aan data in minuten
- ✅ Automatische validatie voorkomt fouten
- 🔒 Privacy-first: Anonimiseert BSN en gevoelige gegevens automatisch
- 📊 Output: Schone CSV of Parquet-bestanden klaar voor analyse

---

# Huidig Workflow

1. **Uploaden** → Plaats DUO-bestanden in inputmap
2. **Metadata Uitpakken** → Veldposities parsen uit .txt-bestanden
3. **Valideren** → Controleer gegevensintegriteit en veldovereenkomsten
4. **Converteren** → Multiprocessing voor snelheid
5. **Output** → Schone bestanden klaar voor analyse

---
transition: slide-up
---

# 🎯 Hoofdverzoek: Decodeerfuncties

Jullie hebben gevraagd om **gedecodeerde versies** naast originele bestanden

### Wat betekent dit?
Coded waarden omzetten naar leesbare labels voor makkelijker onderzoek

### Waarom belangrijk?
- **Makkelijker te interpreteren** van onderzoeksresultaten
- **Snellere analyse** zonder handmatige opzoekingen
- **Betere documentatie** van bevindingen in rapporten

---

# Decoding in Actie: EV-bestand

### Origineel (Coded)

```csv
persoonsgebonden_nummer;inschrijvingsjaar;opleidingsvorm;opleidingsfase
2;2008;1;B
7;2006;1;B
```

### Gedecodeerd

```csv
persoonsgebonden_nummer;inschrijvingsjaar;opleidingsvorm;opleidingsfase
2;2008;voltijd;bachelor
7;2006;voltijd;bachelor
```

<div class="text-sm mt-4">
✅ Nu direct leesbaar in analyses en rapporten
</div>

---

# Decoding in Actie: VAKHAVW-bestand

### Origineel (Coded)

```csv
persoonsgebonden_nummer;diplomajaar;gemiddeld_cijfer;vakcode
127425;2006;66;123
127425;2006;66;131
```

### Gedecodeerd

```csv
persoonsgebonden_nummer;diplomajaar;gemiddeld_cijfer;vak_afkorting
127425;2006;66;Geschiedenis
127425;2006;66;Aardrijkskunde
```

---

# Implementatie Decodeer-functie

### Pipeline met Decoding

```
Raw Data Bestand
    ↓
[Metadata Uitpakken + Decodeertabellen]
    ↓
├─→ Originele Versie (coded waarden)
└─→ Gedecodeerde Versie (leesbare labels)
    ↓
Schone CSV/Parquet Output
```

### Ondersteunde Decoderingen
- 📚 Onderwijsprogrammacodes → Namen
- 👤 Vooropleidingscodes → Types (VWO, HAVO, etc.)
- 🎓 Onderwijsniveaucodes → Bachelor/Master
- 🏆 Vakcodes → Vaknamen
- 🗺️ Geografische codes

---

# Updates in Volgende Release

## Geplande Functies

<div v-click class="my-4">

### 1. **Decodeerfunctionaliteit** ✅
Gedecodeerde versies naast originele bestanden

</div>

<div v-click class="my-4">

### 2. **Windows 11 Installatiezekerheid**
Minder foutmeldingen, soepelere setup

</div>

<div v-click class="my-4">

### 3. **Bijgewerkte Demo-bestanden**
2025/2026 voorbeelden met documentatie

</div>

---

# Toekomstige Roadmap (1CijferHO)

<div class="grid grid-cols-2 gap-6 mt-8">

<div>

### Korte Termijn
- 🔧 Windows stabiliteitsfixes
- 📚 Bijgewerkte demo-bestanden
- 🎯 Decodeerfunctie v1.0 launch

</div>

<div>

### Middellange Termijn
- 🏗️ Refactor voor library-gebruik
- ☁️ Cloud hosting via SURF
- 🧪 Unit tests

</div>

</div>

<div v-click class="mt-8 text-sm opacity-75">

### Visie
Transformatie van localhost-app → Professionele desktop/cloud-oplossing

</div>

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide10.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# No Fairness Without Awareness (NFWA)

## Waarom Onderzoeken We Kansengelijkheid?

---

# Het Probleem in Nederlandse Hoger Onderwijs

### Waarneming
Sommige studentengroepen behalen lager succes ondanks gelijke studiebekwaamheid

### Oorzaken
- ❓ Verborgen selectie in toelating
- ❓ Verborgen patronen in onderwijs
- ❓ Ondersteuning is niet voor alle groepen gelijk
- ❓ Gegevens laten patronen zien - maar welke?

### Gevolgen
- 📉 Ongelijke kansen voor gelijke talenten
- 📊 Onderbenutting van potentieel
- 🎓 Verlies van diversiteit in vervolgonderwijs/beroep

---

# Waarom is Dit Moeilijk te Detecteren?

### Huidig Aanpak
- ✋ Handmatige Excel-analyses
- ⚠️ Risico op fouten en selectieve interpretatie
- 🔍 Lastig om verborgen patronen te zien
- 📈 Data is groter dan ooit

### De Uitdaging
Hoe kun je **objectief** en **systematisch** bias detecteren in onderwijsdata?

> 💡 Dit is precies waarom NFWA bestaat

---

# NFWA: Machine Learning voor Fairness

Een **R-package** dat fairness-analyse automatiseert en toegankelijk maakt

### Core Filosofie
Gebruik **machine learning als instrument** (niet als doel) om bias in data te detecteren

### Onderzoeksgrondslag
Onderzoek van Theo Bakker (LTA, De Haagse Hogeschool) naar kansengelijkheid in hoger onderwijs

---

# Wat NFWA Meet

### Fairness-Metrieken met Praktische Betekenis

<div class="mt-8 space-y-6">

<div class="p-4 bg-blue-50 rounded-lg">

**Gelijke Kans (Equal Opportunity)**

Hebben alle groepen gelijke slagingskans?

</div>

<div class="p-4 bg-green-50 rounded-lg">

**Voorspellende Gelijkheid (Predictive Parity)**

Zijn modelpredikties even betrouwbaar per groep?

</div>

</div>

---

# Fairness-Metrieken (vervolg)

<div class="mt-8 space-y-6">

<div class="p-4 bg-orange-50 rounded-lg">

**Nauwkeurigheidsgelijkheid (Accuracy Equality)**

Zijn foutpercentages gelijk voor alle groepen?

</div>

<div class="p-4 bg-pink-50 rounded-lg">

**Statistische Pariteit (Statistical Parity)**

Krijgen groepen dezelfde positieve uitkomsten?

</div>

</div>

---

# NFWA Workflow: 3 Stappen

```
Stap 1: Voorbereiding
├─ Laad 1CHO data (EV + VAKHAVW)
└─ Definieer gevoelige variabelen (geslacht, vooropleiding, etc.)

Stap 2: Machine Learning Analyse
├─ Train twee modellen (Logistic Regression + Random Forest)
├─ Meet fairness per gevoelige groep
└─ Genereer visualisaties

Stap 3: Rapportage
└─ Automatische PDF met bevindingen & aanbevelingen
```

---

# NFWA Output: Het PDF-Rapport

### Wat zit erin?

<div class="grid grid-cols-2 gap-8 mt-6">
<div>

**Inleiding (Niet-technisch)**
- "Wat is kansengelijkheid?"
- "Hoe werkt deze analyse?"
- Thermometer-analogie

**Methodologie**
- Data voorbereiding
- Model training uitgelegd
- Fairness metrieken
- Bias classificatie (FRN scores)

</div>
<div>

**Visualisaties**
- 📊 Dichtheidsplots per groep
- 📈 Fairness-controle plots
- 🎯 Resultaten samenvatting

**Interpretatie & Acties**
- Wat te doen bij bias
- Vervolgstappen
- Beperkingen

</div>
</div>

---

# NFWA Output: Voorbeeld Visualisaties

<div class="grid grid-cols-2 gap-6 mt-8">
<div>

### Dichtheidsplots
Toont de verdeling van voorspellingen per groep

### Fairness Checks
Visualiseert verschillen tussen groepen met metrieken

</div>
<div>

### Glossarium
22 termen uitgelegd:
- Machine learning concepten
- Fairness metrieken
- Onderwijs-specifieke termen

</div>
</div>

---

# NFWA in Actie: Snelstart

```r
library(nfwa)

# Laad 1CHO data (uit 1cijferho output)
data_ev <- read.csv("ev_data.csv", sep = ";")
data_vakhavw <- read.csv("vakhavw_data.csv", sep = ";")

# Volledige analyse in één functie
result <- analyze_fairness(
  data_ev = data_ev,
  data_vakhavw = data_vakhavw,
  opleidingsnaam = "B International Business Administration",
  eoi = 2010,
  opleidingsvorm = "VT",  # Voltijd
  generate_pdf = TRUE
)
```

**Output**: PDF-rapport automatisch gegenereerd! 📄

---

# NFWA Gegevensvereisten

### Input Data Format

**data_ev** (Studentenniveau)
- 1CHO inschrijvingsgegevens per student
- Retentie-indicator (geslaagd/niet geslaagd)
- Student-ID (Persoonsgebonden nummer)
- Gevoelige variabelen: geslacht, vooropleiding, etc.

**data_vakhavw** (Vakniveau)
- 1CHO-cijfers per student
- Gekoppeld via student-ID

> 💡 **Pro Tip**: Gebruik 1CijferHO om je gegevens voor te bereiden!

---

# NFWA Metadata (Ingebouwd!)

### Geen Setup Nodig ✅

Package wordt geleverd met standaard metadata:
- 📋 Variabele definities en categorieën
- 🗺️ Geografische verrijking (APCG, SES PC4)
- 🔤 Decodeertabellen voor onderwijscodes

### Resultaat
- **Installeren** → **Gebruiken** (geen metadata-voorbereiding!)
- Werkt meteen
- Optioneel: eigen metadata gebruiken

---

# Installatievereisten

### Wat heb je nodig?

| Hulpmiddel | Versie | Doel |
|----------|--------|------|
| **R** | 4.3+ | Kerncode |
| **RStudio** | Nieuwste | IDE (aanbevolen) |
| **Quarto** | Nieuwste | PDF-generatie |
| **TinyTeX** | Nieuwste | LaTeX-ondersteuning |
| **Rtools** | Nieuwste | Alleen Windows |

<div v-click class="mt-4 text-sm">

> ⚠️ Meest voorkomend probleem: Quarto niet in PATH na installatie
> Oplossing: Start R/RStudio volledig opnieuw op

</div>

---

# Package Functies Referentie

### Hoofdfuncties

```r
analyze_fairness()        # ⭐ Volledige analyse (aanbevolen)
read_metadata()           # Laad ingebouwde metadata
transform_data()          # Bereid rauwe 1CHO-gegevens voor
run_nfwa()               # Voer kansengelijkheidsanalyse uit
render_report()          # Genereer PDF-rapport
cleanup_temp()           # Ruim tijdelijke bestanden op
```

### Help Verkrijgen
```r
?nfwa                    # Package-overzicht
vignette("nfwa")         # Volledige tutorial met voorbeelden
```

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide16.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Integratie: 1CijferHO + NFWA

## Een Volledige Workflow

---

# End-to-End Voorbeeld

### Scenario: Analyseer Programma-Fairness

<div v-click class="my-4">

**Stap 1: Bereid Gegevens Voor**
```bash
# Gebruik 1CijferHO met nieuwe decodeerfuncties
1cijferho → schone & gedecodeerde CSV-bestanden
```

</div>

<div v-click class="my-4">

**Stap 2: Analyseer Kansengelijkheid**
```r
# Gebruik NFWA met gedecodeerde gegevens
nfwa::analyze_fairness(...) → fairness inzichten
```

</div>

<div v-click class="my-4">

**Stap 3: Communiceer Resultaten**
```
PDF-rapport met visualisaties & aanbevelingen
Klaar voor stuurgroep/management
```

</div>

---

# Gebruiksscenario's

### Veelvoorkomende Situaties

<div class="grid grid-cols-2 gap-6 text-sm">

<div>

**Programma-evaluatie**
- Is toelating eerlijk voor verschillende demografische groepen?
- Verschillen de retentiecijfers naar geslacht/vooropleiding?

**Institutionele Analyse**
- Welke programma's hebben interventie nodig?
- Waar zijn de grootste gelijkheid-gaten?

</div>

<div>

**Beleidsvorming**
- Op feiten gebaseerd inschrijvingsbeleid
- Gerichte ondersteuningsprogramma's
- Transparantierapportage

</div>

</div>

---

# Unieke Kenmerken

### Waarom NFWA Speciaal Is

✅ **Domeinspecifiek**
- Gebouwd voor hoger onderwijscontext
- Begrijpt 1CHO-gegevensformaat

✅ **Gebruikersvriendelijk**
- Volledige analyse in één functie
- Ingebouwde metadata (geen setup)
- Automatische PDF-rapporten voor niet-technische doelgroepen

✅ **Wetenschappelijk Onderbouwd**
- Onderzoeksgebaseerde fairness-metrieken
- Transparante algoritmes
- Reproduceerbare analyses

✅ **Open Source**
- Toegankelijk voor iedereen
- Community feedback
- Gebaseerd op gepubliceerde onderzoeksmethoden

---

# CEDA: Centre for Educational Data Analytics

### Missie
Onderwijsinstellingen helpen sneller van data naar betrouwbare inzichten te gaan, zodat instellingen controle behouden in een snel veranderende wereld

### Wat we doen
- 🔬 Co-creatie met MBO, HBO en WO-instellingen
- 🛠️ Ontwikkelen van praktisch bruikbare tools (1CijferHO, NFWA, etc.)
- 📊 Data-gestuurde inzichten toegankelijk maken voor iedereen
- 🌐 Delen van succesvolle producten en kennis tussen instellingen

### Ons Doel
Onderwijsinstellingen in staat stellen zelf data-gedreven besluiten te nemen

---

# Projectstatistieken

<div class="grid grid-cols-3 gap-6 mt-8">

<div class="text-center">
  <h3 class="text-3xl">2</h3>
  <p>Hoofdprojecten</p>
  <p class="text-sm">(1CHO + NFWA)</p>
</div>

<div class="text-center">
  <h3 class="text-3xl">100K+</h3>
  <p>Studenten in data</p>
  <p class="text-sm">(Demo datasets)</p>
</div>

<div class="text-center">
  <h3 class="text-3xl">∞</h3>
  <p>Potentiële impact</p>
  <p class="text-sm">(Gelijke kansen)</p>
</div>

</div>

---

# Bronnen & Meer Informatie

### GitHub Repositories

<div class="grid grid-cols-2 gap-6 text-sm mt-6">
<div>

**1CijferHO**
- cedanl/1cijferho
- README.md & ROADMAP.md
- Demo: Ingebouwde voorbeeldbestanden
</div>
<div>

**NFWA**
- cedanl/no-fairness-without-awareness
- Vignette: `vignette("nfwa")`
- PDF rapport voorbeelden
</div>
</div>

### Onderzoek

- Bakker, T. (2024). *No Fairness without Awareness* - Intreerede over kansengelijkheid in hoger onderwijs

---

# Vragen & Discussie

## Laten We Erover Praten!

### Onderwerpen voor Discussie

<div class="mt-6 text-center text-sm" style="list-style: none;">

Decodeerfuncties in 1CijferHO
Implementatie fairness-metrieken
Gegevenspipeline-vragen
Integraatiemogelijkheden
Feedback op toekomstige roadmap

</div>

---

# Dank Jullie Wel

## Tot ziens over twee weken!

<div class="mt-8 text-center text-sm" style="list-style: none;">

Voor vragen of feedback:

📧 GitHub Issues
💬 Direct contact
🤝 Bijdrage-ideeën welkom

</div>

<div class="abs-br m-6 text-xs opacity-50">
<p>Slides gemaakt met Slidev</p>
<p>© Centre for Educational Data Analytics (CEDA)</p>
</div>
