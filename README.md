# CEDA Clidev Presentaties

Presentatierepository van CEDA (Centre for Educational Data Analytics) in de Npuls huisstijl, gebouwd op [Slidev](https://sli.dev).

---

## Wat heb je nodig?

Je hebt twee dingen nodig om dit project te gebruiken: **Node.js** en **Git**. Heb je die al? Sla dan de installatiestappen over en ga direct naar [Project instellen](#project-instellen).

### Node.js installeren

Node.js is de software waarop Slidev draait. Je hebt versie 18 of hoger nodig.

**macOS**

Open de Terminal-app (zoek op "Terminal" via Spotlight met Cmd+Spatie) en voer het volgende in:

```bash
brew install node
```

Heb je Homebrew nog niet? Installeer het eerst via [brew.sh](https://brew.sh).

**Windows**

Open PowerShell als administrator (zoek op "PowerShell" in het Startmenu, klik rechts → Als administrator uitvoeren) en voer het volgende in:

```powershell
winget install OpenJS.NodeJS
```

Of download het installatieprogramma handmatig via [nodejs.org](https://nodejs.org) en volg de wizard.

**Linux (Ubuntu/Debian)**

```bash
sudo apt install nodejs npm
```

**Controleer de installatie**

Sluit je terminal en open hem opnieuw. Voer dan in:

```bash
node --version
```

Je ziet zoiets als `v22.0.0`. Zolang het getal 18 of hoger is, zit je goed.

### Git installeren

Git is nodig om het project te downloaden.

**macOS** — Git is meestal al geïnstalleerd. Controleer met `git --version`. Zo niet: `brew install git`

**Windows** — Download via [git-scm.com](https://git-scm.com) en volg de installer.

**Linux** — `sudo apt install git`

---

## Project instellen

Open je terminal, navigeer naar de map waar je het project wil plaatsen en voer de volgende stappen uit.

**1. Project downloaden**

```bash
git clone https://github.com/cedanl/clidev-presentaties.git
```

**2. Map openen**

```bash
cd clidev-presentaties
```

**3. Afhankelijkheden installeren**

```bash
npm install
```

Dit haalt Slidev en alle andere benodigde pakketten op. Dit duurt de eerste keer een minuutje.

---

## Een presentatie bekijken

```bash
npx slidev YYMMDD_onderwerp.md --open
```

Vervang `YYMMDD_onderwerp.md` door de bestandsnaam van de presentatie die je wil openen, bijvoorbeeld `260311_clidev.md`. De presentatie opent automatisch in je browser op `http://localhost:3030`.

**Sneltoetsen tijdens de presentatie:**

| Toets | Actie |
|-------|-------|
| Spatie / Pijl rechts | Volgende slide |
| Shift+Spatie / Pijl links | Vorige slide |
| `P` | Presentatormodus (notities + volgend slide) |
| `O` | Overzicht van alle slides |
| `F` | Volledig scherm |

Stop de server met `Ctrl+C` in de terminal.

---

## Werken met Claude Code (aanbevolen)

Claude Code is een AI-assistent in je terminal waarmee je presentaties kunt maken en bewerken via gewone tekst. De **clidev skill** geeft Claude Code alle kennis over de Npuls huisstijl, achtergronden en illustraties, en regelt automatisch de projectsetup.

### Claude Code installeren

**macOS / Linux**

```bash
npm install -g @anthropic-ai/claude-code
```

**Windows**

```powershell
npm install -g @anthropic-ai/claude-code
```

Controleer de installatie met `claude --version`.

Je hebt ook een Anthropic-account nodig. Maak er een aan via [claude.ai](https://claude.ai) en log in via:

```bash
claude
```

De eerste keer vraagt het om je in te loggen via de browser.

### Clidev skill installeren

Installeer de clidev skill eenmalig. De skill installeert de slidev basisskill automatisch als die nog niet aanwezig is.

```bash
npx skills add cedanl/clidev-presentaties
```

### Aan de slag

Open Claude Code vanuit willekeurig welke map — je hoeft het project niet zelf te clonen of te zoeken:

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

## Een nieuwe presentatie aanmaken

Geef het bestand een naam in het formaat `YYMMDD_onderwerp.md`, bijvoorbeeld `260326_leeranalytics.md`.

```bash
cp _template.md 260326_leeranalytics.md
mkdir -p public/presentations/260326_leeranalytics
```

`_template.md` bevat werkende voorbeelden van alle slidetypen in de juiste Npuls-opmaak. De map `public/presentations/260326_leeranalytics/` gebruik je voor afbeeldingen en andere bestanden die specifiek bij deze presentatie horen.

Zie de clidev skill (`SKILL.md`) voor stijlregels, achtergronden en illustraties.

---

## Exporteren

```bash
npx slidev export YYMMDD_onderwerp.md              # PDF
npx slidev export YYMMDD_onderwerp.md --format pptx # PowerPoint
npx slidev export YYMMDD_onderwerp.md --format png  # Afbeeldingen per slide
```

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
