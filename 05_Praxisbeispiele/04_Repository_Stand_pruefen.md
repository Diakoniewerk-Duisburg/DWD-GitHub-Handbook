# Praxisbeispiel 04 – Repository-Stand prüfen

## Situation

Es ist unklar, welchen Zustand ein lokales Git-Repository aktuell hat.

Beispielsweise:

- Wurde bereits etwas geändert?
- Gibt es offene Änderungen?
- Welcher Branch ist aktiv?
- Mit welchem GitHub-Repository ist das Projekt verbunden?
- Welche Commits existieren?
- Ist das lokale Repository auf dem aktuellen Stand?

Bevor weitere Befehle ausgeführt werden, wird deshalb zunächst der Repository-Zustand ermittelt.

## 1. In das Repository wechseln

```powershell
cd "D:\GitHub\Mein-Projekt"
```

## 2. Arbeitsverzeichnis prüfen

```powershell
git status
```

Dies ist normalerweise der wichtigste erste Befehl.

Er zeigt unter anderem:

- aktuellen Branch
- Änderungen an Dateien
- neue Dateien
- gelöschte Dateien
- vorgemerkte Änderungen
- Hinweise zum Synchronisationsstand

## 3. Aktuellen Branch feststellen

```powershell
git branch --show-current
```

## 4. Remote feststellen

```powershell
git remote -v
```

Jetzt ist bekannt, welches GitHub-Repository als `origin` konfiguriert ist.

## 5. Letzte Commits ansehen

```powershell
git log --oneline -5
```

## 6. Lokale Änderungen prüfen

Wenn `git status` Änderungen meldet:

```powershell
git diff
```

## 7. Vorgemerkte Änderungen prüfen

Wenn Dateien bereits mit `git add` vorgemerkt wurden:

```powershell
git diff --staged
```

Damit wird geprüft, was beim nächsten Commit tatsächlich gespeichert würde.

## 8. Typische Ergebnisse

### Fall A – Alles sauber

```text
nothing to commit, working tree clean
```

Das bedeutet, dass im lokalen Arbeitsverzeichnis keine offenen Änderungen vorhanden sind.

### Fall B – Lokale Änderungen vorhanden

```text
modified: README.md
```

Dann wurde lokal etwas verändert. Jetzt `git diff` verwenden.

### Fall C – Neue Datei

```text
Untracked files:
    neue_datei.md
```

Die Datei wird derzeit noch nicht von Git versioniert.

### Fall D – Falsches Repository

Wenn `git remote -v` ein unerwartetes Ziel zeigt: **Nicht pushen.** Zuerst Remote und lokalen Pfad prüfen.

## 9. Kompakte Statusprüfung

```powershell
git status
git branch --show-current
git remote -v
```

Für eine ausführlichere Prüfung:

```powershell
git status
git branch --show-current
git remote -v
git log --oneline -5
git diff
git diff --staged
```

# Merksatz

> **`git status` ist der erste Blick in das Repository.**

Wer nicht weiß, was im Repository gerade passiert, sollte zunächst `git status` ausführen und nicht einfach den nächsten Git-Befehl ausprobieren.
