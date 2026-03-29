---
name: concept-analysis-spec
description: "Strukturierte Analyse und Spezifikation neuer Anforderungen. Erstellt sequenziell: Konzeptdokument, Ist-Analyse, Anforderungsanalyse und Implementierungsspezifikation unter ./docs/, gefolgt von GitHub Issues via gh. Verwende diesen Skill wenn der User eine neue Anforderung, ein neues Feature, eine Änderung oder Erweiterung beschreibt und dafür eine strukturierte Analyse, Spezifikation und Issue-Erstellung benötigt."
---

# Concept Analysis Spec

Strukturierte Analyse und Spezifikation von Anforderungen in 5 Schritten:

1. **Konzeptdokument** erstellen (`docs/01-konzept-<thema>.md`)
2. **Ist-Analyse** erstellen (`docs/02-ist-analyse-<thema>.md`)
3. **Anforderungsanalyse** erstellen (`docs/03-anforderungsanalyse-<thema>.md`)
4. **Spezifikation** erstellen (`docs/04-spezifikation-<thema>.md`)
5. **GitHub Issues** anlegen via `gh issue create`

## Workflow

### Vorbereitung

- `<thema>` aus der Anforderung des Users ableiten (kurz, kebab-case, z.B. `user-auth`, `api-caching`)
- Verzeichnis `./docs/` anlegen falls nicht vorhanden
- Codebase explorieren um den aktuellen Zustand zu verstehen (für die Ist-Analyse)

### Schritt 1: Konzeptdokument

Vorlage aus [references/document-templates.md](references/document-templates.md) Abschnitt "Konzeptdokument" verwenden.

- Anforderung des Users in strukturierte Form bringen
- Problemstellung und Zielsetzung klar formulieren
- Lösungsidee skizzieren
- Betroffene Komponenten identifizieren (Codebase lesen!)
- Abgrenzung definieren — was ist NICHT Teil der Anforderung
- Offene Fragen auflisten und dem User stellen bevor fortgefahren wird

**Ausgabe:** `docs/01-konzept-<thema>.md`

Nach Erstellung dem User das Konzept zur Prüfung vorlegen. Erst nach Bestätigung weiter.

### Schritt 2: Ist-Analyse

Vorlage aus [references/document-templates.md](references/document-templates.md) Abschnitt "Ist-Analyse" verwenden.

- Codebase analysieren: relevante Dateien, Module, Abhängigkeiten identifizieren
- Aktuellen Zustand im Kontext der Anforderung dokumentieren
- Bestehende Abhängigkeiten auflisten (intern und extern)
- Einschränkungen und Risiken bei Änderung dokumentieren

**Ausgabe:** `docs/02-ist-analyse-<thema>.md`

Dem User zur Prüfung vorlegen.

### Schritt 3: Anforderungsanalyse

Vorlage aus [references/document-templates.md](references/document-templates.md) Abschnitt "Anforderungsanalyse" verwenden.

- Funktionale Anforderungen aus dem Konzept ableiten, mit Priorität (Muss/Soll/Kann)
- Nicht-funktionale Anforderungen identifizieren (Performance, Sicherheit, etc.)
- Akzeptanzkriterien definieren
- Abhängigkeiten zu anderen Anforderungen notieren

**Ausgabe:** `docs/03-anforderungsanalyse-<thema>.md`

Dem User zur Prüfung vorlegen.

### Schritt 4: Spezifikation

Vorlage aus [references/document-templates.md](references/document-templates.md) Abschnitt "Spezifikation" verwenden.

- Technisches Design basierend auf den vorherigen Dokumenten erstellen
- Architekturänderungen, Datenmodell, Schnittstellen beschreiben
- Implementierungsplan mit konkreten Änderungen pro Komponente
- Testplan erstellen
- Migrations-/Deployment-Schritte dokumentieren (falls zutreffend)
- Referenzen auf die vorherigen Dokumente setzen

**Ausgabe:** `docs/04-spezifikation-<thema>.md`

Dem User zur Prüfung vorlegen.

### Schritt 5: GitHub Issues erstellen

Richtlinien aus [references/github-issues.md](references/github-issues.md) verwenden.

Aus der Spezifikation Issues ableiten:

- **Issue-Größe:** Jedes Issue muss in einer einzelnen Session abarbeitbar sein. Aufteilen nach:
  - Eine Komponente/ein Modul pro Issue
  - Ein logischer Implementierungsschritt pro Issue
  - Frontend und Backend trennen
- **Referenzen:** Jedes Issue verweist auf die erstellten Dokumente unter `./docs/`
- **Akzeptanzkriterien:** Aus der Anforderungsanalyse übernehmen
- **Reihenfolge:** Issues in logischer Implementierungsreihenfolge anlegen

Issues mit `gh issue create` erstellen. Issue-Nummern dem User mitteilen.

## Sprache

Alle Dokumente und Issues werden auf Deutsch verfasst, es sei denn der User gibt eine andere Sprache vor.
