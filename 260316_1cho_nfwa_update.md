---
theme: ./theme
title: 1CijferHO Update & NFWA
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
transition: slide-left
mdc: true
---

<!-- TITELSLIDE -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide1.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div class="title-center">

# 1CijferHO Update

## Nieuwe features, data voorbeelden & introductie NFWA

<div class="mt-2 title-subtitle">
<strong>CEDA</strong> · 16 maart 2026 · Avans & Windesheim
</div>
</div>

---

<!-- AGENDA -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide2.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="margin-left: 50%; padding-left: 2rem; height: 100%; display: flex; flex-direction: column; justify-content: center;">

## Agenda

<div style="font-size: 1rem; line-height: 2.2; margin-top: 1rem;">

- Wat was er in september 2025?
- Decoding: `_decoded` en `_enriched`
- Data voorbeelden uit de echte DEMO-bestanden
- CLI & PyPI package
- Roadmap
- Introductie NFWA
- Staat van Avans
- Pijl interesse

</div>
</div>

---

<!-- HOOFDSTUK: 1CIJFERHO -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide13.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div class="flex items-center justify-center h-full">
  <div style="text-align: center;">
    <h1 style="color: #FFFFFF !important; font-size: 3rem;">1CijferHO</h1>
    <p style="color: #FFFFFF; font-size: 1.3rem; margin-top: 0.5rem;">Alles wat er is bijgekomen sinds september 2025</p>
  </div>
</div>

---

<!-- WAT WAS ER IN SEP 2025 -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Vertrekpunt: september 2025

In september 2025 was 1CijferHO een Streamlit-applicatie die fixed-width ASCII-bestanden omzette naar CSV en Parquet. Dat was het.

<div class="grid grid-cols-2 gap-6" style="margin-top: 1.2rem; font-size: 0.9rem; line-height: 1.8;">
<div style="background: #f9f9f9; border-left: 4px solid #ccc; padding: 0.75rem; border-radius: 4px;">

**Aanwezig in september 2025**

- Streamlit UI (upload, extract, validate, convert)
- Fixed-width naar CSV en Parquet
- Multiprocessing conversie
- BSN-anonimisering

</div>
<div style="background: #f0fff8; border-left: 4px solid #00AF81; padding: 0.75rem; border-radius: 4px;">

**Nieuw sindsdien**

- Decoding: `_decoded` en `_enriched` varianten
- Demo-bestanden getrackt in git
- eencijferho als installeerbaar Python-package (PyPI)
- CLI: `eencijferho pipeline`
- Verbeterde validatiemeldingen
- Versie 0.1.1

</div>
</div>
</div>

---

<!-- DECODING: CONCEPT -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Decoding: drie outputs per bestand

Voor elk EV- en VAKHAVW-bestand levert de pipeline nu drie varianten op:

<div class="grid grid-cols-3 gap-4" style="margin-top: 1.2rem; font-size: 0.87rem; line-height: 1.65;">
<div style="background: #f0f4ff; border-left: 4px solid #3D68EC; padding: 0.75rem; border-radius: 4px;">

**`EV_2024.csv`**

Het originele bestand, gecodeerde waarden precies zoals DUO ze aanlevert.

`opleidingsvorm: 1`
`opleidingsfase: B`
`geslacht: V`

</div>
<div style="background: #f0fff8; border-left: 4px solid #00AF81; padding: 0.75rem; border-radius: 4px;">

**`EV_2024_decoded.csv`**

Originele waarden **onveranderd**. Nieuwe opzoekkolommen toegevoegd vanuit de DEC-tabellen.

`geslacht: V` ← zelfde
`geboorteland_naam_land:` `'Nederland'`
`actuele_instelling_naam:` `'Avans'`

</div>
<div style="background: #fff8f0; border-left: 4px solid #DD784B; padding: 0.75rem; border-radius: 4px;">

**`EV_2024_enriched.csv`**

Waarden in bestaande kolommen **vervangen** via variabelemetadata + DEC.

`opleidingsvorm: voltijd`
`opleidingsfase: bachelor`
`geslacht: vrouw`

</div>
</div>
</div>

---

<!-- DATA VOORBEELD: EV ORIGINEEL -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# EV origineel: gecodeerde waarden

Het oorspronkelijke bestand na conversie van fixed-width naar CSV. Kolomnamen al genormaliseerd naar snake_case.

<div style="margin-top: 1rem; font-size: 0.82rem; line-height: 1.5;">

