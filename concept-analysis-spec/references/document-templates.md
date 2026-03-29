# Dokumentvorlagen

## Inhaltsverzeichnis

1. [Konzeptdokument](#konzeptdokument)
2. [Ist-Analyse](#ist-analyse)
3. [Anforderungsanalyse](#anforderungsanalyse)
4. [Spezifikation](#spezifikation)

---

## Konzeptdokument

Dateiname: `docs/01-konzept-<thema>.md`

```markdown
# Konzept: <Titel>

## 1. Zusammenfassung

Kurze Beschreibung der Anforderung in 2-3 Sätzen.

## 2. Problemstellung

Was ist das Problem oder der Bedarf, der adressiert werden soll?

## 3. Zielsetzung

- Welche Ziele sollen erreicht werden?
- Welche messbaren Ergebnisse werden angestrebt?

## 4. Lösungsidee

Grobe Beschreibung des Lösungsansatzes.

## 5. Betroffene Komponenten

Welche Teile des Systems / der Codebasis sind betroffen?

## 6. Abgrenzung

Was ist explizit NICHT Teil dieser Anforderung?

## 7. Offene Fragen

- Frage 1
- Frage 2
```

---

## Ist-Analyse

Dateiname: `docs/02-ist-analyse-<thema>.md`

```markdown
# Ist-Analyse: <Titel>

## 1. Aktueller Zustand

Beschreibung des aktuellen Systems/Verhaltens im Kontext der Anforderung.

## 2. Relevante Dateien und Komponenten

| Datei/Komponente | Beschreibung | Relevanz |
|---|---|---|
| `path/to/file` | Was macht diese Datei | Wie ist sie betroffen |

## 3. Bestehende Abhängigkeiten

- Interne Abhängigkeiten zwischen Modulen
- Externe Abhängigkeiten (Libraries, APIs, Services)

## 4. Bekannte Einschränkungen

- Technische Limitierungen
- Architektonische Constraints

## 5. Risiken bei Änderung

- Was könnte bei Änderungen brechen?
- Welche Seiteneffekte sind zu erwarten?
```

---

## Anforderungsanalyse

Dateiname: `docs/03-anforderungsanalyse-<thema>.md`

```markdown
# Anforderungsanalyse: <Titel>

## 1. Funktionale Anforderungen

| ID | Anforderung | Priorität | Beschreibung |
|---|---|---|---|
| FA-01 | ... | Muss | ... |
| FA-02 | ... | Soll | ... |
| FA-03 | ... | Kann | ... |

## 2. Nicht-funktionale Anforderungen

| ID | Anforderung | Kategorie | Beschreibung |
|---|---|---|---|
| NFA-01 | ... | Performance | ... |
| NFA-02 | ... | Sicherheit | ... |

## 3. Akzeptanzkriterien

- [ ] Kriterium 1
- [ ] Kriterium 2
- [ ] Kriterium 3

## 4. Abhängigkeiten zu anderen Anforderungen

- Referenz auf verwandte Anforderungen oder bestehende Issues

## 5. Priorisierung

Einordnung der Anforderungen nach Dringlichkeit und Wichtigkeit.
```

---

## Spezifikation

Dateiname: `docs/04-spezifikation-<thema>.md`

```markdown
# Spezifikation: <Titel>

## 1. Übersicht

Zusammenfassung der geplanten Implementierung basierend auf Konzept, Ist-Analyse und Anforderungsanalyse.

## 2. Technisches Design

### 2.1 Architektur

Beschreibung der Architekturänderungen oder -erweiterungen.

### 2.2 Datenmodell

Änderungen am Datenmodell (falls zutreffend).

### 2.3 Schnittstellen

Neue oder geänderte Schnittstellen (APIs, Events, etc.).

## 3. Implementierungsplan

### 3.1 Änderungen pro Komponente

| Komponente | Änderung | Aufwand |
|---|---|---|
| ... | ... | Klein/Mittel/Groß |

### 3.2 Reihenfolge der Implementierung

Nummerierte Liste der Implementierungsschritte in logischer Reihenfolge.

## 4. Testplan

- Unit Tests
- Integrationstests
- Manuelle Tests

## 5. Migration / Deployment

Schritte für Migration oder Deployment (falls zutreffend).

## 6. Referenzen

- [Konzeptdokument](01-konzept-<thema>.md)
- [Ist-Analyse](02-ist-analyse-<thema>.md)
- [Anforderungsanalyse](03-anforderungsanalyse-<thema>.md)
```
