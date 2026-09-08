# Arbeitsweise

## Zweck

Dieser Bereich beschreibt den empfohlenen lokalen Arbeitsablauf mit Git.

Das Ziel ist nicht das Auswendiglernen einzelner Befehle, sondern das sichere Verständnis des aktuellen Repository-Zustands.

## Standardablauf

```text
GitHub / Remote
      ↓
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

## Die vier wichtigen Zustände

```text
Arbeitsverzeichnis
       ↓ git add
Staging
       ↓ git commit
Lokales Repository
       ↓ git push
Remote Repository / GitHub
```

Diese Trennung ist zentral für das Verständnis von Git.

## Dokumente

| Thema | Dokument |
|---|---|
| Repository klonen | [Repository klonen](Repository_klonen.md) |
| Änderungen prüfen | [Änderungen prüfen](Aenderungen_pruefen.md) |
| Commit erstellen | [Commit erstellen](Commit_erstellen.md) |
| Repository synchronisieren | [Repository synchronisieren](Repository_synchronisieren.md) |

## Vor der Arbeit

Zunächst feststellen:

```powershell
Get-Location
git status
git branch --show-current
git remote -v
```

Damit werden die wichtigsten Fragen beantwortet:

- Wo bin ich?
- Welches Repository ist aktiv?
- Welcher Branch ist aktiv?
- Wohin zeigen Fetch und Push?

## Änderungen prüfen

Nach einer Änderung:

```powershell
git status
git diff
```

Vor dem Commit:

```powershell
git add .
git diff --staged
```

`git add .` kann neue Dateien, Änderungen und Löschungen vormerken. Deshalb sollte der Staging-Bereich anschließend geprüft werden.

## Commit

Ein Commit speichert den geprüften Stand zunächst lokal:

```powershell
git commit -m "Beschreibung der Aenderung"
```

Wichtig:

> **Commit ist nicht Push.**

Erst `git push` überträgt lokale Commits zum Remote-Repository.

## Synchronisieren

Wenn auf GitHub zwischenzeitlich Änderungen vorgenommen wurden:

```powershell
git pull
```

`git pull` ruft Änderungen vom Remote-Repository ab und integriert sie in den aktuellen lokalen Branch.

Bei Konflikten muss der Konflikt zunächst analysiert und gelöst werden.

## Empfohlene Grundregel

> **Pull → Arbeiten → Prüfen → Add → Commit → Push → Kontrolle**

Dieser Ablauf verhindert viele typische Fehler und macht Änderungen nachvollziehbar.
