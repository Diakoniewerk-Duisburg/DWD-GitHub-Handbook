# Lernpfad

Dieser Bereich führt Schritt für Schritt durch einen vollständigen Git- und GitHub-Arbeitsablauf.

## Ziel

Nach Abschluss soll verständlich sein:

- was Git und GitHub sind,
- wie ein Repository lokal und online funktioniert,
- wie Änderungen geprüft werden,
- was `git add`, `git commit`, `git push` und `git pull` bewirken,
- wie lokale und Online-Änderungen zusammenarbeiten,
- wie typische Probleme erkannt und kontrolliert werden.

## Lernreihenfolge

### 1. Grundlagen

- [Was ist Git?](../01_Grundlagen/Was_ist_Git.md)
- [Was ist GitHub?](../01_Grundlagen/Was_ist_GitHub.md)
- [Unterschied Git und GitHub](../01_Grundlagen/Unterschied_Git_und_GitHub.md)

### 2. GitHub Repository anlegen

- [GitHub Repository anlegen](../04_HowTos/GitHub_Repository_anlegen.md)

### 3. Lokal arbeiten

- [Repository klonen](../03_Arbeitsweise/Repository_klonen.md)
- [Änderungen prüfen](../03_Arbeitsweise/Aenderungen_pruefen.md)
- [Commit erstellen](../03_Arbeitsweise/Commit_erstellen.md)
- [Repository synchronisieren](../03_Arbeitsweise/Repository_synchronisieren.md)

### 4. Direkt auf GitHub arbeiten

- [Dateien bearbeiten](../02_GitHub_Online/Dateien_bearbeiten.md)
- [Online committen](../02_GitHub_Online/Commit_online.md)
- [Änderungen vergleichen](../02_GitHub_Online/Aenderungen_vergleichen.md)

### 5. Synchronisation verstehen

Der zentrale Ablauf:

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
GitHub / Remote
```

### 6. Probleme verstehen

- [Repository-Stand prüfen](../05_Praxisbeispiele/Praxisbeispiel%20%E2%80%93%20Repository-Stand%20prüfen.md)
- [Push abgelehnt](../05_Praxisbeispiele/Praxisbeispiel%20%E2%80%93%20Push%20abgelehnt.md)
- [Merge Conflict](../08_Troubleshooting/Merge_Conflict.md)

### 7. Sicherheit

- [Sicherheitsübersicht](../09_Sicherheit/README.md)
- [Was gehört nicht in GitHub?](../09_Sicherheit/Was_nicht_in_GitHub_gehoert.md)

## Praktisches Gesamttutorial

[Git und GitHub von Anfang bis Ende](01_Git_und_GitHub_von_Anfang_bis_Ende.md)

Das Tutorial führt einmal vollständig durch einen typischen lokalen und Online-Arbeitsablauf.

## Die fünf wichtigsten Fragen

Bei jeder Git-Aktion sollte klar sein:

### Wo bin ich?

```powershell
Get-Location
```

### In welchem Repository bin ich?

```powershell
git remote -v
```

### Auf welchem Branch bin ich?

```powershell
git branch --show-current
```

### Was hat sich geändert?

```powershell
git status
git diff
```

### Wohin geht die Änderung?

```powershell
git remote -v
```

## Lernziel

Das Ziel ist nicht das Auswendiglernen möglichst vieler Befehle.

> **Das Ziel ist, den Zustand des Repositorys jederzeit verstehen und kontrollieren zu können.**
