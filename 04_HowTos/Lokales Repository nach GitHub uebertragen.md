# Lokales Repository nach GitHub uebertragen

## 1. Ziel

Dieses HowTo beschreibt, wie ein bereits vorhandenes lokales Git-Repository in ein neues GitHub-Repository übertragen wird.

Der Vorgang eignet sich insbesondere für den Fall, dass:

- das Projekt bereits lokal vorhanden ist,
- Git lokal bereits eingerichtet wurde,
- die lokale Git-Historie erhalten bleiben soll,
- auf GitHub ein neues Repository bereitgestellt werden soll.

Ziel ist ein sauberer Zustand, bei dem das lokale Repository und das GitHub-Repository miteinander verbunden und synchronisiert sind.

---

## 2. Ausgangssituation

Beispiel:

```text
Lokaler Projektordner
D:\GitHub\Mein-Projekt
        │
        │ Git Repository
        │
        ▼
neues GitHub Repository
https://github.com/Benutzername/Mein-Projekt
```

Das lokale Repository enthält möglicherweise bereits:

- Dateien
- Verzeichnisse
- Commits
- Branches
- eine vorhandene Git-Historie

Das GitHub-Repository sollte für diesen Anwendungsfall möglichst **leer** angelegt werden.

### Empfohlene Ausgangssituation

```text
Lokal:
Git Repository vorhanden
Git-Historie vorhanden
        │
        │ push
        ▼
GitHub:
neues leeres Repository
```

Damit müssen nicht zwei voneinander unabhängige Historien zusammengeführt werden.

---

## 3. Voraussetzungen

Benötigt werden:

- ein vorhandenes lokales Projektverzeichnis
- Git
- ein GitHub-Account
- Berechtigung zum Schreiben in das Ziel-Repository
- Internetverbindung
- die URL des neuen GitHub-Repositories

Git kann beispielsweise in PowerShell geprüft werden:

```powershell
git --version
```

Beispiel:

```text
git version 2.x.x
```

---

## 4. Vorbereitung

### 4.1 In das lokale Repository wechseln

PowerShell öffnen und in das Projektverzeichnis wechseln:

```powershell
cd "D:\GitHub\Mein-Projekt"
```

Der konkrete Pfad hängt vom lokalen Speicherort des Projekts ab.

---

### 4.2 Repository prüfen

Zunächst den aktuellen Zustand prüfen:

```powershell
git status
```

Dabei ist insbesondere darauf zu achten:

- Befinden wir uns im richtigen Repository?
- Gibt es nicht gespeicherte Änderungen?
- Gibt es unversionierte Dateien?
- Welcher Branch ist aktiv?

Den aktuellen Branch anzeigen:

```powershell
git branch --show-current
```

Beispiel:

```text
main
```

---

### 4.3 Vorhandene Remote-Verbindungen prüfen

Anschließend:

```powershell
git remote -v
```

Es gibt zwei mögliche Situationen.

#### Fall A – Noch kein Remote vorhanden

Es wird nichts oder kein `origin` angezeigt.

Das ist für ein neues Ziel-Repository unproblematisch.

#### Fall B – Bereits ein Remote vorhanden

Beispiel:

```text
origin  https://github.com/AlterAccount/Mein-Projekt.git (fetch)
origin  https://github.com/AlterAccount/Mein-Projekt.git (push)
```

Dann muss zuerst geprüft werden, ob dieses Remote tatsächlich das gewünschte Ziel ist.

**Nicht einfach überschreiben, ohne die vorhandene Verbindung zu prüfen.**

---

## 5. GitHub Repository erstellen

Auf GitHub ein neues Repository erstellen.

Dabei:

1. Repository-Namen festlegen.
2. Besitzer beziehungsweise Account auswählen.
3. Sichtbarkeit festlegen.
4. Repository erstellen.

### Wichtig

Wenn bereits ein vollständiges lokales Repository mit eigener Git-Historie vorhanden ist, sollte das neue GitHub-Repository **nicht zusätzlich mit einer README, `.gitignore` oder Lizenz initialisiert werden**, sofern dies nicht bewusst erforderlich ist.

Der gewünschte Ausgangszustand ist:

```text
GitHub Repository
        │
        └── leer
```

