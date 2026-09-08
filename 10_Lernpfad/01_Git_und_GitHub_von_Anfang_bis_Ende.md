# Git und GitHub von Anfang bis Ende

## 1. Ziel

Dieses Tutorial führt einmal vollständig durch einen typischen Git- und GitHub-Arbeitsablauf.

Am Ende wurden:

- ein GitHub-Repository erstellt,
- ein lokales Repository eingerichtet,
- Änderungen geprüft,
- Commits erstellt,
- Änderungen nach GitHub übertragen,
- eine Änderung direkt auf GitHub durchgeführt,
- diese Änderung lokal übernommen,
- und eine mögliche Konfliktsituation verstanden.

Das Tutorial ist als praktische Übung gedacht.

## 2. Voraussetzungen

Benötigt werden:

- ein GitHub-Account
- Git auf dem lokalen Rechner
- PowerShell
- ein lokaler Arbeitsordner

Git prüfen:

```powershell
git --version
```

## 3. Beispielprojekt

Für das Tutorial verwenden wir:

```text
GitHub-Lernprojekt
```

Das Projekt enthält zunächst nur:

```text
README.md
```

## 4. GitHub Repository erstellen

Ein neues Repository auf GitHub erstellen.

Name:

```text
GitHub-Lernprojekt
```

Für dieses Tutorial wird das Repository leer angelegt.

Wenn bereits ein vollständiges lokales Git-Repository existiert, sollte das Ziel-Repository auf GitHub nicht zusätzlich mit einer eigenen Historie initialisiert werden.

Siehe [GitHub Repository anlegen](../04_HowTos/GitHub_Repository_anlegen.md).

## 5. Lokales Repository erstellen

```powershell
mkdir "D:\GitHub\GitHub-Lernprojekt"
cd "D:\GitHub\GitHub-Lernprojekt"
git init
```

Danach:

```powershell
git status
```

## 6. Erste Datei erstellen

Eine einfache `README.md` anlegen:

```markdown
# GitHub-Lernprojekt

Mein erstes GitHub-Lernprojekt.
```

## 7. Änderung prüfen

```powershell
git status
git diff
```

## 8. Datei für den Commit vormerken

```powershell
git add README.md
git diff --staged
```

Jetzt wird kontrolliert, was tatsächlich committed werden soll.

## 9. Ersten Commit erstellen

```powershell
git commit -m "Initial repository import"
```

Der Commit befindet sich zunächst nur lokal.

## 10. Branch prüfen

```powershell
git branch --show-current
```

Falls erforderlich:

```powershell
git branch -M main
```

Danach erneut prüfen:

```powershell
git branch --show-current
```

## 11. GitHub Repository verbinden

```powershell
git remote add origin https://github.com/Benutzername/GitHub-Lernprojekt.git
git remote -v
```

Prüfen, dass `origin` auf das richtige Repository zeigt.

## 12. Ersten Push durchführen

```powershell
git push -u origin main
```

Jetzt befindet sich der lokale Commit auch auf GitHub.

## 13. Ergebnis kontrollieren

Lokal:

```powershell
git status
git log --oneline -5
```

Auf GitHub prüfen:

- Repository vorhanden
- `README.md` vorhanden
- Branch `main` vorhanden
- Commit vorhanden
- Inhalt korrekt

## 14. Lokale Änderung

README lokal erweitern:

```markdown
# GitHub-Lernprojekt

Mein erstes GitHub-Lernprojekt.

Dieses Projekt dient zum Erlernen von Git und GitHub.
```

Prüfen:

```powershell
git status
git diff
```

Dann:

```powershell
git add README.md
git diff --staged
git commit -m "Expand project description"
git push
```

## 15. Direkt auf GitHub ändern

Die README direkt auf GitHub öffnen, eine weitere Zeile ergänzen und die Änderung online committen.

Damit ist GitHub dem lokalen Repository voraus.

Zurück in PowerShell:

```powershell
git status
```

Ein sauberer lokaler Arbeitsstand bedeutet hier nicht automatisch, dass er aktuell mit GitHub ist.

## 16. Online-Änderung lokal übernehmen

Wenn der lokale Arbeitsstand sauber ist:

```powershell
git pull
```

`git pull` ruft Änderungen vom Remote-Repository ab und integriert sie in den aktuellen lokalen Branch.

Danach:

```powershell
git status
git log --oneline -5
```

Die Online-Änderung ist jetzt auch lokal vorhanden.

