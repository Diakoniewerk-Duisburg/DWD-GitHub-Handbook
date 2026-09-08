# Lernpfad

Dieser Bereich führt Schritt für Schritt durch einen vollständigen Git- und GitHub-Arbeitsablauf.

Der Lernpfad verbindet die einzelnen Kapitel des Handbooks zu einem zusammenhängenden praktischen Beispiel.

## Ziel

Nach Abschluss des Lernpfads soll verständlich sein:

- was ein Git-Repository ist,
- was GitHub ist,
- wie ein Repository lokal verwendet wird,
- wie Änderungen entstehen,
- wie Änderungen geprüft werden,
- was ein Commit ist,
- was `git push` macht,
- was `git pull` macht,
- wie GitHub und ein lokales Repository zusammenarbeiten,
- wie Online- und lokale Änderungen zusammengeführt werden,
- wie typische Probleme erkannt werden.

---

# Lernpfad

## Schritt 1 – Grundlagen verstehen

Zuerst:

- [Was ist Git?](../01_Grundlagen/Was_ist_Git.md)
- [Was ist GitHub?](../01_Grundlagen/Was_ist_GitHub.md)
- [Unterschied Git und GitHub](../01_Grundlagen/Unterschied_Git_und_GitHub.md)

---

## Schritt 2 – Repository auf GitHub erstellen

Ein neues Repository wird auf GitHub angelegt.

[HowTo – GitHub Repository anlegen](../04_HowTos/01_Repository/GitHub_Repository_anlegen.md)

---

## Schritt 3 – Repository lokal bereitstellen

Das Repository wird lokal geklont.

[Repository klonen](../03_Arbeitsweise/Repository_klonen.md)

---

## Schritt 4 – Repository-Zustand prüfen

Vor der ersten Änderung:

```powershell
git status
git branch --show-current
git remote -v
```

Praxisbeispiel:

[Repository-Stand prüfen](../05_Praxisbeispiele/04_Repository_Stand_pruefen.md)

---

## Schritt 5 – Datei ändern

Eine Datei wird lokal bearbeitet.

Beispielsweise:

```text
README.md
```

---

## Schritt 6 – Änderung prüfen

```powershell
git status
git diff
```

Praxis:

[Lokale Änderung committen und pushen](../05_Praxisbeispiele/03_Lokale_Aenderung_committen_und_pushen.md)

---

## Schritt 7 – Änderung für Commit vormerken

```powershell
git add README.md
```

Danach:

```powershell
git diff --staged
```

Jetzt wird kontrolliert, was tatsächlich committed werden soll.

---

## Schritt 8 – Commit erstellen

```powershell
git commit -m "Update project documentation"
```

Der Commit befindet sich jetzt lokal.

Noch nicht auf GitHub.

---

## Schritt 9 – Push

```powershell
git push
```

Jetzt wird der lokale Commit zum Remote-Repository übertragen.

---

## Schritt 10 – GitHub kontrollieren

Das Repository auf GitHub öffnen.

Prüfen:

- Datei vorhanden?
- Änderung vorhanden?
- Commit vorhanden?
- richtiger Branch?

---

# Zweiter Teil – Änderung direkt auf GitHub

Jetzt wird bewusst die andere Richtung getestet.

## Schritt 11 – Datei online ändern

Eine Datei wird direkt über GitHub bearbeitet.

Siehe:

[Dateien bearbeiten](../02_GitHub_Online/Dateien_bearbeiten.md)

---

## Schritt 12 – Online-Commit

Die Änderung wird direkt auf GitHub committed.

Siehe:

[Commit online](../02_GitHub_Online/Commit_online.md)

---

## Schritt 13 – Lokalen Stand aktualisieren

Zurück im lokalen Repository:

```powershell
git status
```

Wenn das Arbeitsverzeichnis sauber ist:

```powershell
git pull
```

Jetzt befindet sich die Online-Änderung auch lokal.

---

# Dritter Teil – Konflikt verstehen

Jetzt wird bewusst eine Situation betrachtet, in der beide Seiten unabhängig geändert wurden.

## Schritt 14 – Lokal ändern

Eine Datei lokal bearbeiten und committen.

```powershell
git add .
git commit -m "Update local documentation"
```

---

## Schritt 15 – Gleichzeitig online ändern

Die gleiche Datei oder ein anderer Bereich wird direkt auf GitHub geändert und committed.

Jetzt besitzen lokal und GitHub unterschiedliche Änderungen.

---

## Schritt 16 – Push

```powershell
git push
```

Der Push kann abgelehnt werden.

---

## Schritt 17 – Situation analysieren

Zuerst:

```powershell
git status
git branch --show-current
git remote -v
```

Dann die Ursache feststellen.

Siehe:

[Push abgelehnt](../05_Praxisbeispiele/05_Push_abgelehnt.md)

---

## Schritt 18 – Änderungen integrieren

Wenn der lokale Zustand sauber ist:

```powershell
git pull
```

Git versucht, die Änderungen zusammenzuführen.

Wenn ein Konflikt entsteht:

[Merge Conflict](../08_Troubleshooting/Merge_Conflict.md)

---

## Schritt 19 – Konflikt lösen

Die betroffene Datei wird geprüft und die gewünschte endgültige Version hergestellt.

Danach:

```powershell
git add <Datei>
```

und den von Git erwarteten Abschluss des Merge-Vorgangs durchführen.

Anschließend:

```powershell
git status
```

---

## Schritt 20 – Erneut pushen

Nach erfolgreicher Zusammenführung:

```powershell
git push
```

---

# Der komplette Ablauf

```text
Git verstehen
      ↓
GitHub verstehen
      ↓
Repository erstellen
      ↓
Repository klonen
      ↓
Status prüfen
      ↓
Datei ändern
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
GitHub kontrollieren
      ↓
online ändern
      ↓
git pull
      ↓
lokal weiterarbeiten
      ↓
git push
      ↓
Konflikt verstehen
      ↓
Konflikt lösen
      ↓
synchronisieren
```

---

# Die fünf wichtigsten Fragen

Bei jeder Git-Aktion sollte man beantworten können:

### 1. Wo bin ich?

```powershell
Get-Location
```

### 2. In welchem Repository bin ich?

```powershell
git remote -v
```

### 3. Auf welchem Branch bin ich?

```powershell
git branch --show-current
```

### 4. Was hat sich geändert?

```powershell
git status
git diff
```

### 5. Wohin geht die Änderung?

```powershell
git remote -v
```

---

# Lernziel

Nach dem Lernpfad sollte folgender Zusammenhang klar sein:

```text
                   GitHub
                     ▲
                     │
                   push
                     │
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
```

Und in die andere Richtung:

```text
GitHub
  │
  │ pull
  ▼
lokales Repository
```

---

# Abschluss

Wer diesen Lernpfad verstanden hat, benötigt für die tägliche Arbeit meistens nur noch:

- die Befehlsreferenz für einzelne Befehle,
- die Troubleshooting-Dokumentation bei Problemen,
- die Sicherheitsregeln für kritische Inhalte,
- die Checklisten für wiederkehrende Aufgaben.

Das eigentliche Ziel ist nicht das Auswendiglernen von Git-Befehlen.

> **Das Ziel ist, den Zustand des Repositorys jederzeit verstehen und kontrollieren zu können.**