# git commit

## Zweck

`git commit` speichert die aktuell gestagten Änderungen in der lokalen Git-Historie.

## Syntax

```powershell
git commit -m "Commit message"
```

## Beispiel

```powershell
git commit -m "Update GitHub documentation"
```

## Vor dem Commit

Empfohlene Prüfung:

```powershell
git status
git diff --staged
```

## Nach dem Commit

```powershell
git status
```

Die Änderung befindet sich anschließend in der lokalen Git-Historie.

## Wichtig

Ein Commit wird nicht automatisch nach GitHub übertragen.

Dafür ist anschließend erforderlich:

```powershell
git push
```

## Ablauf

```text
git add
   ↓
git commit
   ↓
lokale Git-Historie
   ↓
git push
   ↓
GitHub
```

## Merksatz

> `git commit` speichert Änderungen lokal in der Git-Historie.