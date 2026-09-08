# git diff

## Zweck

`git diff` zeigt Änderungen zwischen verschiedenen Zuständen eines Git-Repositorys.

Der Befehl ist besonders wichtig, um vor einem Commit zu kontrollieren, was tatsächlich geändert wurde.

## Nicht gestagte Änderungen anzeigen

```powershell
git diff
```

Zeigt Änderungen, die im Working Tree vorhanden sind, aber noch nicht mit `git add` vorgemerkt wurden.

## Gestagte Änderungen anzeigen

```powershell
git diff --staged
```

Zeigt Änderungen, die bereits für den nächsten Commit vorgemerkt wurden.

## Typischer Prüfablauf

```powershell
git status
git diff
git add .
git diff --staged
```

Damit können sowohl die vorhandenen als auch die für den Commit vorgesehenen Änderungen geprüft werden.

## Beispiel

```text
Datei vor Änderung
       │
       ▼
Datei bearbeiten
       │
       ▼
git diff
       │
       ▼
Änderung prüfen
       │
       ▼
git add
       │
       ▼
git diff --staged
       │
       ▼
Commit
```

## Warum ist `git diff` wichtig?

Ein Commit sollte möglichst nur die Änderungen enthalten, die tatsächlich beabsichtigt sind.

`git diff` hilft dabei, versehentliche Änderungen frühzeitig zu erkennen.

## Merksatz

> `git diff` zeigt, was sich geändert hat.