Die vorhandene Historie kommt anschließend aus dem lokalen Repository.

---

## 6. GitHub Repository mit dem lokalen Repository verbinden

Nach der Erstellung die Repository-URL verwenden.

Beispiel:

```powershell
git remote add origin https://github.com/Benutzername/Mein-Projekt.git
```

Danach unbedingt prüfen:

```powershell
git remote -v
```

Erwartetes Ergebnis:

```text
origin  https://github.com/Benutzername/Mein-Projekt.git (fetch)
origin  https://github.com/Benutzername/Mein-Projekt.git (push)
```

### Warum diese Prüfung wichtig ist

`origin` ist lediglich der Name der Remote-Verbindung.

Entscheidend ist die dahinterliegende URL.

Vor dem ersten Push muss deshalb eindeutig feststehen:

> Wohin werden meine lokalen Commits übertragen?

---

## 7. Dateien und Git-Status prüfen

Vor dem ersten Push sollte nochmals geprüft werden:

```powershell
git status
```

Falls Änderungen oder neue Dateien vorhanden sind, müssen diese zunächst versioniert werden.

Beispiel:

```powershell
git add .
```

Danach:

```powershell
git status
```

Jetzt sollte erkennbar sein, welche Dateien für den Commit vorgemerkt wurden.

Optional kann die vorbereitete Änderung detailliert geprüft werden:

```powershell
git diff --staged
```

---

## 8. Ersten Commit erstellen

Wenn noch kein Commit für die vorhandenen Dateien existiert:

```powershell
git commit -m "Initial repository import"
```

Danach:

```powershell
git status
```

Ein sauberer Zustand sieht beispielsweise so aus:

```text
nothing to commit, working tree clean
```

### Wichtig

Ein Commit befindet sich zunächst **nur lokal**.

Bis zu diesem Zeitpunkt wurde noch nichts zu GitHub übertragen.

---

## 9. Branch prüfen

Vor dem Push prüfen:

```powershell
git branch --show-current
```

Wenn der gewünschte Hauptbranch `main` heißt:

```text
main
```

Falls der lokale Branch beispielsweise `master` heißt, sollte vor dem Push bewusst entschieden werden, welcher Branch verwendet werden soll.

Ein mögliches Umbenennen nach `main` wäre:

```powershell
git branch -M main
```

Danach erneut prüfen:

```powershell
git branch --show-current
```

---

## 10. Repository nach GitHub übertragen

Wenn:

- das richtige lokale Repository geöffnet ist,
- der richtige Branch aktiv ist,
- das richtige Remote konfiguriert ist,
- die Dateien geprüft wurden,
- die Commits vorhanden sind,

kann der erste Push durchgeführt werden:

```powershell
git push -u origin main
```

### Bedeutung

```text
git
    └── push
          ├── origin
          │     └── Ziel-Repository
          └── main
                └── zu übertragender Branch
```

Die Option:

```text
-u
```

legt die Upstream-Beziehung zwischen dem lokalen Branch und dem Remote-Branch fest.

Dadurch können spätere Pushes meist einfacher mit:

```powershell
git push
```

durchgeführt werden.

---

## 11. Übertragung kontrollieren

Nach dem Push:

```powershell
git status
```

Danach das Repository auf GitHub öffnen.

Prüfen:

- Sind die Dateien vorhanden?
- Ist die erwartete Verzeichnisstruktur vorhanden?
- Ist der richtige Branch aktiv?
- Sind die Commit-Historie und die Commit-Nachrichten vorhanden?
- Ist der aktuelle Stand vollständig?

Zusätzlich kann lokal geprüft werden:

```powershell
git log --oneline -5
```

Damit lässt sich die lokale Historie mit der auf GitHub vergleichen.

---

## 12. Erfolgreicher Endzustand

Der gewünschte Zustand sieht folgendermaßen aus:

```text
                 Git
                  │
        ┌─────────┴─────────┐
        │                   │
        ▼                   ▼
lokales Repository      GitHub Repository
        │                   │
        │       push        │
        └──────────────────►│
                            │
                         synchron
```

Lokal:

```text
main
origin → GitHub Repository
working tree clean
```

Auf GitHub:

```text
main
Dateien vorhanden
Git-Historie vorhanden
```

