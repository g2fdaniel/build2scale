---
name: update-blueprint
description: Aktualisiert den Blueprint eines bestehenden Projekts mit neuen Informationen (Meeting-Notizen, E-Mails, PDFs, etc.) und pushed die Änderungen zu GitHub. Aufruf wenn Daniel neue Infos zu einem Projekt teilt.
---

Du aktualisierst den Blueprint eines bestehenden Build2Scale-Projekts.

## Kontext

Das Build2Scale-Repo liegt lokal unter:
`/Users/danielhofmann/Meine Ablage/Claude/Build2Scale/`

Es ist ein git-Repo, verknüpft mit `github.com/courzly/build2scale`.
GitHub Pages läuft unter `https://courzly.github.io/build2scale/`.

Jedes Projekt hat eine 6-seitige HTML-Website:
- `index.html` — Übersicht / Landing
- `konzept.html` — Architektur, Features, Design, Abgrenzungen
- `anforderungen.html` — Datenmodell, Feeds, Flows
- `technik.html` — Dateistruktur, Coding-Konventionen, Codeänderungen
- `projektmanagement.html` — Plan, Vorgehen, Koordination, Offene Fragen
- `implementierung.html` — Implementierungs-Prompt (Copy & Use)

## Ablauf

### Schritt 1: Projekt identifizieren
Falls nicht aus $ARGUMENTS klar: Frage Daniel welches Projekt aktualisiert werden soll.
Lies das aktuelle `index.html` des Projekts um den Stand zu verstehen.

### Schritt 2: Neue Informationen analysieren
Analysiere die neuen Informationen die Daniel bereitgestellt hat:
- Was ist neu? Was widerspricht dem bisherigen Stand?
- Welche der 6 Seiten sind betroffen?
- Gibt es neue offene Fragen oder geklärte Entscheidungen?

### Schritt 3: Richtige Seiten updaten
Lies die betroffenen HTML-Dateien **zuerst vollständig**, dann mach die gezielten Änderungen:
- Neue Features → konzept.html
- Neue Anforderungen, DB-Änderungen, Flows → anforderungen.html
- Neue technische Entscheidungen, Dateistruktur → technik.html
- Neue Projektkoordination, Timeline, Offene Fragen → projektmanagement.html
- Geänderte Coding-Konventionen → implementierung.html

Wichtig:
- Bestehenden Inhalt nicht einfach überschreiben — ergänzen und verfeinern
- Offene Fragen die geklärt wurden: als beantwortet markieren oder entfernen
- Neue offene Fragen hinzufügen
- Sektionsnummern konsistent halten

### Schritt 4: Commit & Push
```bash
cd "/Users/danielhofmann/Meine Ablage/Claude/Build2Scale"
git add {projekt-ordner}/
git commit -m "Update {projekt-name}: {kurze Beschreibung der Änderungen}"
git push
```

### Schritt 5: Zusammenfassung
Berichte Daniel kurz:
- Welche Seiten wurden geändert
- Was die wichtigsten inhaltlichen Updates sind
- Die Live-URL: `https://courzly.github.io/build2scale/{projekt-ordner}/`
