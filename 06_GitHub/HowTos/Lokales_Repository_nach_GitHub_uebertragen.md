# Lokales Repository nach GitHub uebertragen

## Ziel

Dieses HowTo beschreibt, wie ein bereits vorhandenes lokales Git-Repository in ein neues GitHub-Repository übertragen wird.

## Ausgangssituation

Das lokale Projekt enthält bereits:

- Dateien und Verzeichnisse
- ein Git-Repository
- gegebenenfalls mehrere Commits
- einen lokalen Branch

Auf GitHub soll ein neues Repository als Ziel bereitgestellt werden.

Für diesen Anwendungsfall sollte das GitHub-Repository möglichst leer angelegt werden.

## Voraussetzungen

- lokales Git-Repository
- installierte Git-Version
- GitHub-Account
- Schreibberechtigung für das Ziel-Repository
- URL des GitHub-Repositories

Git prüfen:

```powershell
git --version
```

## 1. Lokales Repository öffnen

```powershell
cd "D:\GitHub\Mein-Projekt"
```

Prüfen:

```powershell
Get-Location
git status
git branch --show-current
git remote -v
```

Damit wird vor dem ersten Push geklärt:

- Wo befinden wir uns?
- Welches Repository ist aktiv?
- Welcher Branch ist aktiv?
- Ist bereits ein Remote vorhanden?

## 2. GitHub Repository erstellen

Ein neues Repository auf GitHub erstellen.

Wenn lokal bereits eine vollständige Git-Historie vorhanden ist, sollte das GitHub-Repository möglichst nicht zusätzlich mit README, `.gitignore` oder Lizenz initialisiert werden.

Ziel:

```text
Lokales Repository        GitHub
mit Historie       →      neues leeres Repository
```

## 3. Remote verbinden

Wenn noch kein Remote vorhanden ist:

```powershell
git remote add origin https://github.com/Benutzername/Mein-Projekt.git
```

Danach unbedingt prüfen:

```powershell
git remote -v
```

`origin` ist nur der Name der Remote-Verbindung. Entscheidend ist die dahinterliegende URL.

## 4. Dateien und Änderungen prüfen

```powershell
git status
git diff
```

Wenn Dateien noch nicht versioniert sind:

```powershell
git add .
```

Danach:

```powershell
git diff --staged
git status
```

Vor dem Commit muss geprüft werden, dass nur die gewünschten Dateien enthalten sind und keine vertraulichen Daten übertragen werden.

## 5. Ersten Commit erstellen

Wenn noch kein Commit für den aktuellen Projektstand existiert:

```powershell
git commit -m "Initial repository import"
```

Danach:

```powershell
git status
```

Ein Commit befindet sich zunächst nur lokal.

## 6. Hauptbranch prüfen

```powershell
git branch --show-current
```

Wenn der Hauptbranch `main` sein soll und der lokale Branch anders heißt:

```powershell
git branch -M main
```

Danach erneut prüfen:

```powershell
git branch --show-current
```

## 7. Nach GitHub übertragen

Wenn Repository, Branch, Remote und Commit geprüft wurden:

```powershell
git push -u origin main
```

Die Option `-u` legt die Upstream-Beziehung zwischen lokalem Branch und Remote-Branch fest.

Spätere Pushes können dann meist einfach mit:

```powershell
git push
```

erfolgen.

## 8. Ergebnis kontrollieren

Nach dem Push:

```powershell
git status
git log --oneline -5
git remote -v
```

Anschließend das Repository auf GitHub öffnen und prüfen:

- Dateien vorhanden
- Verzeichnisstruktur korrekt
- Branch korrekt
- Commit-Historie vorhanden
- Commit-Nachrichten nachvollziehbar

## Variante: GitHub enthält bereits Commits

Wenn GitHub bereits separat initialisiert wurde, können zwei voneinander unabhängige Historien existieren.

Beispiel:

```text
Lokal:   A → B → C
GitHub:  X
```

Ein Push kann dann abgelehnt werden.

Nicht sofort verwenden:

```powershell
git push --force
```

Stattdessen zunächst den Zustand analysieren und gegebenenfalls die Anleitung [Push abgelehnt](../08_Troubleshooting/Push_abgelehnt.md) verwenden.

## Sicherheitsprüfung

Vor dem Push dürfen insbesondere nicht enthalten sein:

- Passwörter
- Personal Access Tokens
- API Keys
- private Schlüssel
- Zugangsdaten
- vertrauliche Konfiguration
- personenbezogene Daten
- Produktionsdaten

Vor dem Push:

```powershell
git status
git diff --staged
```

prüfen.

## Erfolgreicher Endzustand

```text
Lokales Repository
      │
      │ git push
      ▼
GitHub Repository
```

Lokal ist der Arbeitsstand sauber und das Remote zeigt den erwarteten Branch und die erwartete Historie.

## Kurzfassung

```powershell
cd "D:\GitHub\Mein-Projekt"
git status
git branch --show-current
git remote -v
git remote add origin https://github.com/Benutzername/Mein-Projekt.git
git add .
git diff --staged
git commit -m "Initial repository import"
git branch -M main
git push -u origin main
git status
```