Damit ist die erstmalige Bereitstellung abgeschlossen.

---

# 13. Variante: GitHub Repository enthält bereits Dateien

Besondere Vorsicht ist erforderlich, wenn das GitHub-Repository bereits initialisiert wurde.

Beispielsweise:

```text
Lokal:
Commit A
Commit B
Commit C

GitHub:
Commit X
```

Dann existieren zwei unterschiedliche Historien.

Ein einfaches:

```powershell
git push
```

kann in diesem Fall abgelehnt werden.

Typischerweise erscheint eine Meldung, dass der Remote-Stand weiter fortgeschritten ist.

### Nicht sofort verwenden

```powershell
git push --force
```

Ein Force Push kann vorhandene Commits auf dem Remote verändern oder entfernen.

Stattdessen sollte zunächst geklärt werden:

- Welche Historie ist die richtige?
- Welche Dateien befinden sich bereits auf GitHub?
- Muss die Historie zusammengeführt werden?
- Kann das GitHub-Repository neu und leer erstellt werden?

Für diesen Fall sollte die Anleitung [Push abgelehnt](../../08_Troubleshooting/Push_abgelehnt.md) herangezogen werden.

---

# 14. Typische Fehler

## Falsches Repository

Prüfen:

```powershell
git remote -v
```

und:

```powershell
git status
```

Der lokale Pfad sollte ebenfalls kontrolliert werden:

```powershell
Get-Location
```

---

## Falscher Branch

Prüfen:

```powershell
git branch --show-current
```

---

## Falsches Remote

Prüfen:

```powershell
git remote -v
```

Ein Remote kann beispielsweise korrigiert werden mit:

```powershell
git remote set-url origin https://github.com/Benutzername/Mein-Projekt.git
```

Danach erneut:

```powershell
git remote -v
```

---

## Nothing to commit

```text
nothing to commit, working tree clean
```

ist kein Fehler.

Es bedeutet lediglich, dass aktuell keine nicht gespeicherten Änderungen vorhanden sind.

Siehe:

[Nothing to commit](../../08_Troubleshooting/Nothing_to_commit.md)

---

## Push abgelehnt

Wenn GitHub bereits Änderungen enthält, kann der Push abgelehnt werden.

Nicht blind mit `--force` arbeiten.

Siehe:

[Push abgelehnt](../../08_Troubleshooting/Push_abgelehnt.md)

---

# 15. Sicherheitsprüfung

Vor dem ersten Push muss geprüft werden, dass keine vertraulichen Daten übertragen werden.

Insbesondere dürfen nicht versehentlich enthalten sein:

- Passwörter
- Personal Access Tokens
- API Keys
- private Schlüssel
- Zugangsdaten
- vertrauliche Konfigurationsdateien
- personenbezogene Daten
- Produktionsdaten

Vor dem Push:

```powershell
git status
```

und gegebenenfalls:

```powershell
git diff --staged
```

prüfen.

**Ein einmal auf GitHub veröffentlichter Schlüssel darf nicht einfach durch spätere Löschung als sicher betrachtet werden.**

Siehe:

[Was nicht in GitHub gehoert](../../09_Sicherheit/Was_nicht_in_GitHub_gehoert.md)

---

# 16. Kurzfassung

Für ein vorhandenes lokales Repository und ein neues, leeres GitHub-Repository:

```powershell
cd "D:\GitHub\Mein-Projekt"

git status
git branch --show-current
git remote -v

git remote add origin https://github.com/Benutzername/Mein-Projekt.git

git status
git add .
git status
git diff --staged

git commit -m "Initial repository import"

git branch --show-current

git push -u origin main

git status
```

Danach das Repository auf GitHub kontrollieren.

---

# 17. Merksatz

Der Vorgang lässt sich auf sieben Schritte reduzieren:

```text
Prüfen
   ↓
GitHub Repository erstellen
   ↓
Remote verbinden
   ↓
Dateien prüfen
   ↓
Commit erstellen
   ↓
Push durchführen
   ↓
Ergebnis kontrollieren
```

Oder kurz:

> **Prüfen → Verbinden → Commit → Push → Kontrollieren**

Damit ist ein lokales Git-Repository sauber an GitHub angebunden und erstmalig übertragen.