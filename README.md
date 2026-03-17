# CEDA Clidev Presentaties

Presentatierepository van CEDA (Centre for Educational Data Analytics) in de Npuls huisstijl, gebouwd op [Slidev](https://sli.dev).

---

## Opstarten

### 1. Claude Code installeren

**macOS / Linux**

```bash
npm install -g @anthropic-ai/claude-code
```

**Windows**

```powershell
npm install -g @anthropic-ai/claude-code
```

Je hebt ook een Anthropic-account nodig. Maak er een aan via [claude.ai](https://claude.ai) en log eenmalig in via:

```bash
claude
```

### 2. Clidev skill installeren

```bash
npx skills add cedanl/clidev-presentaties
```

De skill installeert de Slidev basisskill automatisch als die nog niet aanwezig is.

### 3. Presentatie maken

Open Claude Code vanuit willekeurig welke map:

```bash
claude
```

Roep de skill aan en beschrijf wat je nodig hebt:

```
/clidev Maak een presentatie van 20 minuten over leeranalytics voor beleidsmedewerkers.
Datum: 26 maart 2026.
```

Claude zoekt het project op de machine, navigeert daarheen (of kloont het als het er nog niet staat) en maakt de presentatie aan met de juiste huisstijl, achtergronden en sprekersnotities.

---

## Projectstructuur

```
clidev-presentaties/
├── YYMMDD_onderwerp.md          # Presentatiebestanden
├── _template.md                 # Startpunt voor nieuwe presentaties
├── SKILL.md                     # Clidev skill voor Claude Code
├── theme/                       # Npuls-thema (fonts, kleuren, logo)
└── public/
    ├── npuls/
    │   ├── powerpoint_slides/   # Achtergronden (Slide1-19.PNG)
    │   ├── powerpoint_illustrations/  # 70+ SVG-iconen
    │   ├── npuls_logo.jpg
    │   └── Npuls_lettertype/    # Lettertypen
    ├── ceda_contributors/       # Teamfoto's
    └── presentations/
        └── YYMMDD_onderwerp/    # Presentatiespecifieke bestanden
```
