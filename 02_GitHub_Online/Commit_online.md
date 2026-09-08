# Commit direkt in GitHub erstellen

## 1. Zweck

Ein Commit speichert eine Änderung in der Versionshistorie eines Git-Repositorys.

GitHub ermöglicht es, einen Commit direkt über die Weboberfläche zu erstellen.

## 2. Was ist ein Commit?

Ein Commit ist ein definierter Stand von Änderungen.

Ein Commit enthält unter anderem:

- die vorgenommenen Änderungen
- den Autor
- den Zeitpunkt
- eine Commit-Nachricht
- eine eindeutige Commit-ID

Dadurch kann später nachvollzogen werden, was geändert wurde.

## 3. Wann entsteht ein Commit?

Bei der Arbeit direkt in GitHub entsteht ein Commit beispielsweise beim:

- Erstellen einer Datei
- Bearbeiten einer Datei
- Löschen einer Datei
- Verschieben einer Datei

Die Änderung wird dabei direkt in der Git-Historie des Repositorys gespeichert.

## 4. Commit-Nachricht

Die Commit-Nachricht beschreibt möglichst kurz, was geändert wurde.

Beispiele:

```text
Add GitHub online documentation
```

```text
Update repository documentation
```

```text
Fix documentation typo
```

Eine gute Commit-Nachricht sollte:

- kurz sein
- die Änderung beschreiben
- keine unnötigen Details enthalten
- möglichst eindeutig sein

## 5. Commit über GitHub

Nach einer Änderung bietet GitHub die Möglichkeit, die Änderung zu committen.

Dabei wird normalerweise angegeben:

- Commit-Nachricht
- optional eine ausführlichere Beschreibung
- Ziel-Branch bzw. Vorgehensweise

Danach wird der Commit erstellt.

## 6. Commit direkt auf `main`

Wenn direkt auf `main` gearbeitet wird und dies erlaubt ist:

```text
Datei ändern
     │
     ▼
Commit
     │
     ▼
main
```

Die Änderung befindet sich danach unmittelbar im Hauptbranch.

Diese Vorgehensweise eignet sich für kleine, unkritische Dokumentationsänderungen, sofern die Repository-Regeln dies zulassen.

## 7. Commit über einen neuen Branch

Bei kontrollierter Arbeitsweise kann GitHub die Änderung stattdessen in einem neuen Branch speichern.

Beispiel:

```text
main
 │
 └── documentation-update
          │
          └── Commit
```

Die Änderung kann anschließend über einen Pull Request geprüft und nach `main` übernommen werden.

## 8. Commit kontrollieren

Nach dem Commit sollte kontrolliert werden:

- Commit vorhanden?
- richtige Commit-Nachricht?
- richtige Datei geändert?
- richtiger Branch?
- erwarteter Inhalt vorhanden?

Die Commit-Historie kann über den Bereich **Commits** des Repositorys aufgerufen werden.

## 9. Commit und Dateiänderung

Ein Commit ist nicht einfach eine Kopie einer einzelnen Datei.

Git speichert die Änderungen am Repository-Stand.

Beispielsweise können in einem Commit mehrere Dateien enthalten sein.

Bei direkter Bearbeitung einer einzelnen Datei in GitHub betrifft der Commit häufig nur diese Änderung.

## 10. Merksatz

> Ein Commit ist ein nachvollziehbar gespeicherter Änderungspunkt in der Git-Historie.

Ein Commit sollte deshalb immer eine klare und verständliche Aussage darüber enthalten, was geändert wurde.