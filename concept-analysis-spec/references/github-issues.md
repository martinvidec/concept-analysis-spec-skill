# GitHub Issues Erstellung

## Grundsätze

- Jedes Issue muss in einer einzelnen Session abarbeitbar sein
- Issues referenzieren die erstellten Dokumente unter `./docs/`
- Issues werden mit `gh issue create` angelegt
- Verwende Labels falls im Repository vorhanden

## Issue-Größe bestimmen

Ein Issue ist zu groß, wenn es mehrere unabhängige Änderungen umfasst. Aufteilen nach:

- **Eine Komponente / ein Modul pro Issue** — Änderungen an verschiedenen Modulen in separate Issues
- **Ein logischer Schritt pro Issue** — z.B. "Datenmodell anlegen" und "API-Endpunkt implementieren" trennen
- **Frontend und Backend trennen** — wenn beides betroffen ist
- **Tests als eigenes Issue** — nur wenn der Testumfang groß ist, sonst zum Implementierungs-Issue

## Issue-Vorlage

```
Titel: <Kurze, prägnante Beschreibung der Aufgabe>

## Kontext

Basierend auf:
- [Konzept](docs/01-konzept-<thema>.md)
- [Ist-Analyse](docs/02-ist-analyse-<thema>.md)
- [Anforderungsanalyse](docs/03-anforderungsanalyse-<thema>.md)
- [Spezifikation](docs/04-spezifikation-<thema>.md)

## Aufgabe

Beschreibung was in diesem Issue zu tun ist.

## Akzeptanzkriterien

- [ ] Kriterium 1
- [ ] Kriterium 2

## Betroffene Dateien

- `path/to/file1`
- `path/to/file2`
```

## gh Befehle

Einzelnes Issue erstellen:

```bash
gh issue create --title "<titel>" --body "<body>"
```

Mit Labels:

```bash
gh issue create --title "<titel>" --body "<body>" --label "enhancement"
```

Mehrere Issues erstellen: Jedes Issue einzeln mit `gh issue create` anlegen. Die Issue-Nummern in der Ausgabe notieren und dem User mitteilen.
