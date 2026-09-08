# GitHub Online

## 1. Zweck

GitHub kann vollständig oder teilweise direkt über die Weboberfläche genutzt werden.

Für viele einfache Aufgaben ist kein lokal installiertes Git erforderlich.

Dieser Bereich beschreibt die Arbeit **direkt im GitHub-Repository über den Browser**.

## 2. Typische Aufgaben

Über die GitHub-Weboberfläche können unter anderem:

- Repositorys geöffnet werden
- Dateien angezeigt werden
- Dateien erstellt werden
- Dateien bearbeitet werden
- Dateien verschoben werden
- Dateien gelöscht werden
- Verzeichnisse angelegt werden
- Commits erstellt werden
- Branches erstellt werden
- Änderungen verglichen werden
- Pull Requests erstellt werden

## 3. Grundprinzip

Eine Änderung direkt auf GitHub folgt grundsätzlich diesem Muster:

```text
GitHub Repository
       │
       ▼
Datei auswählen
       │
       ▼
Änderung durchführen
       │
       ▼
Änderung beschreiben
       │
       ▼
Commit erstellen
       │
       ▼
Änderung ist im Repository gespeichert
```

Ein Commit ist dabei der entscheidende Schritt.

Er speichert die Änderung in der Git-Historie des Repositorys.

## 4. Online oder lokal?

Nicht jede Aufgabe muss lokal durchgeführt werden.

### GitHub Online eignet sich besonders für

- einzelne Markdown-Dateien ändern
- Tippfehler korrigieren
- Dokumentation ergänzen
- einzelne Dateien erstellen
- kleine Änderungen durchführen
- schnell einen Commit erstellen

### Lokales Git eignet sich besonders für

- umfangreiche Änderungen
- viele Dateien
- größere Projekte
- Skripte und Quellcode
- automatisierte Verarbeitung
- Arbeiten ohne permanente Internetverbindung
- komplexere Branch- und Merge-Szenarien

## 5. Wichtiger Unterschied

Bei der Online-Arbeit befindet sich die Änderung unmittelbar im GitHub-Repository.

Bei der lokalen Arbeit existieren zunächst zwei Stände:

```text
Lokales Repository
        │
        │ git push
        ▼
GitHub Repository
```

Deshalb muss bei lokaler Arbeit regelmäßig synchronisiert werden.

## 6. Online-Arbeitsablauf

Für eine einfache Änderung:

1. GitHub öffnen
2. Repository öffnen
3. Datei auswählen
4. Datei bearbeiten
5. Änderung prüfen
6. Commit-Nachricht eingeben
7. Commit erstellen
8. Änderung kontrollieren

## 7. Branches

Auch bei der Online-Arbeit können Branches verwendet werden.

Für kleine Änderungen kann direkt auf `main` gearbeitet werden, sofern dies für das Repository zulässig ist.

Für größere oder kontrollierte Änderungen sollte ein eigener Branch verwendet werden.

Beispiel:

```text
main
 │
 └── documentation-update
          │
          ├── Änderungen
          └── Commit
```

Anschließend kann die Änderung über einen Pull Request zurück nach `main` geführt werden.

## 8. Kontrolle nach einer Änderung

Nach einem Online-Commit sollte geprüft werden:

- Ist die Datei am richtigen Ort?
- Ist der Inhalt korrekt?
- Wurde die Änderung tatsächlich gespeichert?
- Ist der Commit in der Historie vorhanden?
- Wurde versehentlich auf dem falschen Branch gearbeitet?

## 9. Weiterführende Dokumentation

Die einzelnen Tätigkeiten werden in separaten Dokumenten beschrieben.

Geplante Dokumente:

- `Repository_oeffnen.md`
- `Dateien_anlegen.md`
- `Dateien_bearbeiten.md`
- `Dateien_verschieben.md`
- `Dateien_loeschen.md`
- `Commit_online.md`
- `Branch_online.md`
- `Pull_Request_online.md`
- `Aenderungen_vergleichen.md`