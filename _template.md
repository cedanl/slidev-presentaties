---
theme: ./theme
title: Titel van de presentatie
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
transition: slide-left
mdc: true
---

<!-- TITELSLIDE (Slide1.PNG) -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide1.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div class="title-center">

# Titel

## Ondertitel

<div class="mt-2 title-subtitle">
<strong>CEDA</strong> - Centre for Educational Data Analytics
</div>
</div>

---

<!-- AGENDAISLIDE (Slide2.PNG) — tekst rechts, afbeelding links -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide2.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="margin-left: 50%; padding-left: 2rem; height: 100%; display: flex; flex-direction: column; justify-content: center;">

## Agenda

<div style="font-size: 1rem; line-height: 2; margin-top: 1rem;">

- Onderwerp 1
- Onderwerp 2
- Onderwerp 3

</div>
</div>

---

<!-- HOOFDSTUKSLIDE (Slide13/14/15.PNG) — witte tekst verplicht, geen bullets -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide13.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div class="flex items-center justify-center h-full">
  <h1 style="color: #FFFFFF !important; font-size: 3rem;">Hoofdstuk 1</h1>
</div>

---

<!-- CONTENTSLIDE — bullets (Slide3.PNG) -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Slidetitel

<div style="font-size: 0.95rem; line-height: 1.8; margin-top: 1rem;">

- Punt één
- Punt twee
- Punt drie

</div>
</div>

---

<!-- TWEEKOLOMMEN (Slide3.PNG) -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Slidetitel

<div class="grid grid-cols-2 gap-6" style="font-size: 0.9rem; line-height: 1.7; margin-top: 1rem;">
<div>

**Links**
- Punt één
- Punt twee
- Punt drie

</div>
<div>

**Rechts**
- Punt één
- Punt twee
- Punt drie

</div>
</div>
</div>

---

<!-- DRIEKOLOMMEN (Slide3.PNG) -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Slidetitel

<div class="grid grid-cols-3 gap-4" style="font-size: 0.9rem; line-height: 1.6; margin-top: 1rem;">
<div>

**Kolom 1**

Tekst of bullets hier.

</div>
<div>

**Kolom 2**

Tekst of bullets hier.

</div>
<div>

**Kolom 3**

Tekst of bullets hier.

</div>
</div>
</div>

---

<!-- CITAAT / HIGHLIGHT (Slide3.PNG) -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; padding: 3rem 5rem; z-index: 1;">

<div style="font-family: 'Cooper Light BT', serif; font-size: 1.8rem; line-height: 1.5; color: #3D68EC;">
"Citaat of kernboodschap die de aandacht trekt."
</div>

<div style="margin-top: 1.5rem; font-size: 0.9rem; color: #000;">— Naam, Functie</div>

</div>

---

<!-- CODE DEMO (Slide3.PNG) -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Slidetitel

```python {1|3-5|all}
# Stap 1: importeer de bibliotheek
import pandas as pd

# Stap 2: laad de data
df = pd.read_csv("data.csv")
print(df.head())
```

</div>

---

<!-- TABEL (Slide3.PNG) -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Slidetitel

| Kolom A | Kolom B | Kolom C |
|---------|---------|---------|
| Waarde 1 | Waarde 2 | Waarde 3 |
| Waarde 4 | Waarde 5 | Waarde 6 |

</div>

---

<!-- ILLUSTRATIE + TEKST (Slide3.PNG) -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide3.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>

<div style="position: absolute; inset: 0; display: flex; flex-direction: column; justify-content: center; padding: 2rem 4rem; z-index: 1;">

# Slidetitel

<div class="grid grid-cols-2 gap-6" style="margin-top: 1rem; align-items: center;">
<div style="font-size: 0.95rem; line-height: 1.8;">

- Punt één
- Punt twee
- Punt drie

</div>
<div style="display: flex; justify-content: center;">
  <img src="/npuls/powerpoint_illustrations/data.svg" style="width: 180px;" />
</div>
</div>
</div>

---

<!-- AFSLUITSLIDE (Slide17.PNG) — geen tekst -->
<div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: -1;">
  <img src="/npuls/powerpoint_slides/Slide17.PNG" style="width: 100%; height: 100%; object-fit: cover;" />
</div>
