# GitHub Online

## Zweck

Dieser Bereich beschreibt die direkte Arbeit mit einem Repository über die GitHub-Weboberfläche.

Viele einfache Aufgaben können vollständig online erledigt werden. Dafür ist kein lokales Git notwendig.

## Typische Aufgaben

| Aufgabe | Anleitung |
|---|---|
| Datei anlegen | [Dateien anlegen](Dateien_anlegen.md) |
| Datei bearbeiten | [Dateien bearbeiten](Dateien_bearbeiten.md) |
| Datei verschieben | [Dateien verschieben](Dateien_verschieben.md) |
| Datei löschen | [Dateien löschen](Dateien_loeschen.md) |
| Änderungen vergleichen | [Änderungen vergleichen](Aenderungen_vergleichen.md) |
| Online committen | [Commit online](Commit_online.md) |
| Branch erstellen | [Branch online](Branch_online.md) |
| Pull Request erstellen | [Pull Request online](Pull_Request_online.md) |

## Grundprinzip

Bei der Arbeit direkt auf GitHub findet die Änderung auf dem Remote-Repository statt.

```text
GitHub Repository
       │
       ▼
Datei online bearbeiten
       │
       ▼
Commit auf GitHub
```

Die Änderung befindet sich danach auf GitHub, aber **nicht automatisch im lokalen Repository**.

Wenn lokal weitergearbeitet werden soll, muss der lokale Stand anschließend aktualisiert werden:

```powershell
git pull
```

`git pull` ruft Änderungen vom Remote-Repository ab und integriert sie in den aktuellen lokalen Branch.

## Online arbeiten oder lokal arbeiten?

### Online ist sinnvoll für

- kleine Dokumentationsänderungen
- Tippfehler
- kurze Ergänzungen
- einzelne Dateien
- schnelle Korrekturen
- einfache README-Anpassungen

### Lokal ist sinnvoll für

- viele Dateien
- umfangreiche Änderungen
- Programmcode
- Tests
- strukturierte Änderungen über mehrere Verzeichnisse
- Änderungen, die vor dem Commit ausführlich geprüft werden müssen

## Direkt auf `main` oder Branch?

Für kleine, kontrollierte Änderungen kann direkt auf `main` gearbeitet werden, sofern dies im Repository erlaubt und organisatorisch gewünscht ist.

Für größere oder gemeinsam bearbeitete Änderungen ist ein eigener Branch mit anschließendem Pull Request die sauberere Vorgehensweise:

```text
main
 │
 └── Arbeitsbranch
       │
       ├── Änderung
       ├── Prüfung
       └── Pull Request
              │
              ▼
             main
```

## Nach einer Online-Änderung

Wenn lokal weitergearbeitet wird:

```powershell
git pull
git status
```

Danach kann normal weitergearbeitet werden.

## Wichtige Regel

> **Eine Änderung auf GitHub ist eine Änderung am Remote-Repository. Sie ist nicht automatisch Bestandteil des lokalen Arbeitsverzeichnisses.**

## Kontrolle

Nach einer Online-Änderung sollten insbesondere geprüft werden:

- richtige Datei
- richtiger Branch
- erwarteter Commit
- korrekter Dateistand
- keine unbeabsichtigten Änderungen

## Weiterführend

Für die lokale Arbeitsweise siehe [03 – Arbeitsweise](../03_Arbeitsweise/README.md).

Für die Unterschiede zwischen Git und GitHub siehe [01 – Grundlagen](../01_Grundlagen/Unterschied_Git_und_GitHub.md).
