# Git-Befehlsreferenz

## Zweck

Dieser Bereich enthält eine kompakte Referenz der wichtigsten Git-Befehle für die tägliche Arbeit.

Die Befehle werden nicht isoliert betrachtet. Entscheidend ist das Verständnis des jeweiligen Repository-Zustands.

## Wichtigste Befehle

| Befehl | Zweck |
|---|---|
| `git init` | Neues lokales Git-Repository erstellen |
| `git status` | Aktuellen Repository-Zustand prüfen |
| `git add` | Änderungen für einen Commit vormerken |
| `git diff` | Änderungen vergleichen |
| `git commit` | Änderungen lokal als Commit speichern |
| `git pull` | Änderungen vom Remote abrufen und integrieren |
| `git push` | Lokale Commits zum Remote übertragen |
| `git clone` | Vorhandenes Repository lokal kopieren |
| `git log` | Commit-Historie anzeigen |
| `git branch` | Branches anzeigen und verwalten |
| `git remote` | Remote-Verbindungen anzeigen und verwalten |

## Standardablauf

```text
git pull
    ↓
Arbeiten
    ↓
git status
    ↓
git diff
    ↓
git add
    ↓
git diff --staged
    ↓
git commit
    ↓
git push
    ↓
git status
```

## Die wichtigsten fünf Befehle

### 1. `git status`

**Prüfen**

```powershell
git status
```

Frage:

> Was ist aktuell los?

### 2. `git add`

**Vorbereiten**

```powershell
git add .
```

Frage:

> Welche Änderungen sollen in den nächsten Commit?

### 3. `git commit`

**Lokal speichern**

```powershell
git commit -m "Beschreibung der Aenderung"
```

Frage:

> Welche Änderung soll als nachvollziehbarer Versionsstand gespeichert werden?

### 4. `git push`

**Übertragen**

```powershell
git push
```

Frage:

> Welche lokalen Commits sollen zum Remote übertragen werden?

### 5. `git pull`

**Aktualisieren**

```powershell
git pull
```

Frage:

> Welche Änderungen liegen auf GitHub und müssen in meinen aktuellen lokalen Branch integriert werden?

## Wichtige Grundregel

### Commit ist nicht Push

Ein Commit:

```text
Arbeitsverzeichnis
       ↓
    Staging
       ↓
     Commit
```

speichert eine Änderung zunächst **lokal**.

Erst:

```powershell
git push
```

überträgt den Commit zum Remote-Repository, beispielsweise zu GitHub.

## Weitere Referenzen

- [`git_init.md`](git_init.md)
- [`git_status.md`](git_status.md)
- [`git_add.md`](git_add.md)
- [`git_commit.md`](git_commit.md)
- [`git_pull.md`](git_pull.md)
- [`git_push.md`](git_push.md)
- [`git_clone.md`](git_clone.md)
- [`git_diff.md`](git_diff.md)
- [`git_log.md`](git_log.md)
- [`git_branch.md`](git_branch.md)
- [`git_remote.md`](git_remote.md)

## Merkhilfe

```text
status  → prüfen
add     → vorbereiten
commit  → lokal speichern
push    → übertragen
pull    → aktualisieren
```

Wer diese fünf Schritte versteht, beherrscht bereits den wichtigsten Teil der täglichen Git-Arbeit.