```
persoonsgebonden_nummer ; inschrijvingsjaar ; opleidingsvorm ; opleidingsfase ; geslacht
2                       ; 2008              ; 1              ; B              ; V
7                       ; 2006              ; 1              ; B              ; M
7                       ; 2010              ; 1              ; M              ; M
10                      ; 2007              ; 1              ; B              ; V
```

</div>

<div style="margin-top: 1rem; font-size: 0.9rem; line-height: 1.7;">

`opleidingsvorm: 1` = voltijd, `2` = deeltijd, `3` = duaal. Dat zie je hier niet.
`opleidingsfase: B` = bachelor, `M` = master.
`geslacht: V` = vrouw, `M` = man. Dat moet je ook apart weten.

</div>
</div>

---

<!-- DATA VOORBEELD: EV DECODED -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# EV decoded: nieuwe opzoekkolommen

`_decoded` laat alle oorspronkelijke waarden staan, maar voegt nieuwe kolommen toe via de DEC-tabellen uit de bestandsbeschrijving:

<div style="margin-top: 1rem; font-size: 0.82rem; line-height: 1.5;">

```
geslacht ; geboorteland_naam_land ; nationaliteit_1_omschrijving_nationaliteit
V        ; Nederland              ; Nederlandse
M        ; Turkije                ; Nederlandse
M        ; Turkije                ; Nederlandse
V        ; Nederland              ; Nederlandse
```

```
actuele_instelling_naam          ; postcode_gemeentenaam
Vrije Universiteit Amsterdam     ; Amstelveen
Vrije Universiteit Amsterdam     ; Amsterdam
...
```

</div>

<div style="margin-top: 0.8rem; font-size: 0.87rem;">
`geslacht` blijft `V` en `M`. Voor de vertaling naar vrouw/man is de variabelemetadata nodig, niet de DEC-tabellen.
</div>
</div>

---

<!-- DATA VOORBEELD: EV ENRICHED -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# EV enriched: waarden vervangen

`_enriched` gebruikt ook de variabelemetadata en vervangt daarmee de gecodeerde waarden in bestaande kolommen:

<div class="grid grid-cols-2 gap-6" style="margin-top: 1rem; font-size: 0.82rem; line-height: 1.5;">
<div>

**Origineel**

```
opleidingsvorm ; opleidingsfase ; geslacht
1              ; B              ; V
1              ; B              ; M
1              ; M              ; M
1              ; B              ; V
```

</div>
<div>

**Enriched**

```
opleidingsvorm ; opleidingsfase ; geslacht
voltijd        ; bachelor       ; vrouw
voltijd        ; bachelor       ; man
voltijd        ; master         ; man
voltijd        ; bachelor       ; vrouw
```

</div>
</div>

<div style="margin-top: 1rem; font-size: 0.87rem; line-height: 1.7;">
Plus alle DEC-opzoekkolommen die `_decoded` ook heeft. `_enriched` is de meest complete variant.
</div>
</div>

---

<!-- DATA VOORBEELD: VAKHAVW -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# VAKHAVW decoded: vakcode uitgebreid

Het VAKHAVW-bestand krijgt drie nieuwe kolommen vanuit de Dec_vakcode-tabel:

<div class="grid grid-cols-2 gap-6" style="margin-top: 1rem; font-size: 0.82rem; line-height: 1.5;">
<div>

**Origineel**

```
pgn    ; diplomajaar ; vakcode ; afkorting_vak
117706 ; 2005        ; 61      ; du1
117706 ; 2005        ; 71      ; en
117706 ; 2005        ; 122     ; gs1
117706 ; 2005        ; 123     ; gs
```

`vakcode` is een numerieke code.

</div>
<div>

**Decoded: nieuwe kolommen**

```
vakcode ; vakcode_omschrijving_vak    ; vakcode_roepnaam_vak
61      ; Deutsche taal 1            ; Duits 1
71      ; Engelse taal               ; Engels
122     ; geschiedenis 1             ; geschiedenis1
123     ; geschiedenis               ; geschiedenis
```

De originele `vakcode` blijft staan, naast de nieuwe kolommen.

</div>
</div>
</div>

---

<!-- FEATURE: CLI & PYPI -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# eencijferho als Python-package

De backend is nu een installeerbaar Python-package, gepubliceerd op PyPI. Je kunt het gebruiken zonder de Streamlit UI.

<div class="grid grid-cols-2 gap-6" style="margin-top: 1rem; font-size: 0.85rem; line-height: 1.6;">
<div>

**Installeren**

```bash
pip install eencijferho
```

**CLI: stap voor stap**

```bash
eencijferho extract  --input invoer/ --output uitvoer/
eencijferho validate --input invoer/ --output uitvoer/
eencijferho convert  --input invoer/ --output uitvoer/
```

