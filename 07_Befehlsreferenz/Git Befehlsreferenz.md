# Git Befehlsreferenz

Diese Seite dient als Schnellreferenz für die wichtigsten Git-Befehle.

Die einzelnen Befehle werden in den jeweiligen Dokumenten ausführlicher erklärt.

## Übersicht

| Befehl | Zweck | Dokumentation |
|---|---|---|
| `git status` | Repository-Zustand prüfen | [git status](git_status.md) |
| `git add` | Änderungen vormerken | [git add](git_add.md) |
| `git commit` | Commit erstellen | [git commit](git_commit.md) |
| `git pull` | Änderungen von GitHub holen | [git pull](git_pull.md) |
| `git push` | Commits zu GitHub übertragen | [git push](git_push.md) |
| `git clone` | Repository lokal kopieren | [git clone](git_clone.md) |
| `git diff` | Änderungen anzeigen | [git diff](git_diff.md) |
| `git log` | Git-Historie anzeigen | [git log](git_log.md) |
| `git branch` | Branches verwalten | [git branch](git_branch.md) |
| `git remote` | Remote-Verbindungen verwalten | [git remote](git_remote.md) |

---

# Die wichtigsten Befehle

## 1. Zustand prüfen

```powershell
git status
```

Frage:

> Was ist aktuell in meinem Repository los?

---

## 2. Änderungen anzeigen

```powershell
git diff
```

Frage:

> Was habe ich geändert?

---

## 3. Änderungen vormerken

```powershell
git add .
```

Frage:

> Welche Änderungen sollen in den nächsten Commit?

---

## 4. Vorgemerkte Änderungen prüfen

```powershell
git diff --staged
```

Frage:

> Was wird tatsächlich committed?

---

## 5. Commit erstellen

```powershell
git commit -m "Beschreibung der Änderung"
```

Frage:

> Welche logisch zusammengehörende Änderung speichere ich jetzt in der Git-Historie?

---

## 6. Änderungen von GitHub holen

```powershell
git pull
```

Frage:

> Gibt es Änderungen auf GitHub, die ich lokal noch nicht habe?

---

## 7. Änderungen zu GitHub übertragen

```powershell
git push
```

Frage:

> Welche meiner lokalen Commits sollen zu GitHub übertragen werden?

---

## 8. Repository klonen

```powershell
git clone <Repository-URL>
```

Frage:

> Wie bekomme ich ein GitHub-Repository lokal?

---

## 9. Historie anzeigen

```powershell
git log --oneline -5
```

Frage:

> Welche Commits wurden zuletzt erstellt?

---

## 10. Branch prüfen

```powershell
git branch --show-current
```

Frage:

> Auf welchem Branch arbeite ich gerade?

---

## 11. Remote prüfen

```powershell
git remote -v
```

Frage:

> Mit welchem GitHub-Repository ist mein lokales Repository verbunden?

---

# Standardworkflow

Für die tägliche Arbeit reicht zunächst dieser Ablauf:

```powershell
git pull

# Dateien bearbeiten

git status
git diff

git add .
git diff --staged

git commit -m "Describe the change"

git push

git status
```

## Merkhilfe

```text
status  → prüfen
diff    → Änderungen ansehen
add     → vorbereiten
commit  → lokal speichern
push    → zu GitHub übertragen
pull    → von GitHub aktualisieren
```

> Wer diese sechs Schritte versteht, beherrscht bereits einen großen Teil des täglichen Git-Arbeitsablaufs.