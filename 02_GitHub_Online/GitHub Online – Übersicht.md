# Arbeiten direkt in GitHub

Dieser Bereich beschreibt die direkte Arbeit mit einem Repository über die GitHub-Weboberfläche.

Ein lokales Git-Repository ist dafür nicht zwingend erforderlich.

## Typische Aufgaben

| Aufgabe | Anleitung |
|---|---|
| Neue Datei erstellen | [Dateien anlegen](Dateien_anlegen.md) |
| Bestehende Datei ändern | [Dateien bearbeiten](Dateien_bearbeiten.md) |
| Datei verschieben | [Dateien verschieben](Dateien_verschieben.md) |
| Datei löschen | [Dateien löschen](Dateien_loeschen.md) |
| Änderungen prüfen | [Änderungen vergleichen](Aenderungen_vergleichen.md) |
| Änderung committen | [Commit online](Commit_online.md) |
| Branch verwenden | [Branch online](Branch_online.md) |
| Pull Request erstellen | [Pull Request online](Pull_Request_online.md) |

## Grundprinzip

Eine Änderung direkt auf GitHub folgt grundsätzlich diesem Ablauf:

```text
Repository öffnen
      ↓
Datei auswählen
      ↓
Datei bearbeiten
      ↓
Änderung prüfen
      ↓
Commit erstellen
      ↓
Ergebnis kontrollieren
```

## Commit online

Auch bei einer Änderung über die Weboberfläche wird ein Git-Commit erzeugt.

Der Unterschied zur lokalen Arbeitsweise besteht darin, dass GitHub die Änderung direkt im Remote-Repository speichert.

```text
GitHub Weboberfläche
        ↓
Änderung
        ↓
Commit
        ↓
GitHub Repository
```

## Direkter Commit auf `main`

Bei einfachen Dokumentationsänderungen kann direkt auf `main` gearbeitet werden, sofern dies für das Repository vorgesehen ist.

Für größere Änderungen oder Änderungen mit Review-Anforderung sollte stattdessen ein Branch verwendet und anschließend ein Pull Request erstellt werden.

## Branch und Pull Request

Für kontrollierte Änderungen:

```text
main
 │
 └── Branch erstellen
          ↓
       Änderung
          ↓
       Commit
          ↓
    Pull Request
          ↓
       Prüfung
          ↓
       Merge
          ↓
         main
```

## Online oder lokal?

| Situation | Geeignete Arbeitsweise |
|---|---|
| Kleine Markdown-Korrektur | GitHub Online |
| Kleine Dokumentationsergänzung | GitHub Online |
| Einzelne Datei ändern | GitHub Online |
| Viele Dateien ändern | Lokal mit Git |
| Große Umstrukturierung | Lokal mit Git |
| Skripte entwickeln | Lokal mit Git |
| Tests durchführen | Lokal mit Git |
| Änderungen mit Review | Branch + Pull Request |

## Wichtig

Änderungen, die direkt auf GitHub vorgenommen werden, sind anschließend **nicht automatisch im lokalen Repository vorhanden**.

Nach einer Online-Änderung muss das lokale Repository bei Bedarf synchronisiert werden:

```powershell
git pull
```

Siehe dazu:

[Repository synchronisieren](../03_Arbeitsweise/Repository_synchronisieren.md)