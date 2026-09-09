# git push

## Zweck

`git push` überträgt lokale Commits in ein entferntes Repository, beispielsweise nach GitHub.

## Syntax

```powershell
git push
```

## Beispiel

Nach einem Commit:

```powershell
git commit -m "Update documentation"
git push
```

Der Commit wird anschließend auf GitHub verfügbar.

## Ablauf

```text
Datei ändern
    ↓
git add
    ↓
git commit
    ↓
lokales Repository
    ↓
git push
    ↓
GitHub
```

## Push-Ablehnung

Ein Push kann abgelehnt werden, wenn das Remote-Repository inzwischen Änderungen enthält, die lokal noch fehlen.

Typische Meldung:

```text
! [rejected] main -> main
```

In diesem Fall sollte zuerst die Ursache geprüft werden.

Nicht einfach mehrfach `git push` ausführen.

## Merksatz

> `git push` überträgt lokale Commits nach GitHub.