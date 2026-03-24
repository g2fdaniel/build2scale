---
name: new-project
description: Legt ein neues Projekt im Build2Scale-Repo an — mit vollständiger 6-seitiger Blueprint-Website, Memory-Eintrag und GitHub-Push. Aufruf wenn Daniel ein neues Projekt blueprinten will das in Build2Scale verwaltet wird.
---

Du legst ein neues Projekt im Build2Scale-Repo an.

## Kontext

Das Build2Scale-Repo liegt lokal unter:
`/Users/danielhofmann/Meine Ablage/Claude/Build2Scale/`

Es ist ein git-Repo, verknüpft mit `github.com/courzly/build2scale`.
GitHub Pages: `https://courzly.github.io/build2scale/`

Bestehende Projekte als Referenz:
- `Inner-Circle/` — Inner Circle Club für Fortuneglobe

## Ablauf

### Schritt 1: Projektinfos sammeln
Falls nicht aus $ARGUMENTS klar, frage nach:
- Projektname (kurz, für Ordnernamen, z.B. `loyalty-shop`)
- Auftraggeber / Kunde
- Kurzbeschreibung des Ziels
- Repo-URL oder lokaler Pfad zur Codebase (falls vorhanden)
- Budget & Deadline (falls bekannt)
- Angebotsnummer (falls vorhanden)

### Schritt 2: Codebase lesen (falls Repo vorhanden)
Klone das Repo oder lies die Dateien.
Verschaffe dir Überblick über:
- Tech Stack, Frameworks, Architektur
- Datenbankschema
- Bestehende Module die für das neue Feature relevant sind
- Deployment-Setup

### Schritt 3: Projektordner anlegen
Lege an: `/Users/danielhofmann/Meine Ablage/Claude/Build2Scale/{projekt-slug}/`

Erstelle die 6 HTML-Dateien als vollständige, verlinkte Website:
- `index.html` — Landing mit Karten-Navigation zu den 5 Unterseiten
- `konzept.html` — Architektur, Features (MVP + Phase 2), Design, Abgrenzungen
- `anforderungen.html` — Datenmodell, Feeds/Schnittstellen, Flows
- `technik.html` — Dateistruktur, Coding-Konventionen, Bestehende Dateien
- `projektmanagement.html` — 4-Wochen-Plan, Vorgehen, Offene Fragen
- `implementierung.html` — Implementierungs-Prompt (Copy & Use für Claude/Cursor)

**Design-Referenz:** Schau dir `Inner-Circle/index.html` an — gleiches CSS, gleiche Navbar-Struktur, gleiches Dark Theme. Passe Farben/Inhalte an das neue Projekt an.

Jede Datei braucht:
- Vollständiges CSS (identisch mit Inner-Circle)
- Sticky Navbar mit Links zu allen 6 Seiten (aktive Seite mit class="nav-link active")
- Footer mit Prev/Next Navigation

### Schritt 4: Memory-Eintrag erstellen
Lege an:
`/Users/danielhofmann/.claude/projects/-Users-danielhofmann-Meine-Ablage-Claude-Build2Scale/memory/project_{projekt-slug}.md`

Format:
```markdown
---
name: {Projektname}
description: {Ein-Satz-Beschreibung}
type: project
---

{Auftraggeber} beauftragt go2flow mit {Kurzbeschreibung}.

**Budget:** {Budget} | **Frist:** {Deadline}
**Repo:** {Repo-URL}
**Blueprint:** /Users/danielhofmann/Meine Ablage/Claude/Build2Scale/{slug}/

**Why:** {Warum wird das gebaut?}

**How to apply:** {Wie soll Claude dieses Wissen nutzen?}
```

Aktualisiere auch:
`/Users/danielhofmann/.claude/projects/-Users-danielhofmann-Meine-Ablage-Claude-Build2Scale/memory/MEMORY.md`

### Schritt 5: Commit & Push
```bash
cd "/Users/danielhofmann/Meine Ablage/Claude/Build2Scale"
git add {projekt-slug}/
git commit -m "Add {projekt-name} blueprint"
git push
```

### Schritt 6: Zusammenfassung
Berichte Daniel:
- Projektordner erstellt: `{pfad}`
- Live-URL: `https://courzly.github.io/build2scale/{slug}/`
- Memory-Eintrag erstellt
- Was noch offen ist (offene Fragen, fehlende Infos)
