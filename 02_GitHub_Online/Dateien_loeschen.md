# Datei direkt in GitHub löschen

## 1. Zweck

Dieses HowTo beschreibt, wie eine Datei direkt über die GitHub-Weboberfläche aus einem Repository entfernt wird.

## 2. Voraussetzungen

- Zugriff auf das Repository
- Berechtigung zum Ändern des Repositorys
- Prüfung, dass die Datei tatsächlich nicht mehr benötigt wird

## 3. Datei auswählen

1. Repository öffnen.
2. Zum Speicherort der Datei navigieren.
3. Die Datei öffnen.
4. Die Löschfunktion auswählen.

## 4. Löschung prüfen

Vor dem Commit sollte geprüft werden:

- Ist es wirklich die richtige Datei?
- Wird die Datei noch benötigt?
- Gibt es Links auf diese Datei?
- Wird die Datei von anderen Dokumenten referenziert?
- Gibt es einen fachlichen oder technischen Grund für ihre Aufbewahrung?

## 5. Commit durchführen

Die Löschung wird über einen Commit gespeichert.

Beispiel:

```text id="4cqg9m"
Remove obsolete documentation
```

## 6. Ergebnis kontrollieren

Nach dem Commit prüfen:

- Datei nicht mehr im aktuellen Repository-Stand vorhanden
- Commit in der Historie vorhanden
- gegebenenfalls betroffene Links korrigiert

## 7. Ist eine gelöschte Datei endgültig verloren?

Nein.

Eine über Git gelöschte Datei kann grundsätzlich über die Git-Historie wiedergefunden werden, sofern der entsprechende Commit weiterhin vorhanden ist.

Das bedeutet jedoch nicht, dass Dateien bedenkenlos gelöscht werden sollten.

Insbesondere vertrauliche oder sicherheitsrelevante Daten dürfen nicht einfach mit der Annahme gelöscht werden, dass sie damit aus der Git-Historie verschwunden sind.

## 8. Verzeichnisse

Wird die letzte Datei eines Verzeichnisses gelöscht, verschwindet das Verzeichnis ebenfalls aus der sichtbaren Repository-Struktur.

Git verwaltet keine leeren Verzeichnisse.

## 9. Wann ist Online-Löschen sinnvoll?

Die direkte Löschung eignet sich insbesondere für:

- veraltete Dokumentationsdateien
- versehentlich angelegte Dateien
- nicht mehr benötigte einzelne Dateien

Bei umfangreichen Bereinigungen sollte die Änderung lokal geplant und durchgeführt werden.

## 10. Merksatz

> Das Löschen einer Datei entfernt sie aus dem aktuellen Repository-Stand, nicht automatisch aus der Git-Historie.