</div>
<div>

**CLI: alles in één**

```bash
eencijferho pipeline --input invoer/ --output uitvoer/
```

Metadata (JSON, logs, Excel) gaat automatisch naar `uitvoer/metadata/`. Databestanden staan in de uitvoermap zelf.

</div>
</div>
</div>

---

<!-- PIPELINE OVERZICHT -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# De volledige pipeline nu

<div style="margin-top: 1rem; font-size: 0.9rem; line-height: 1.9;">

| Stap | Omschrijving | Nieuw? |
|------|-------------|--------|
| 1 | Conversie fixed-width naar CSV | |
| 2 | Decoding naar `_decoded.csv` en `_enriched.csv` | Nieuw |
| 3 | Validatie conversieresultaten | Verbeterd |
| 4 | Compressie naar Parquet | |
| 5 | Encryptie van outputbestanden | Nieuw |
| 6 | Header normalisatie naar snake_case | Nieuw |

</div>
</div>

---

<!-- ROADMAP -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Roadmap

<div class="grid grid-cols-3 gap-4" style="margin-top: 1rem; font-size: 0.88rem; line-height: 1.7;">
<div>

**Komende release**

- Windows 11: stabielere installatie met minder foutmeldingen bij Python & C++ dependencies
- Demo-bestanden bijgewerkt naar versie 2025/2026 inclusief gebruiksuitleg

</div>
<div>

**Hierna**

- Installatie valideren via VM of Docker
- Functies krijgen kleinere scope: data-invoer en verwerking worden gescheiden
- Verdere ontwikkeling als herbruikbare library

</div>
<div>

**Later / ideeën**

- Onderzoek naar cloud-hosting via SURF
- Streamlit-projecten integreren in cloud-omgeving
- Unit tests voor de conversie-pipeline

</div>
</div>
</div>

---

<!-- HOOFDSTUK: NFWA -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide14.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div class="flex items-center justify-center h-full">
  <div style="text-align: center;">
    <h1 style="color: #FFFFFF !important; font-size: 2.8rem;">No Fairness Without Awareness</h1>
    <p style="color: #FFFFFF; font-size: 1.2rem; margin-top: 0.5rem;">Introductie van het R-package</p>
  </div>
</div>

---

<!-- NFWA: WAT IS HET -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Wat is NFWA?

<div class="grid grid-cols-2 gap-6" style="margin-top: 1rem; font-size: 0.9rem; line-height: 1.8;">
<div>

Een R-package voor kansengelijkheidsanalyse in het hoger onderwijs. Ontwikkeld op basis van het onderzoek van lector Dr. Theo Bakker (LTA, De Haagse Hogeschool).

**De kernvraag:** zijn er in studiedata patronen die wijzen op ongelijke kansen voor bepaalde studentgroepen?

Het prognosemodel is het instrument voor de analyse, niet het einddoel.

</div>
<div>

```r
library(nfwa)

data_ev <- read.csv("EV_2024.csv", sep = ";")
data_vakhavw <- read.csv("VAKHAVW_2024.csv",
                          sep = ";")

result <- analyze_fairness(
  data_ev        = data_ev,
  data_vakhavw   = data_vakhavw,
  opleidingsnaam = "B Bedrijfskunde",
  eoi            = 2019,
  opleidingsvorm = "VT",
  generate_pdf   = TRUE
)
```

</div>
</div>
</div>

---

<!-- NFWA: HOE WERKT HET -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Hoe werkt NFWA?

`analyze_fairness()` voert vier stappen automatisch uit:

<div style="margin-top: 1rem; font-size: 0.9rem; line-height: 1.85;">

**Stap 1: Metadata inlezen**
Ingebouwde metadata: variabeledefinities, APCG- en SES-verrijkingstabellen, decode-tabellen voor vooropleiding en ISAT-codes. Niets hoef je zelf aan te leveren.

**Stap 2: Data transformeren**
1CHO-data gefilterd op opleiding, opleidingsvorm en `eoi` (eerste jaar aan de opleiding). Retentie bepaald, vooropleiding gedecodeerd, APCG en SES toegevoegd op basis van postcode.

**Stap 3: Fairness-analyse**
Twee ML-modellen (Logistic Regression + Random Forest) getraind. Per sensitieve variabele fairness-metrieken berekend en visualisaties gegenereerd in `temp/`.

**Stap 4: PDF-rapport**
Quarto compileert een volledig rapport met plots, conclusies en een glossarium.

</div>
</div>

---

<!-- NFWA: METRIEKEN -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Fairness-metrieken

