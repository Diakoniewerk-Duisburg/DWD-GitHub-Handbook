# Praxisbeispiel 07 – Mehrere Änderungen sauber committen

## Situation

Während einer Arbeitssitzung wurden mehrere Dateien geändert.

Jetzt stellt sich die Frage:

> Sollen alle Änderungen gemeinsam committed werden?

Die Antwort lautet:

> **Nicht automatisch.**

Entscheidend ist, ob die Änderungen logisch zusammengehören.

## 1. Änderungen vollständig erfassen

```powershell
git status
git diff
```

## 2. Logischen Zusammenhang feststellen

Beispiel:

```text
README.md
04_HowTos/README.md
05_Praxisbeispiele/README.md
```

Wenn alle Änderungen demselben Zweck dienen, kann ein gemeinsamer Commit sinnvoll sein.

```powershell
git add .
git diff --staged
git commit -m "Improve handbook navigation"
```

## 3. Nicht zusammengehörende Änderungen trennen

Beispielsweise:

```text
README.md                → Dokumentation
PROJECT_TIME_TRACKING.md → Zeiterfassung
TestScript.ps1           → technischer Test
```

Diese Änderungen gehören möglicherweise nicht zusammen.

Dann Dateien gezielt vormerken:

```powershell
git add README.md
git diff --staged
git commit -m "Update handbook documentation"
```

Danach kann die nächste logische Änderung separat committed werden.

## 4. Warum kleine logische Commits sinnvoll sind

Eine gute Commit-Historie sollte nachvollziehbar sein.

Beispiel:

```text
Add GitHub online workflow
Add repository transfer guide
Improve handbook navigation
Add troubleshooting examples
Update security documentation
```

Weniger hilfreich wären allgemeine Meldungen wie:

```text
Update files
Changes
Fix stuff
Update
```

## 5. `git add .` ist nicht automatisch falsch

Der Befehl ist praktisch und kann bei einem zusammenhängenden Änderungsumfang sinnvoll sein.

Er sollte aber nicht bedeuten, alles ungeprüft zu committen.

Nach dem Staging:

```powershell
git diff --staged
```

prüfen.

## 6. Beispiel für eine saubere Arbeitsweise

```powershell
git status
git diff

git add README.md
git add 04_HowTos/README.md
git add 05_Praxisbeispiele/README.md

git status
git diff --staged
git commit -m "Improve handbook navigation"

git status
```

# Merksatz

> **Ein Commit sollte eine logisch zusammengehörende Änderung beschreiben – nicht einfach alle aktuell vorhandenen Änderungen.**
