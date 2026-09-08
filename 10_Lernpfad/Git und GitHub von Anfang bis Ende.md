# Git und GitHub von Anfang bis Ende

## 1. Ziel

Dieses Tutorial führt einmal vollständig durch einen typischen Git- und GitHub-Arbeitsablauf.

Am Ende wurde:

- ein GitHub-Repository erstellt,
- ein lokales Repository eingerichtet,
- eine Datei geändert,
- ein Commit erstellt,
- die Änderung nach GitHub übertragen,
- eine Änderung direkt auf GitHub durchgeführt,
- diese Änderung lokal übernommen,
- ein abweichender Stand verstanden,
- und der vollständige Synchronisationsablauf durchgeführt.

Das Tutorial ist als praktische Übung gedacht.

---

# 2. Voraussetzungen

Benötigt werden:

- ein GitHub-Account
- Git auf dem lokalen Rechner
- PowerShell
- ein lokaler Arbeitsordner

Git prüfen:

```powershell
git --version
```

---

# 3. Beispielprojekt

Für das Tutorial verwenden wir ein bewusst einfaches Repository:

```text
GitHub-Lernprojekt
```

Das Projekt enthält zunächst nur:

```text
README.md
```

---

# 4. GitHub Repository erstellen

Auf GitHub ein neues Repository erstellen.

Name:

```text
GitHub-Lernprojekt
```

Für dieses Tutorial wird das Repository leer angelegt.

Das bedeutet:

- keine zusätzliche README
- keine zusätzliche `.gitignore`
- keine zusätzliche Lizenz

Der Grund ist, dass wir die lokale Git-Historie bewusst selbst aufbauen.

---

# 5. Lokales Repository erstellen

Einen lokalen Projektordner anlegen:

```powershell
mkdir "D:\GitHub\GitHub-Lernprojekt"
cd "D:\GitHub\GitHub-Lernprojekt"
```

Git initialisieren:

```powershell
git init
```

---

# 6. Erste Datei erstellen

Eine einfache README-Datei erstellen.

Beispielinhalt:

```markdown
# GitHub-Lernprojekt

Mein erstes GitHub-Lernprojekt.
```

---

# 7. Zustand prüfen

```powershell
git status
```

Git sollte die neue Datei als nicht versioniert anzeigen.

Beispielsweise:

```text
Untracked files:
    README.md
```

---

# 8. Datei für Commit vormerken

```powershell
git add README.md
```

Danach:

```powershell
git status
```

Die Datei befindet sich jetzt im Staging.

---

# 9. Staging prüfen

```powershell
git diff --staged
```

Jetzt wird kontrolliert, was tatsächlich committed werden soll.

---

# 10. Ersten Commit erstellen

```powershell
git commit -m "Initial repository import"
```

Damit existiert der erste lokale Commit.

---

# 11. Branch prüfen

```powershell
git branch --show-current
```

Falls der Branch noch nicht `main` heißt:

```powershell
git branch -M main
```

Danach:

```powershell
git branch --show-current
```

Erwartet:

```text
main
```

---

# 12. GitHub Repository verbinden

Die URL des zuvor erstellten GitHub-Repositorys verwenden:

```powershell
git remote add origin https://github.com/Benutzername/GitHub-Lernprojekt.git
```

Danach:

```powershell
git remote -v
```

Prüfen, dass `origin` auf das richtige Repository zeigt.

---

# 13. Ersten Push durchführen

```powershell
git push -u origin main
```

Jetzt befindet sich der lokale Commit auch auf GitHub.

---

# 14. Ergebnis kontrollieren

Lokal:

```powershell
git status
```

Anschließend GitHub öffnen.

Prüfen:

```text
[ ] Repository vorhanden
[ ] README vorhanden
[ ] Branch main vorhanden
[ ] Commit vorhanden
[ ] Inhalt korrekt
```

Damit ist der erste Teil abgeschlossen.

---

# 15. Erste lokale Änderung

Jetzt wird die README lokal erweitert.

Beispiel:

```markdown
# GitHub-Lernprojekt

Mein erstes GitHub-Lernprojekt.

Dieses Projekt dient zum Erlernen von Git und GitHub.
```

---

# 16. Änderung prüfen

```powershell
git status
```

Danach:

```powershell
git diff
```

Die Änderung wird jetzt sichtbar.

---

# 17. Änderung committen

```powershell
git add README.md
git diff --staged
git commit -m "Expand project description"
```

---

# 18. Änderung nach GitHub übertragen

```powershell
git push
```

Danach GitHub öffnen und kontrollieren.

---

# 19. Jetzt direkt auf GitHub arbeiten

Die README direkt auf GitHub öffnen.

Eine weitere Zeile ergänzen:

```markdown
Dieses Repository wird für praktische Übungen verwendet.
```

Die Änderung online committen.

Damit ist GitHub dem lokalen Repository voraus.

---

# 20. Lokalen Stand prüfen

Zurück in PowerShell:

```powershell
git status
```

Der lokale Arbeitsstand kann weiterhin sauber aussehen.

Aber:

> Lokal bedeutet „sauber“ nicht automatisch „aktuell mit GitHub“.

Das ist ein wichtiger Unterschied.

---

# 21. Änderungen von GitHub übernehmen

```powershell
git pull
```

Git ruft die Änderungen vom Remote ab und integriert sie in den aktuellen lokalen Branch.

Danach:

```powershell
git status
```

und:

```powershell
git log --oneline -5
```