<div class="grid grid-cols-2 gap-6" style="margin-top: 1rem; font-size: 0.88rem; line-height: 1.75;">
<div>

**Gelijke kans (Equal Opportunity)**
Heeft elke groep een gelijke kans op een positieve uitkomst (retentie)? Kijkt naar de true positive rate per groep.

**Nauwkeurigheidsgelijkheid (Accuracy Equality)**
Is het foutpercentage van het model gelijk voor alle groepen?

</div>
<div>

**Predictieve pariteit (Predictive Parity)**
Als het model een positieve uitkomst voorspelt, klopt dat dan even vaak voor alle groepen?

**Statistische pariteit (Statistical Parity)**
Krijgen groepen ongeacht prestatie dezelfde verhouding positieve uitkomsten?

</div>
</div>

<div style="margin-top: 1.2rem; font-size: 0.88rem; background: #f0f4ff; border-left: 4px solid #3D68EC; padding: 0.75rem; border-radius: 4px;">
Geen van deze metrieken is "de beste". Ze belichten verschillende dimensies van eerlijkheid. Het rapport helpt bepalen welke metriek relevant is voor de specifieke onderzoeksvraag.
</div>
</div>

---

<!-- HOOFDSTUK: STAAT VAN AVANS -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide15.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div class="flex items-center justify-center h-full">
  <div style="text-align: center;">
    <h1 style="color: #FFFFFF !important; font-size: 3rem;">Staat van Avans</h1>
    <p style="color: #FFFFFF; font-size: 1.2rem; margin-top: 0.5rem;">Doorontwikkeling en de stap naar andere instellingen</p>
  </div>
</div>

---

<!-- STAAT VAN AVANS: WAT IS HET -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Staat van Avans: wat is het?

<div class="grid grid-cols-2 gap-6" style="margin-top: 1rem; font-size: 0.9rem; line-height: 1.8;">
<div>

De **Staat van Avans** is een jaarlijkse rapportage die Avans zelf heeft ontwikkeld over de studentstromen binnen de instelling. Ze brengt in kaart wie instroomt, hoeveel studenten uitvallen, wat het rendement is en hoeveel studenten van studie wisselen.

De analyses worden uitgesplitst naar vooropleiding, leeftijdsgroep en HBOsector. Zo wordt zichtbaar waar Avans het goed doet en waar aandacht nodig is.

</div>
<div>

**Losstaand van NFWA**

NFWA analyseert fairness per opleiding: zijn er ongelijke kansen voor bepaalde studentgroepen? De Staat van Avans kijkt breder: het is een instellingsoverzicht van studentstromen over alle opleidingen heen.

Ze kunnen elkaar aanvullen, maar zijn onafhankelijk van elkaar.

</div>
</div>
</div>

---

<!-- STAAT VAN AVANS: DOORONTWIKKELING -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Doorontwikkeling: van Avans naar alle instellingen

Avans heeft de Staat van Avans zelf ontwikkeld. CEDA wil dit concept doorontwikkelen zodat elke instelling die haar 1CHO-data aanlevert een vergelijkbare rapportage kan krijgen.

<div style="margin-top: 1.2rem; font-size: 0.88rem; line-height: 1.6;">

```
1CHO-data instelling X
       ↓
 eencijferho pipeline (conversie + decoding)
       ↓
 gestandaardiseerde CSV-output
       ↓
 Staat van [Instelling X]
 (instroom · rendement · uitval · studiewissel)
```

</div>

<div style="margin-top: 1rem; font-size: 0.9rem; line-height: 1.7;">

Het rapport is vergelijkbaar opgebouwd voor elke instelling. Zo kunnen instellingen patronen bij zichzelf herkennen en, als ze dat willen, vergelijken met anderen.

</div>
</div>

---

<!-- PIJL INTERESSE -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; padding: 2rem 5rem; z-index: 1;">

<div style="font-family: 'Cooper Light BT', serif; font-size: 2rem; line-height: 1.5; color: #3D68EC;">
Zou Windesheim ook zo'n rapportage willen?
</div>

<div style="margin-top: 2rem; font-size: 1rem; color: #000; line-height: 1.9; max-width: 600px;">

Avans heeft de Staat van Avans zelf ontwikkeld. CEDA wil dit concept doorontwikkelen zodat andere instellingen er ook gebruik van kunnen maken. We zijn benieuwd of Windesheim daar interesse in heeft.

</div>

<div style="margin-top: 2rem; font-size: 1.1rem; font-weight: 600; color: #DD784B;">
Laat het ons weten
</div>

</div>

---

<!-- AFSLUITSLIDE -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide17.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>
