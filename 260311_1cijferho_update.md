---
theme: default
class: text-center
title: 1CijferHO Tool - Update Maart 2026
---

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

  /* Apply fonts */
  :deep(.slide) {
    font-family: 'General Sans', Arial, Helvetica, sans-serif;
  }

  /* Headings met Npuls kleuren */
  :deep(h1) {
    color: #DD784B !important;
    font-weight: 700;
  }
  :deep(h2) {
    color: #DD784B !important;
    font-weight: 600;
  }
  :deep(h3), :deep(h4), :deep(h5), :deep(h6) {
    color: #000000 !important;
  }

  /* Subtitle op title slide - Zwart en niet bold */
  .title-subtitle {
    color: #000000 !important;
    font-weight: 400 !important;
  }

  .title-subtitle strong {
    font-weight: 400 !important;
  }

  /* Links */
  :deep(a) { color: #3D68EC; }
  :deep(a:hover) { color: #DD784B; }

  /* Strong/Bold tekst */
  :deep(strong) { color: #3D68EC; }

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

  /* Force illustrations to full visibility */
  img[src*="powerpoint_illustrations"] {
    opacity: 1 !important;
  }

  img[src*="powerpoint_illustrations"] * {
    opacity: 1 !important;
  }
</style>

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide1.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# 1CijferHO Tool

## Update Maart 2026

<div class="mt-8 text-xl title-subtitle">
<strong>CEDA</strong> - Centre for Educational Data Analytics
</div>

<div class="mt-4 text-base title-subtitle">
11 maart 2026
</div>

<!--
⏱️ Timing: 1 minuut

📌 Key points:
- Welkom gebruikers
- Laatste update was september 2025, nu tijd voor nieuwe update
- Vandaag: wat er gebeurd is en wat er nog komt

💡 Opening:
"Welkom! De laatste keer dat we een update gaven over de 1CijferHO Tool was in september 2025. Vandaag nemen we je mee in wat er sindsdien gebeurd is en vooral: wat er nog gaat komen."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide2.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="margin-left: 50%; padding-left: 2rem;">

# Agenda

<div class="mt-8">

- Korte terugblik
- Wat hebben we bereikt sinds september?
- Nieuwe release: v0.1.1
- Roadmap: waar gaan we naartoe?
- Vragen

</div>

</div>

<!--
⏱️ Timing: 30 seconden

📌 Key points:
- Kort overzicht van structuur
- We kijken terug, maar vooral vooruit

🔄 Transitie:
"Laten we beginnen met een korte terugblik..."
-->

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide13.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="font-weight: 700; font-size: 3.5rem; color: #FFFFFF;">

# Korte Terugblik

</div>

<div style="font-weight: 600; font-size: 2rem; margin-top: 1rem; color: #FFFFFF;">

## September 2025

</div>

<!--
⏱️ Timing: 30 seconden

📌 Key points:
- Hoofdstuk overgang
- Context schetsen van waar we vandaan komen

🔄 Transitie:
"Even de context: waar stonden we in september 2025?"
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Wat is de 1CijferHO Tool?

<div class="mt-6">

### Voor wie nieuw is

<div class="mt-4" style="line-height: 1.6;">

De 1CijferHO Tool maakt **1cijferHO-data direct bruikbaar** voor analyse en onderzoek:

- Automatische verwerking van complexe ASCII-bestanden
- Metadata extractie uit ongestructureerde .txt-bestanden
- Data-anonimisering (BSN-verwijdering)
- Output in CSV of Parquet formaat
- Gebruiksvriendelijke Streamlit interface
- Verwerkt gigabytes data in enkele minuten

</div>

</div>

<img src="/npuls/powerpoint_illustrations/data.svg"
     style="position: absolute; bottom: 2rem; right: 2rem; width: 140px; opacity: 1.0;"
     alt="Data" />

<!--
⏱️ Timing: 2 minuten

📌 Key points:
- Voor nieuwe gebruikers: wat doet de tool?
- Benadruk snelheid en gebruiksgemak
- 1cijferHO data is complex, wij maken het simpel

💡 Extra context:
"Voor wie nieuw is: 1cijferHO-data is notoir complex om mee te werken. Onze tool lost dat op."

🔄 Transitie:
"Nu je weet wat de tool doet, laten we kijken naar wat er gebeurd is sinds september..."
-->

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide14.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="font-weight: 700; font-size: 3.5rem; color: #FFFFFF;">

# Wat Hebben We Bereikt?

</div>

<div style="font-weight: 600; font-size: 2rem; margin-top: 1rem; color: #FFFFFF;">

## September 2025 - Maart 2026

</div>

<!--
⏱️ Timing: 30 seconden

📌 Key points:
- Hoofdstuk: resultaten
- Veel gebeurd in 6 maanden

🔄 Transitie:
"De afgelopen 6 maanden zijn we niet stil blijven zitten..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Releases & Groei

<div class="grid grid-cols-2 gap-6 mt-6">

<div>

### Nieuwe Versies

<div class="mt-3" style="line-height: 1.7;">

- **v0.9** (juni 2025) - Stable release
- **v0.9.1** (november 2025) - Bugfixes
- **v0.1.1** (maart 2026) - Huidige versie

</div>

<div class="mt-4" style="font-size: 0.9rem; line-height: 1.5;">

Elke release heeft de tool **makkelijker, duidelijker en veiliger** gemaakt.

</div>

</div>

<div>

### Community Groei

<div class="mt-3" style="line-height: 1.7;">

- **7 GitHub stars** ⭐
- **2 forks** van andere instellingen
- **151 commits** op main branch
- Gepresenteerd op **DAIR 2025**

</div>

</div>

</div>

<img src="/npuls/powerpoint_illustrations/Ster geel.svg"
     style="position: absolute; top: 2rem; right: 2rem; width: 120px; opacity: 1.0;"
     alt="Ster" />

<!--
⏱️ Timing: 2 minuten

📌 Key points:
- Drie releases, steeds beter
- Community groeit (niet alleen CEDA)
- Presentatie op DAIR toont vertrouwen

💡 Extra context:
"DAIR is het jaarlijkse congres voor data-analisten in het onderwijs - dat we daar mochten presenteren is een mooie erkenning."

🔄 Transitie:
"Maar wat hebben die releases nou concreet gebracht?"
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Belangrijkste Verbeteringen

<div class="mt-5">

### Sinds September 2025

<div class="grid grid-cols-2 gap-5 mt-4" style="line-height: 1.7;">

<div>

**Toegankelijkheid**
- Nu makkelijk te installeren
- Werkt op alle besturingssystemen
- Snellere onboarding nieuwe gebruikers

**Gebruikerservaring**
- Duidelijkere foutmeldingen
- Betere documentatie
- Intuïtievere interface

</div>

<div>

**Impact**
- Sneller van data naar inzicht
- Meer onderwijsinstellingen gebruiken de tool
- Presentatie op landelijk congres (DAIR 2025)

**Samenwerking**
- Open source community groeit
- 2 forks door andere instellingen
- Actieve ontwikkeling

</div>

</div>

</div>

<img src="/npuls/powerpoint_illustrations/Vaantje geel met vink.svg"
     style="position: absolute; bottom: 1.5rem; right: 2rem; width: 130px; opacity: 1.0;"
     alt="Vinkje" />

<!--
⏱️ Timing: 2 minuten

📌 Key points:
- Toegankelijkheid verbeterd - minder drempels
- Impact groeit - meer gebruikers, meer instellingen
- Presentatie op DAIR toont impact binnen sector

💡 Extra context:
"Belangrijkste is dat de tool nu echt voor iedereen toegankelijk is, niet alleen voor technische specialisten."

🔄 Transitie:
"Dit brengt ons bij de nieuwste release..."
-->

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide15.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="font-weight: 700; font-size: 3.5rem; color: #FFFFFF;">

# Nieuwe Release

</div>

<div style="font-weight: 600; font-size: 2rem; margin-top: 1rem; color: #FFFFFF;">

## v0.1.1 - Maart 2026

</div>

<!--
⏱️ Timing: 30 seconden

📌 Key points:
- Focus op nieuwste release
- Beschikbaar sinds 11 maart (vandaag!)

🔄 Transitie:
"Vandaag is de nieuwste versie uitgebracht..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# v0.1.1: Wat is er nieuw?

<div class="mt-5" style="line-height: 1.8;">

### Belangrijkste Verbeteringen

**Makkelijker te Gebruiken**
- Eenvoudige installatie met één commando
- Werkt direct uit de doos
- Geen technische kennis meer nodig voor installatie

**Duidelijker**
- Data wordt automatisch leesbaar gemaakt
- Betere documentatie en hulp
- Helder overzicht van wat er gebeurt

**Veiliger**
- Gestandaardiseerde installatie methode
- Betere validatie van data
- Privacy en anonimisering voorop

</div>

<img src="/npuls/powerpoint_illustrations/Pakket compact.svg"
     style="position: absolute; bottom: 1.5rem; right: 2rem; width: 140px; opacity: 1.0;"
     alt="Pakket" />

<!--
⏱️ Timing: 2 minuten

📌 Key points:
- Drie pijlers: Makkelijker, Duidelijker, Veiliger
- Lage drempel = meer gebruik = meer impact
- Privacy en veiligheid blijven voorop staan

💡 Extra context:
"De tool was al goed, maar we willen dat iedereen die met 1cijferHO-data werkt hem kan gebruiken - ongeacht technisch niveau."

🔄 Transitie:
"Dit is allemaal mooi, maar waar gaan we naartoe?"
-->

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide13.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="font-weight: 700; font-size: 3.5rem; color: #FFFFFF;">

# Roadmap

</div>

<div style="font-weight: 600; font-size: 2rem; margin-top: 1rem; color: #FFFFFF;">

## Wat Staat Ons Te Wachten?

</div>

<!--
⏱️ Timing: 30 seconden

📌 Key points:
- Van terugkijken naar vooruitkijken
- Roadmap is publiek op GitHub

🔄 Transitie:
"Laten we kijken naar wat er nog gaat gebeuren..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Roadmap: Korte Termijn

<div class="mt-5">

### Volgende Maanden

<div class="mt-4" style="line-height: 1.9;">

**Gebruikerservaring**
- Nog snellere verwerking van grote datasets
- Verbeterde stabiliteit en betrouwbaarheid
- Actuele demo-bestanden (versie 2025/2026)

**Toegankelijkheid**
- Nog makkelijkere installatie op Windows
- Betere documentatie en voorbeelden
- Video tutorials en handleidingen

**Kwaliteitsborging**
- Uitgebreidere automatische testen
- Meer validatie van resultaten
- Proactieve foutopsporing

</div>

</div>

<img src="/npuls/powerpoint_illustrations/Pijlen rechts grafisch.svg"
     style="position: absolute; bottom: 1.5rem; right: 2rem; width: 120px; opacity: 1.0;"
     alt="Pijlen" />

<!--
⏱️ Timing: 2-3 minuten

📌 Key points:
- Refactoring = beter onderhoudbare code
- Testing = hogere betrouwbaarheid
- Demo updates = actueel blijven

💡 Extra context:
"Scoop is een package manager voor Windows, vergelijkbaar met Homebrew op Mac. Dit maakt installatie op Windows nóg makkelijker."

🔄 Transitie:
"En op langere termijn..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Roadmap: Lange Termijn

<div class="mt-5">

### Toekomstvisie

<div class="mt-4" style="line-height: 1.9;">

**Veilig Samenwerken**
- Integratie met Secure Data Platform (SDP)
- Veilig delen van analyses tussen instellingen
- Privacy-by-design uitbreidingen

**Bredere Inzetbaarheid**
- Ondersteuning voor meer databronnen
- Makkelijker combineren met andere data
- Standaardisatie van analyses

**Sectorbrede Impact**
- Gebruik door meerdere onderwijsinstellingen
- Kennis delen binnen sector
- Samenwerking met beleidmakers en onderzoekers

</div>

</div>

<img src="/npuls/powerpoint_illustrations/netwerk.svg"
     style="position: absolute; bottom: 1.5rem; right: 2rem; width: 140px; opacity: 1.0;"
     alt="Netwerk" />

<!--
⏱️ Timing: 2-3 minuten

📌 Key points:
- SDP integratie = veilig werken met gevoelige data
- Performance blijft belangrijk bij groeiende datasets
- Community focus = samenwerking binnen sector

💡 Extra context:
"SDP is ons Secure Data Platform waar we veilig met privacygevoelige data kunnen werken. De tool daar integreren is een logische volgende stap."

🎯 Call to action:
"We zijn altijd op zoek naar feedback en bijdragen. GitHub issues en pull requests zijn welkom!"

🔄 Transitie:
"Laten we afsluiten met hoe je betrokken kunt blijven..."
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Hoe Blijf Je Betrokken?

<div class="mt-5" style="line-height: 1.7;">

### Mogelijkheden

**Gebruik de Tool**
- Installeer via PyPI: `pip install 1cijferho`
- Geef feedback via GitHub Issues
- Deel je use cases met ons

**Volg Ontwikkelingen**
- Star de repository op GitHub
- Watch releases voor updates
- Bekijk de publieke roadmap

**Bijdragen**
- Code contributions via pull requests
- Documentatie verbeteringen
- Bug reports en feature requests

</div>

<div class="mt-5 text-center" style="font-size: 1.1rem;">

**GitHub**: [github.com/cedanl/1cijferho](https://github.com/cedanl/1cijferho)

</div>

<img src="/npuls/powerpoint_illustrations/Connecties.svg"
     style="position: absolute; bottom: 1.5rem; right: 2rem; width: 140px; opacity: 1.0;"
     alt="Connecties" />

<!--
⏱️ Timing: 2 minuten

📌 Key points:
- Meerdere manieren om betrokken te blijven
- Feedback is waardevol
- Open source = samenwerking

💡 Extra context:
"Jullie feedback is ontzettend waardevol geweest. Veel features zijn geboren uit gebruikersvragen."

🔄 Transitie:
"Zijn er vragen?"
-->

---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

# Vragen?

<div class="mt-8 text-center" style="font-size: 1.3rem; line-height: 2;">

**Contact**

CEDA - Centre for Educational Data Analytics

GitHub: [cedanl/1cijferho](https://github.com/cedanl/1cijferho)

</div>

<img src="/npuls/powerpoint_illustrations/Boeken roze blauw.svg"
     style="position: absolute; bottom: 2rem; right: 2rem; width: 140px; opacity: 1.0;"
     alt="Boeken" />

<!--
⏱️ Timing: 5-10 minuten (Q&A)

📌 Key points:
- Open voor alle vragen
- Technisch, gebruik, roadmap - alles mag

💡 Mogelijke vragen voorbereiden:
- "Hoe upgrade ik van oude versie naar v0.1.1?"
- "Kan de tool ook met andere databronnen werken?"
- "Hoe kan ik bijdragen aan development?"
- "Wat is de timeline voor SDP integratie?"

🔄 Afsluiting:
"Bedankt voor jullie aandacht en jullie voortdurende gebruik van de tool!"
-->

---
class: text-center
---

<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide17.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<!--
⏱️ Timing: Closing slide

📌 GEEN TEKST op deze slide - alleen de background

💡 Laat deze slide zien terwijl mensen weglopen of laatste vragen stellen
-->
