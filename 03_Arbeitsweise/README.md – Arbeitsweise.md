# Arbeiten mit Git und GitHub

## 1. Zweck

Dieser Bereich beschreibt den praktischen Standardablauf bei der Arbeit mit lokalen Git-Repositorys und GitHub.

Der Schwerpunkt liegt auf der Arbeit unter Windows mit PowerShell.

## 2. Grundprinzip

Bei der lokalen Arbeit existieren grundsätzlich zwei Repository-Stände:

```text
Lokales Repository
        │
        │ git push
        ▼
GitHub Repository
        │
        │ git pull
        ▼
Lokales Repository
```

Änderungen werden zunächst lokal durchgeführt und anschließend mit GitHub synchronisiert.

## 3. Standard-Arbeitsablauf

Der typische Ablauf lautet:

```text
Repository aktualisieren
        │
        ▼
Änderungen durchführen
        │
        ▼
Änderungen prüfen
        │
        ▼
Änderungen stagen
        │
        ▼
Commit erstellen
        │
        ▼
Repository synchronisieren
        │
        ▼
Push nach GitHub
```

## 4. Repository aktualisieren

Vor Beginn der Arbeit sollte geprüft werden, ob das lokale Repository aktuell ist.

Typischerweise:

```powershell
git status
git pull
```

Dadurch wird verhindert, dass auf einem veralteten lokalen Stand gearbeitet wird.

## 5. Änderungen durchführen

Die Dateien werden lokal mit dem geeigneten Editor bearbeitet.

Beispielsweise:

```text
D:\GitHub\DWD-GitHub-Handbook\
```

Während der Bearbeitung kann Git die Änderungen erkennen.

## 6. Änderungen prüfen

Nach der Bearbeitung:

```powershell
git status
```

zeigt, welche Dateien geändert wurden.

Mit:

```powershell
git diff
```

können die tatsächlichen Änderungen betrachtet werden.

## 7. Änderungen stagen

Die gewünschten Änderungen werden für den nächsten Commit vorbereitet.

Beispiel:

```powershell
git add README.md
```

oder mehrere Änderungen:

```powershell
git add .
```

Vor der Verwendung von `git add .` sollte geprüft werden, ob tatsächlich alle angezeigten Änderungen zum Commit gehören.

## 8. Commit erstellen

Die vorbereiteten Änderungen werden mit einem Commit gespeichert:

```powershell
git commit -m "Update documentation"
```

Der Commit wird zunächst nur im lokalen Repository gespeichert.

## 9. Push nach GitHub

Anschließend wird der Commit nach GitHub übertragen:

```powershell
git push
```

Danach enthält das GitHub-Repository den neuen Commit.

## 10. Abschlusskontrolle

Nach dem Push:

```powershell
git status
```

ausführen.

Ein sauberer Zustand sollte ungefähr bedeuten:

```text
nothing to commit, working tree clean
```

Damit ist die lokale Arbeitskopie hinsichtlich der nicht committeten Änderungen sauber.

## 11. Wichtiger Unterschied

`git commit` und `git push` sind zwei unterschiedliche Vorgänge.

### Commit

```text
Änderung
   ↓
lokale Git-Historie
```

### Push

```text
lokale Git-Historie
   ↓
GitHub
```

Ein Commit bedeutet daher nicht automatisch, dass die Änderung bereits auf GitHub vorhanden ist.

## 12. Pull und Push

### Pull

```powershell
git pull
```

holt Änderungen von GitHub in das lokale Repository.

### Push

```powershell
git push
```

überträgt lokale Commits nach GitHub.

## 13. Empfohlener Standard

Für einfache Arbeiten:

```powershell
git pull
git status
```

Arbeiten durchführen.

Danach:

```powershell
git status
git diff
git add .
git commit -m "Update documentation"
git push
git status
```

## 14. Grundregel

> Vor der Arbeit aktualisieren. Vor dem Commit prüfen. Nach dem Commit pushen. Nach dem Push den Zustand kontrollieren.

## 15. Weiterführende Dokumentation

Die einzelnen Schritte werden in separaten Dokumenten detailliert beschrieben:

- `Repository_klonen.md`
- `Aenderungen_pruefen.md`
- `Commit_erstellen.md`
- `Repository_synchronisieren.md`