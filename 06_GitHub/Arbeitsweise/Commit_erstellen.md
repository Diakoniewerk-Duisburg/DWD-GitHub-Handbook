# Commit erstellen

## 1. Zweck

Ein Commit speichert vorbereitete Änderungen in der lokalen Git-Versionshistorie.

Der Commit ist ein zentraler Bestandteil der Git-Arbeitsweise.

Wichtig:

> Ein Commit befindet sich zunächst nur im lokalen Repository. Erst durch `git push` wird er zu GitHub übertragen.

## 2. Voraussetzungen

Vor dem Commit sollte geprüft werden:

```powershell
git status
```

und:

```powershell
git diff
```

Die Änderungen müssen bewusst ausgewählt und geprüft worden sein.

## 3. Änderungen stagen

Eine einzelne Datei:

```powershell
git add README.md
```

Mehrere bestimmte Dateien:

```powershell
git add README.md Dokumentation.md
```

Alle Änderungen:

```powershell
git add .
```

### Empfehlung

`git add .` ist bequem, sollte aber nicht blind verwendet werden.

Vorher:

```powershell
git status
```

prüfen.

## 4. Gestagte Änderungen prüfen

Nach dem Staging:

```powershell
git diff --staged
```

Damit wird kontrolliert, welche Änderungen tatsächlich in den Commit aufgenommen werden.

## 5. Commit erstellen

Der Commit wird mit einer Commit-Nachricht erstellt:

```powershell
git commit -m "Update documentation"
```

Die Commit-Nachricht sollte kurz und eindeutig beschreiben, was geändert wurde.

## 6. Gute Commit-Nachrichten

Beispiele:

```text
Add GitHub online guide
```

```text
Update repository documentation
```

```text
Fix documentation links
```

```text
Add troubleshooting guide
```

Eine Commit-Nachricht sollte nicht lediglich lauten:

```text
Update
```

oder:

```text
Änderung
```

weil daraus später nicht mehr eindeutig hervorgeht, was geändert wurde.

## 7. Commit kontrollieren

Nach dem Commit:

```powershell
git status
```

ausführen.

Zusätzlich kann die Historie geprüft werden:

```powershell
git log --oneline -5
```

Damit werden beispielsweise die letzten fünf Commits angezeigt.

## 8. Commit ist noch nicht auf GitHub

Nach:

```powershell
git commit
```

ist die Änderung nur lokal gespeichert.

Der Ablauf ist:

```text
Datei
  ↓
git add
  ↓
Staging Area
  ↓
git commit
  ↓
Lokale Git-Historie
  ↓
git push
  ↓
GitHub
```

## 9. Commit ändern

Wenn unmittelbar nach dem Commit ein Fehler festgestellt wird, kann der letzte Commit unter bestimmten Umständen noch korrigiert werden.

Beispielsweise:

```powershell
git commit --amend
```

Dieser Befehl sollte jedoch nicht leichtfertig für bereits veröffentlichte Commits verwendet werden.

Insbesondere bei Commits, die bereits nach GitHub übertragen wurden, gelten zusätzliche Regeln.

## 10. Mehrere Commits

Mehrere logisch getrennte Änderungen sollten möglichst auch in getrennten Commits gespeichert werden.

Beispiel:

```text
Commit 1:
Add GitHub online documentation

Commit 2:
Fix documentation links

Commit 3:
Add troubleshooting guide
```

Das verbessert die Nachvollziehbarkeit.

## 11. Grundregel

> Erst prüfen, dann stagen, dann Commit erstellen.

Empfohlener Ablauf:

```powershell
git status
git diff
git add .
git diff --staged
git commit -m "Beschreibung der Änderung"
git status
```