Die Online-Änderung ist jetzt auch lokal vorhanden.

---

# 22. Lokal erneut arbeiten

Jetzt wird lokal eine weitere Änderung vorgenommen.

Beispiel:

```markdown
## Lernziel

Das Zusammenspiel zwischen lokalem Git und GitHub verstehen.
```

Danach:

```powershell
git status
git diff
```

---

# 23. Commit und Push

```powershell
git add README.md
git diff --staged
git commit -m "Add learning objective"
git push
```

Damit ist die Änderung wieder auf GitHub.

---

# 24. Was wurde bisher gelernt?

Der komplette einfache Ablauf lautet:

```text
GitHub Repository erstellen
        ↓
lokales Repository erstellen
        ↓
Datei erstellen
        ↓
git add
        ↓
git commit
        ↓
git remote add
        ↓
git push
        ↓
GitHub
        ↓
online ändern
        ↓
git pull
        ↓
lokal weiterarbeiten
        ↓
git commit
        ↓
git push
```

---

# 25. Konfliktsituation verstehen

Jetzt betrachten wir einen wichtigen Sonderfall.

Lokal wird eine Datei geändert:

```text
Lokale Änderung
```

Gleichzeitig wird dieselbe Datei auf GitHub geändert:

```text
Online Änderung
```

Beide Änderungen basieren auf demselben Ausgangsstand.

Vereinfacht:

```text
          lokale Änderung
         /
A ───── B
         \
          Online Änderung
```

Jetzt können die beiden Stände auseinanderlaufen.

---

# 26. Push kann abgelehnt werden

Wenn lokal committed wurde:

```powershell
git commit -m "Update local documentation"
```

und anschließend:

```powershell
git push
```

kann Git den Push ablehnen.

Das ist ein Schutzmechanismus.

---

# 27. Situation untersuchen

Zuerst:

```powershell
git status
```

Dann:

```powershell
git branch --show-current
git remote -v
```

Danach muss festgestellt werden, was auf GitHub passiert ist.

---

# 28. Änderungen integrieren

Wenn die lokale Situation dies zulässt:

```powershell
git pull
```

Git versucht nun, die Änderungen zusammenzuführen.

Wenn kein Konflikt entsteht, kann anschließend wieder:

```powershell
git push
```

ausgeführt werden.

---

# 29. Merge Conflict

Wenn beide Seiten dieselbe Stelle unterschiedlich verändert haben, kann Git den Konflikt nicht automatisch lösen.

Dann:

```powershell
git status
```

verwenden.

Die betroffene Datei enthält möglicherweise Konfliktmarkierungen:

```text
<<<<<<< HEAD
Lokale Änderung
=======
Änderung auf GitHub
>>>>>>> origin/main
```

Diese Markierungen sind keine gültigen Inhalte für die endgültige Datei.

Die gewünschte Version muss manuell hergestellt werden.

---

# 30. Konflikt abschließen

Nach der manuellen Bearbeitung:

```powershell
git add <Datei>
```

Danach den von Git erwarteten Merge-Abschluss durchführen.

Anschließend:

```powershell
git status
```

Wenn der Konflikt vollständig gelöst wurde, kann anschließend wieder gepusht werden:

```powershell
git push
```

---

# 31. Der wichtigste Kontrollpunkt

Wenn nicht klar ist, was im Repository passiert, nicht raten.

Zuerst:

```powershell
git status
git branch --show-current
git remote -v
```

Diese drei Befehle beantworten bereits:

```text
Wo bin ich?
Auf welchem Branch bin ich?
Wohin zeigt das Remote?
```

Für die Änderungen:

```powershell
git diff
git diff --staged
```

Für die Historie:

```powershell
git log --oneline -5
```

---

# 32. Der vollständige Git-Kreislauf

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

Dieser Kreislauf ist das zentrale Modell für die tägliche Arbeit.

---

# 33. Abschlussprüfung

Am Ende des Tutorials:

```powershell
git status
git branch --show-current
git remote -v
git log --oneline -5
```

Danach GitHub öffnen und prüfen:

```text
[ ] Repository vorhanden
[ ] richtiger Branch
[ ] erwartete Dateien vorhanden
[ ] letzte Änderungen vorhanden
[ ] Commit-Historie nachvollziehbar
[ ] keine vertraulichen Daten veröffentlicht
```

---

# 34. Was man nach diesem Tutorial können sollte

Nach Abschluss sollte man erklären können:

### Git

> Git verwaltet die Versionshistorie eines Projekts.

### GitHub

> GitHub stellt Git-Repositories online bereit und ermöglicht Zusammenarbeit.

### `git add`

> Änderungen für den nächsten Commit vormerken.

### `git commit`

> Einen lokalen Versionsstand in der Git-Historie speichern.

### `git push`

> Lokale Commits zum Remote-Repository übertragen.

### `git pull`

> Änderungen vom Remote abrufen und in den aktuellen lokalen Branch integrieren.

### `git status`

> Den aktuellen Zustand des lokalen Repositorys prüfen.

### `git remote -v`

> Anzeigen, mit welchem Remote-Repository das lokale Repository verbunden ist.

---

# 35. Der wichtigste Merksatz

> **Git ist kein System, bei dem man einfach Befehle nacheinander ausführt.**

Entscheidend ist immer:

```text
Zustand verstehen
       ↓
Aktion durchführen
       ↓
Ergebnis prüfen
```

Oder kurz:

> **Prüfen → Handeln → Kontrollieren**