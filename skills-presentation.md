# Claude Code Skills: Automated Refactoring & Standards Compliance

## Slide 1: What are Claude Code Skills?

**Title:** Claude Code Skills voor Geautomatiseerde Workflows

**Visual concept:**
- Icon grid showing different skills as puzzle pieces that fit together
- Or: Flowchart showing `/r-package-refactor` → code transformation → `/check-style` validation

**Content:**

**Wat zijn Skills?**
- Herbruikbare AI-prompts voor specifieke taken
- Leven in `.claude/skills/` als Markdown bestanden
- Worden aangeroepen met `/skill-name` (bijv. `/r-package-refactor`)

**CEDA Skills Ecosystem**
- 📦 `/r-package-refactor` - Transform R scripts naar proper packages
- ✅ `/check-style` - Valideer code tegen CEDA standards
- 🏗️ `/init-repo` - Scaffold nieuwe projecten
- 🔄 `/migrate-cookiecutter` - Migreer oude Python repos
- 📝 `/write-issue` - GitHub issue/PR management

**Voordeel:** Consistency across projecten + snellere onboarding

---

## Slide 2: R Package Refactoring in Action

**Title:** Van Scripts naar Package: Het Refactoring Proces

**Visual concept:**
- Before/After diagram
- LEFT: Messy scripts folder structure → RIGHT: Clean package structure
- Or: Step-by-step flow diagram

**Voorbeeld transformatie:**

```
VOOR:                          NA:
scripts/                       pkgname/
├── helpers.R                  ├── R/
├── download.R                 │   ├── ingest_data.R
├── process.R                  │   ├── transform_data.R
├── analyze.R                  │   ├── run_pipeline.R
└── config.yml                 │   └── run_app.R
                               ├── inst/
                               │   ├── app/          (Shiny)
                               │   └── metadata/     (data dictionary)
                               ├── DESCRIPTION
                               └── tests/
```

**Het Proces:**
1. **Discover** - Analyseer huidige code (automatisch)
2. **Extract** - Converteer scripts → functies (phase-by-phase)
3. **Package** - Voeg DESCRIPTION, NAMESPACE toe
4. **Interactive** - Genereer Shiny app (`run_app()`)
5. **Validate** - Run `/check-style` voor CEDA compliance

**Skills werken samen:**
- `/r-package-refactor` doet het zware werk
- `/check-style` valideert het resultaat
- Beide refereren naar `standards/` documentatie

---

## Bonus Slide: Technical Architecture

**Title:** Hoe Skills Samenwerken (Optional Deep Dive)

**Visual concept:** Architecture diagram showing skill relationships

**Cross-referencing:**
```markdown
# In r-package-refactor/SKILL.md
Use `/check-style` to validate after refactoring
Use `/init-repo` for reference structure
See `standards/r-style.md` for guidelines

# In check-style/SKILL.md
Read `standards/r-style.md` for validation rules
Check against `standards/principles.md`

# Result: Single source of truth
- Standards docs = definities
- Skills = automatisering
- No duplication!
```

**Developer Experience:**

1. User runs: `/r-package-refactor`
2. Skill analyzes code → proposes plan → executes incrementally
3. At end: "Run `/check-style` to validate"
4. User runs: `/check-style` → instant feedback

**Metrics:**
- R-package skill: 1,265 lines of refactoring guidance
- After de-duplication: **-127 lines** (references standards instead)
- Check-style skill: 108 lines for validation
- Together: Complete workflow zonder duplication

---

## Speaker Notes / Extra Context

### Why This Matters for CEDA

**Consistency Problem:**
- Verschillende developers, verschillende stijlen
- Legacy repos met oude conventies
- Nieuwe medewerkers moeten standards leren

**Skills Oplossing:**
- Gecodificeerde best practices
- Instant onboarding voor nieuwe developers
- Automatische compliance checking

### R Package Refactoring: The Hard Problem

**Challenges:**
- Transformeren van scripts → functions is error-prone
- Package structure kent veel edge cases (NAMESPACE, exports, imports)
- Shiny app moet correct integreren
- Data conventions (01-raw/, 02-prepared/, 03-output/)
- Documentation in 2 talen (Dutch README, English code)

**Skill voordelen:**
- Phase-by-phase approach (incremental, get approval)
- Handles alle edge cases (explicit namespacing, `|>` pipe, `air` formatting)
- Genereert Shiny app boilerplate
- Valideert met `/check-style` at the end

### Real-World Usage

**Voor een developer:**
```bash
# Old way: Manual refactoring (2-3 days)
1. Read documentation
2. Trial and error met package structure
3. Fix namespace issues
4. Add Shiny app
5. Hope je niks vergeten bent

# New way: Skill-driven (2-3 hours)
/r-package-refactor
→ Answer 5 config questions
→ Approve transformation plan
→ Watch skill execute phase-by-phase
→ Run /check-style
→ Done! ✅
```

**Time savings:** ~80-90% reduction in refactoring tijd

### Presentation Tips

**Audience = Developers:**
- Focus op DX (Developer Experience)
- Show real code examples
- Demo live als mogelijk

**Audience = Management:**
- Focus op consistency & time savings
- Show before/after metrics
- Emphasize onboarding benefits

**Visual Aids:**
- Screenshots van skill in action
- Animated GIF van terminal tijdens refactoring
- Side-by-side code comparison
- Network diagram van skills relationships

### Call to Action

"Next time je een R script project hebt dat professioneler moet:"
- Try `/r-package-refactor`
- Contribute improvements to the skill
- Add nieuwe skills voor andere workflows

**Repo:** https://github.com/cedanl/.github
