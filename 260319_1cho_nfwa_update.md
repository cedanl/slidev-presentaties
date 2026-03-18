---
theme: ./theme
title: 1CijferHO Update
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


<div class="mt-2 title-subtitle">
<strong>CEDA</strong> · 19 maart 2026 · Avans & Windesheim
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

- CEDA update
- Vertrekpunt: vorige release
- Decoding: `_decoded` en `_enriched`
- Data voorbeelden uit de echte DEMO-bestanden
- CLI & PyPI package
- Roadmap
- Staat van Avans
- Jullie behoefte

</div>
</div>

---

<!-- CEDA UPDATE -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# CEDA update

Het team is gegroeid. Dat betekent meer capaciteit, meer tijd voor doorontwikkeling, en meer ruimte om samen te werken met instellingen.

<div class="grid grid-cols-2 gap-6" style="margin-top: 1.2rem; font-size: 0.9rem; line-height: 1.8;">
<div style="background: #f0fff8; border-left: 4px solid #00AF81; padding: 0.75rem; border-radius: 4px;">

**Wat dat oplevert**

- Snellere doorontwikkeling van bestaande tools
- Meer ruimte voor nieuwe vraagstukken vanuit instellingen
- Beter onderhoud en documentatie

</div>
<div style="background: #f0f4ff; border-left: 4px solid #3D68EC; padding: 0.75rem; border-radius: 4px;">

**Waar we naartoe willen**

Samenwerken met onderwijsinstellingen aan betere onderwijsdataoplossingen. Niet bouwen voor instellingen, maar samen met ze.

</div>
</div>

<div style="margin-top: 1.2rem; font-size: 0.88rem; color: #555;">
Volg onze voortgang op GitHub: <a href="https://github.com/cedanl" style="color: #3D68EC;">github.com/cedanl</a>
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
    <p style="color: #FFFFFF; font-size: 1.3rem; margin-top: 0.5rem;">Alles wat er is bijgekomen sinds de vorige release</p>
  </div>
</div>

---

<!-- WAT WAS ER IN SEP 2025 -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Vertrekpunt: vorige release

In de vorige release was 1CijferHO een Streamlit-applicatie die fixed-width ASCII-bestanden omzette naar CSV en Parquet. Dat was het.

<div class="grid grid-cols-2 gap-6" style="margin-top: 1.2rem; font-size: 0.9rem; line-height: 1.8;">
<div style="background: #f9f9f9; border-left: 4px solid #ccc; padding: 0.75rem; border-radius: 4px;">

**Aanwezig in de vorige release**

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
pgn ; geslacht ; geboorteland ; nationaliteit_1 ; opleidingsvorm ; opleidingsfase
2   ; V        ; 6030         ; 1               ; 1              ; B
7   ; M        ; 6030         ; 1               ; 1              ; B
7   ; M        ; 6030         ; 1               ; 1              ; M
10  ; V        ; 6030         ; 1               ; 1              ; B
```

</div>

<div style="margin-top: 1rem; font-size: 0.9rem; line-height: 1.7;">

Wat betekent `6030`? Wat is nationaliteit `1`? Wat is `opleidingsvorm: 1`?
Je hebt de DUO-bestandsbeschrijving nodig om dit te begrijpen.

</div>
</div>

---

<!-- DATA VOORBEELD: EV DECODED -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# EV decoded: nieuwe opzoekkolommen

`_decoded` laat alle oorspronkelijke waarden staan. Per gecodeerde kolom komen er nieuwe opzoekkolommen bij:

<div style="margin-top: 1rem; font-size: 0.84rem; line-height: 1.7;">

```
geboorteland  →  geboorteland_naam_land
6030             Nederland
```

```
nationaliteit_1  →  nationaliteit_1_omschrijving_nationaliteit
1                   Nederlandse
```

```
instellingscode  →  instellingscode_naam_instelling
21PL                Vrije Universiteit Amsterdam
```

```
postcodecijfers_student_op_1_oktober  →  ...gemeentenaam_per_1_januari_2024
1183                                      Amstelveen
```

</div>
</div>

---

<!-- DATA VOORBEELD: EV ENRICHED -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# EV enriched: waarden vervangen

`_enriched` vervangt de gecodeerde waarden in bestaande kolommen via de variabelemetadata. De kolomnaam blijft hetzelfde, de waarde wordt leesbaar:

<div style="margin-top: 1rem; font-size: 0.84rem; line-height: 1.7;">

```
geslacht: V          →  geslacht: vrouw
geslacht: M          →  geslacht: man
```

```
opleidingsvorm: 1    →  opleidingsvorm: voltijd
```

```
opleidingsfase: B    →  opleidingsfase: bachelor
opleidingsfase: M    →  opleidingsfase: master
```

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

Het VAKHAVW-bestand krijgt nieuwe kolommen vanuit de Dec_vakcode-tabel. De originele `vakcode` blijft staan:

<div style="margin-top: 1rem; font-size: 0.84rem; line-height: 1.7;">

```
vakcode  →  vakcode_omschrijving_vak
61          Deutsche taal 1
71          Engelse taal
122         geschiedenis 1
```

```
vakcode  →  vakcode_roepnaam_vak
61          Duits 1
71          Engels
122         geschiedenis1
```

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

<!-- STAAT VAN AVANS: DOORONTWIKKELING -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Staat van Avans

Avans heeft een jaarlijkse rapportage over studentstromen binnen de instelling. CEDA gaat dit concept doorontwikkelen zodat andere instellingen er ook gebruik van kunnen maken.

<div style="margin-top: 1.2rem; font-size: 0.9rem; line-height: 1.8; background: #f9f9f9; border-left: 4px solid #ccc; padding: 0.75rem; border-radius: 4px;">

We zijn hier mee bezig. Meer volgt zodra er iets te laten zien is.

</div>
</div>

---

<!-- JULLIE BEHOEFTE -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; padding: 2rem 5rem; z-index: 1;">

<div style="font-family: 'Cooper Light BT', serif; font-size: 2rem; line-height: 1.5; color: #3D68EC;">
Waar hebben jullie nog meer behoefte aan?
</div>

<div style="margin-top: 2rem; font-size: 1rem; color: #000; line-height: 1.9; max-width: 600px;">

We zijn benieuwd wat er bij jullie speelt rond onderwijsdata. Welke analyses wil je kunnen maken? Waar loop je tegenaan? We denken graag mee.

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
