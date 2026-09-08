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

---

# 1. In das Repository wechseln

```powershell id="2z8d4f"
cd "D:\GitHub\Mein-Projekt"
```

---

# 2. Arbeitsverzeichnis prüfen

```powershell id="7x5k3p"
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

---

# 3. Aktuellen Branch feststellen

```powershell id="c1q9hv"
git branch --show-current
```

Beispiel:

```text id="7d8q2m"
main
```

Damit ist bekannt, auf welchem Branch gearbeitet wird.

---

# 4. Remote feststellen

```powershell id="g4m2zs"
git remote -v
```

Beispiel:

```text id="9x7p1q"
origin  https://github.com/Benutzername/Mein-Projekt.git (fetch)
origin  https://github.com/Benutzername/Mein-Projekt.git (push)
```

Jetzt ist bekannt, welches GitHub-Repository als `origin` konfiguriert ist.

---

# 5. Letzte Commits ansehen

```powershell id="4m8v2a"
git log --oneline -5
```

Beispiel:

```text id="h3f7q1"
a91c321 Update documentation
72b8f11 Add troubleshooting guide
15d3c8a Initial repository import
```

Damit kann die lokale Historie nachvollzogen werden.

---

# 6. Lokale Änderungen prüfen

Wenn `git status` Änderungen meldet:

```powershell id="f2w9k6"
git diff
```

Damit wird sichtbar, was im Arbeitsverzeichnis geändert wurde.

---

# 7. Vorgemerkte Änderungen prüfen

Wenn Dateien bereits mit `git add` vorgemerkt wurden:

```powershell id="v6q3j8"
git diff --staged
```

Damit wird geprüft, was beim nächsten Commit tatsächlich gespeichert würde.

---

# 8. Typische Ergebnisse

## Fall A – Alles sauber

```text id="c5y4x8"
nothing to commit, working tree clean
```

Das bedeutet:

> Im lokalen Arbeitsverzeichnis befinden sich keine offenen Änderungen.

---

## Fall B – Lokale Änderungen vorhanden

Beispiel:

```text id="a2w8r5"
modified: README.md
```

Dann wurde lokal etwas verändert.

Jetzt:

```powershell id="8c4v1m"
git diff
```

verwenden.

---

## Fall C – Neue Datei

Beispiel:

```text id="z5m7n2"
Untracked files:
    neue_datei.md
```

Die Datei wird derzeit noch nicht von Git versioniert.

Vor einem Commit muss bewusst entschieden werden, ob sie aufgenommen werden soll.

---

## Fall D – Falsches Repository

Wenn `git remote -v` ein unerwartetes Ziel zeigt:

```text id="p9c3w7"
origin  https://github.com/FalscherAccount/Falsches-Repository.git
```

**Nicht pushen.**

Zuerst Remote und lokalen Pfad korrigieren beziehungsweise die Situation klären.

---

# 9. Kompakte Statusprüfung

Wenn schnell der wichtigste Zustand ermittelt werden soll:

```powershell id="h2v8q6"
git status
git branch --show-current
git remote -v
```

Für eine ausführlichere Prüfung:

```powershell id="y4p7s1"
git status
git branch --show-current
git remote -v
git log --oneline -5
git diff
git diff --staged
```

---

# 10. Entscheidungslogik

Nach der Prüfung kann der weitere Weg bestimmt werden:

```text id="b1k6x9"
git status
    │
    ├── sauber
    │     │
    │     └── weitere Aktion möglich
    │
    ├── lokale Änderungen
    │     │
    │     └── git diff
    │
    └── unbekannter / unerwarteter Zustand
          │
          └── erst analysieren
```

---

# Merksatz

> **`git status` ist der erste Blick in das Repository.**

Wer nicht weiß, was im Repository gerade passiert, sollte zunächst `git status` ausführen und nicht einfach den nächsten Git-Befehl ausprobieren.