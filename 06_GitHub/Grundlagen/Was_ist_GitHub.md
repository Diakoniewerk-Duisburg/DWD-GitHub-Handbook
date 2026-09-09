# Was ist GitHub?

## 1. Zweck

GitHub ist eine internetbasierte Plattform für die Speicherung, Verwaltung und Zusammenarbeit an Git-Repositorys.

GitHub verwendet Git als Grundlage.

GitHub erweitert Git unter anderem um:

- zentrale Repositorys
- Benutzerverwaltung
- Zusammenarbeit
- Pull Requests
- Code Reviews
- Issues
- Projekte
- Releases
- Actions
- Sicherheitsfunktionen
- Weboberfläche

## 2. GitHub Repository

Ein GitHub Repository ist ein Git-Repository, das auf der GitHub-Plattform gespeichert wird.

Beispiel:

```text
Lokaler Computer
      │
      │ git push
      ▼
    GitHub
      │
      │ git pull
      ▼
Lokaler Computer
```

Das Repository kann dabei sowohl über Git-Befehle als auch über die GitHub-Weboberfläche bearbeitet werden.

## 3. Arbeiten über die Weboberfläche

GitHub ermöglicht es, viele Aufgaben direkt im Browser durchzuführen.

Beispielsweise können:

- Dateien erstellt werden
- Dateien bearbeitet werden
- Dateien gelöscht werden
- Dateien verschoben werden
- Commits erstellt werden
- Branches erstellt werden
- Pull Requests erstellt werden
- Änderungen verglichen werden

Dafür ist kein lokales Git erforderlich.

Das ist insbesondere für kleine Änderungen an Dokumentationen praktisch.

## 4. Zusammenarbeit

GitHub ermöglicht mehreren Personen, an einem Repository zu arbeiten.

Dabei können Änderungen über Git und GitHub nachvollzogen werden.

Typische Elemente sind:

```text
Repository
    │
    ├── Branch
    │      │
    │      └── Änderungen
    │
    ├── Commit
    │
    ├── Pull Request
    │
    └── Merge
```

## 5. GitHub als zentraler Speicherort

Ein GitHub Repository kann als zentrale Ablage für ein Projekt verwendet werden.

Dabei bleibt Git jedoch ein verteiltes Versionsverwaltungssystem.

Das bedeutet:

- das lokale Repository besitzt seine eigene Historie
- GitHub besitzt ebenfalls die Repository-Historie
- beide können miteinander synchronisiert werden

## 6. GitHub und lokale Arbeit

Es gibt deshalb zwei grundlegende Arbeitsweisen.

### Arbeiten lokal

```text
Datei
  ↓
Lokales Git
  ↓
Commit
  ↓
Push
  ↓
GitHub
```

### Arbeiten direkt online

```text
GitHub
  ↓
Datei bearbeiten
  ↓
Commit
  ↓
GitHub
```

Beide Vorgehensweisen sind möglich.

## 7. Wann ist die GitHub-Weboberfläche sinnvoll?

Die Weboberfläche eignet sich besonders für:

- kleine Dokumentationsänderungen
- Korrekturen
- einzelne Dateien
- schnelle Anpassungen
- Änderungen ohne lokalen Entwicklungsstand

Bei größeren Änderungen ist die lokale Arbeit mit Git meist geeigneter.

## 8. Sicherheit

Ein GitHub Repository kann öffentlich oder privat sein.

Bei internen Projekten müssen insbesondere folgende Punkte beachtet werden:

- keine Passwörter speichern
- keine Zugangstokens speichern
- keine vertraulichen Daten veröffentlichen
- keine geheimen Schlüssel in Repositorys ablegen
- Berechtigungen kontrollieren

Die Tatsache, dass ein Repository privat ist, ersetzt keine sorgfältige Behandlung vertraulicher Informationen.

## 9. Grundprinzip

Git ist die Versionsverwaltung.

GitHub ist die Plattform, auf der Git-Repositorys gespeichert, verwaltet und gemeinsam bearbeitet werden können.