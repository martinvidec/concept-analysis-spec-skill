# Concept Analysis Spec Skill

Ein Claude Code Skill zur strukturierten Analyse und Spezifikation neuer Anforderungen. Der Skill erstellt sequenziell:

1. **Konzeptdokument** – Anforderung strukturieren, Problemstellung, Lösungsidee
2. **Ist-Analyse** – Aktuellen Zustand der Codebase dokumentieren
3. **Anforderungsanalyse** – Funktionale/nicht-funktionale Anforderungen, Akzeptanzkriterien
4. **Spezifikation** – Technisches Design und Implementierungsplan
5. **GitHub Issues** – Aufgeteilt in session-große Einheiten via `gh`

Alle Dokumente werden unter `./docs/` abgelegt. Jeder Schritt wird zur Prüfung vorgelegt, bevor es weitergeht.

## Voraussetzungen

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installiert
- [GitHub CLI (`gh`)](https://cli.github.com/) installiert und authentifiziert (wird in Schritt 5 für die Issue-Erstellung verwendet)

## Installation

Claude Code lädt Skills automatisch aus zwei Verzeichnissen:

- `~/.claude/skills/<skill-name>/` – global verfügbar in allen Projekten
- `<projekt>/.claude/skills/<skill-name>/` – nur für ein bestimmtes Projekt

Wichtig ist, dass das **Skill-Verzeichnis selbst** (`concept-analysis-spec/` mit `SKILL.md` darin) im `skills/`-Ordner liegt – nicht das Repo-Wurzelverzeichnis.

### Option A: Global installieren (empfohlen)

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/martinvidec/concept-analysis-spec-skill.git /tmp/concept-analysis-spec-skill
cp -r /tmp/concept-analysis-spec-skill/concept-analysis-spec ~/.claude/skills/
rm -rf /tmp/concept-analysis-spec-skill
```

### Option B: Projekt-lokal installieren

Im Wurzelverzeichnis des Zielprojekts ausführen:

```bash
mkdir -p .claude/skills
git clone https://github.com/martinvidec/concept-analysis-spec-skill.git /tmp/concept-analysis-spec-skill
cp -r /tmp/concept-analysis-spec-skill/concept-analysis-spec .claude/skills/
rm -rf /tmp/concept-analysis-spec-skill
```

### Option C: Per Symlink (für Mitentwicklung am Skill)

Wer den Skill weiterentwickeln möchte, kann statt `cp` einen Symlink anlegen, sodass Änderungen am geklonten Repo sofort wirksam werden:

```bash
git clone https://github.com/martinvidec/concept-analysis-spec-skill.git ~/code/concept-analysis-spec-skill
mkdir -p ~/.claude/skills
ln -s ~/code/concept-analysis-spec-skill/concept-analysis-spec ~/.claude/skills/concept-analysis-spec
```

### Installation prüfen

Nach dem Start einer neuen Claude-Code-Session sollte der Skill verfügbar sein. Eine kurze Prüfung:

```bash
ls ~/.claude/skills/concept-analysis-spec/SKILL.md
```

Existiert die Datei, ist der Skill korrekt installiert und wird von Claude Code automatisch geladen.

## Verwendung

Den Skill in einem beliebigen Projekt-Verzeichnis mit Claude Code verwenden. Einfach eine neue Anforderung beschreiben, z.B.:

```
Wir brauchen eine Caching-Schicht für unsere API-Aufrufe um die Ladezeiten zu reduzieren.
```

Claude erkennt anhand der `description` in `SKILL.md` automatisch, dass dieser Skill passt, und führt durch den gesamten Analyse- und Spezifikationsprozess.

## Struktur

```
concept-analysis-spec/
├── SKILL.md                      # Workflow und Skill-Definition
└── references/
    ├── document-templates.md     # Vorlagen für alle 4 Dokumente
    └── github-issues.md          # Richtlinien für Issue-Erstellung
```

## Update

Wer per `git clone` (Option A/B) installiert hat, aktualisiert über erneutes Clonen und Kopieren. Bei Option C (Symlink) genügt ein `git pull` im Repo.

## Deinstallation

```bash
rm -rf ~/.claude/skills/concept-analysis-spec
```

(bzw. analog `.claude/skills/concept-analysis-spec` bei projekt-lokaler Installation)

## Lizenz

MIT
