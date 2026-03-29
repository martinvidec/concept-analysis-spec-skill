# Concept Analysis Spec Skill

Ein Claude Code Skill zur strukturierten Analyse und Spezifikation neuer Anforderungen. Der Skill erstellt sequenziell:

1. **Konzeptdokument** - Anforderung strukturieren, Problemstellung, Lösungsidee
2. **Ist-Analyse** - Aktuellen Zustand der Codebase dokumentieren
3. **Anforderungsanalyse** - Funktionale/nicht-funktionale Anforderungen, Akzeptanzkriterien
4. **Spezifikation** - Technisches Design und Implementierungsplan
5. **GitHub Issues** - Aufgeteilt in session-große Einheiten via `gh`

Alle Dokumente werden unter `./docs/` abgelegt. Jeder Schritt wird zur Prüfung vorgelegt bevor es weitergeht.

## Installation

### Voraussetzungen

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installiert
- [GitHub CLI (`gh`)](https://cli.github.com/) installiert und authentifiziert

### Skill installieren

```bash
claude install-skill https://github.com/martinvidec/concept-analysis-spec-skill
```

### Verwendung

Den Skill in einem beliebigen Projekt-Verzeichnis mit Claude Code verwenden. Einfach eine neue Anforderung beschreiben, z.B.:

```
Wir brauchen eine Caching-Schicht für unsere API-Aufrufe um die Ladezeiten zu reduzieren.
```

Der Skill wird automatisch getriggert und führt durch den gesamten Analyse- und Spezifikationsprozess.

## Struktur

```
concept-analysis-spec/
├── SKILL.md                      # Workflow und Skill-Definition
└── references/
    ├── document-templates.md     # Vorlagen für alle 4 Dokumente
    └── github-issues.md          # Richtlinien für Issue-Erstellung
```

## Lizenz

MIT
