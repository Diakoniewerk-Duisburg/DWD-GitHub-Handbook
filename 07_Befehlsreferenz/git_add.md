# git add

## Zweck

`git add` nimmt Änderungen in die Staging Area auf.

Damit wird festgelegt, welche Änderungen beim nächsten Commit berücksichtigt werden.

## Einzelne Datei

```powershell
git add README.md
```

## Mehrere Dateien

```powershell
git add README.md Dokumentation.md
```

## Alle Änderungen

```powershell
git add .
```

## Kontrolle

Nach `git add` sollte geprüft werden:

```powershell
git status
```

Für eine detaillierte Kontrolle:

```powershell
git diff --staged
```

## Wichtig

`git add` erstellt noch keinen Commit.

Der Ablauf lautet:

```text
Änderung
   ↓
git add
   ↓
Staging Area
   ↓
git commit
```

## Merksatz

> `git add` bestimmt, welche Änderungen in den nächsten Commit aufgenommen werden.