## 17. Lokal erneut arbeiten

Eine weitere lokale Änderung vornehmen und prüfen:

```powershell
git status
git diff
```

Dann:

```powershell
git add README.md
git diff --staged
git commit -m "Add learning objective"
git push
```

## 18. Konfliktsituation verstehen

Ein Konflikt kann entstehen, wenn lokal und auf GitHub unabhängig voneinander dieselbe Stelle geändert wurde.

Vereinfacht:

```text
          lokale Änderung
         /
A ───── B
         \
          Online Änderung
```

Der lokale und der entfernte Stand können dann auseinanderlaufen.

## 19. Push kann abgelehnt werden

Wenn lokal committed wurde und GitHub inzwischen ebenfalls geändert wurde, kann:

```powershell
git push
```

abgelehnt werden.

Das ist ein Schutzmechanismus und kein Grund, sofort einen Force Push auszuführen.

Zuerst:

```powershell
git status
git branch --show-current
git remote -v
```

Siehe [Push abgelehnt](../05_Praxisbeispiele/Praxisbeispiel%20%E2%80%93%20Push%20abgelehnt.md).

## 20. Änderungen integrieren

Wenn der Zustand dies zulässt:

```powershell
git pull
```

Git versucht, die Änderungen zu integrieren.

Wenn kein Konflikt entsteht, kann anschließend wieder gepusht werden:

```powershell
git push
```

## 21. Merge Conflict

Wenn Git Änderungen nicht automatisch zusammenführen kann:

```powershell
git status
```

Die betroffene Datei kann Konfliktmarkierungen enthalten:

```text
<<<<<<< HEAD
Lokale Änderung
=======
Änderung auf GitHub
>>>>>>> origin/main
```

Diese Markierungen müssen bei der manuellen Konfliktlösung entfernt werden.

Die gewünschte endgültige Datei herstellen und anschließend:

```powershell
git add <Datei>
```

Danach den von Git erwarteten Abschluss des Merge-Vorgangs durchführen und erneut prüfen:

```powershell
git status
```

Wenn der Konflikt vollständig gelöst wurde:

```powershell
git push
```

Siehe [Merge Conflict](../08_Troubleshooting/Merge_Conflict.md).

## 22. Die wichtigsten Kontrollbefehle

Wenn unklar ist, was im Repository passiert:

```powershell
git status
git branch --show-current
git remote -v
git diff
git diff --staged
git log --oneline -5
```

Diese Befehle beantworten:

```text
Wo bin ich?
Auf welchem Branch bin ich?
Wohin zeigt das Remote?
Was hat sich geändert?
Was ist für den Commit vorgemerkt?
Welche Commits existieren?
```

## 23. Der vollständige Git-Kreislauf

```text
                  GitHub
                    ▲
                    │
                  push
                    │
             lokales Repository
                    ▲
                    │
                 commit
                    ▲
                    │
                  add
                    ▲
                    │
             Arbeitsverzeichnis
                    │
                    │
                  pull
                    │
                    ▼
                  GitHub
```

## 24. Abschlussprüfung

Am Ende:

```powershell
git status
git branch --show-current
git remote -v
git log --oneline -5
```

Auf GitHub prüfen:

```text
[ ] Repository vorhanden
[ ] richtiger Branch
[ ] erwartete Dateien vorhanden
[ ] letzte Änderungen vorhanden
[ ] Commit-Historie nachvollziehbar
[ ] keine vertraulichen Daten veröffentlicht
```

## 25. Was man nach diesem Tutorial verstehen sollte

### Git

Git verwaltet die Versionshistorie eines Projekts.

### GitHub

GitHub stellt Git-Repositories online bereit und ermöglicht Zusammenarbeit.

### `git add`

Änderungen für den nächsten Commit vormerken.

### `git commit`

Einen lokalen Versionsstand in der Git-Historie speichern.

### `git push`

Lokale Commits zum Remote-Repository übertragen.

### `git pull`

Änderungen vom Remote abrufen und in den aktuellen lokalen Branch integrieren.

### `git status`

Den aktuellen Zustand des lokalen Repositorys prüfen.

### `git remote -v`

Anzeigen, mit welchem Remote-Repository das lokale Repository verbunden ist.

## Merksatz

> **Git ist kein System, bei dem man einfach Befehle nacheinander ausführt. Entscheidend ist immer: Zustand verstehen → Aktion durchführen → Ergebnis prüfen.**
