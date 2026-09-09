# Datei direkt in GitHub verschieben

## 1. Zweck

Dieses HowTo beschreibt, wie eine bestehende Datei innerhalb eines GitHub-Repositorys in ein anderes Verzeichnis verschoben wird.

Die Verschiebung kann direkt über die GitHub-Weboberfläche durchgeführt werden.

## 2. Voraussetzungen

- Zugriff auf das Repository
- Berechtigung zum Bearbeiten der Datei
- das Zielverzeichnis muss bekannt sein

## 3. Datei öffnen

1. Repository in GitHub öffnen.
2. Zum aktuellen Speicherort der Datei navigieren.
3. Die Datei öffnen.
4. Den Bearbeitungsmodus öffnen.

## 4. Pfad der Datei ändern

Im Bearbeitungsmodus kann der Dateipfad angepasst werden.

Beispiel:

```text id="r9o8c1"
Vorher:

04_HowTos/Neue_Anleitung.md
```

Ändern in:

```text id="2v7bsl"
04_HowTos/01_Repository/Neue_Anleitung.md
```

Durch die Änderung des Pfades wird die Datei in das neue Verzeichnis verschoben.

## 5. Commit durchführen

Die Pfadänderung anschließend als Commit speichern.

Beispiel:

```text id="2l90yq"
Move repository guide
```

## 6. Ergebnis kontrollieren

Nach dem Commit:

1. das neue Verzeichnis öffnen,
2. prüfen, ob die Datei dort vorhanden ist,
3. prüfen, ob die Datei am alten Speicherort nicht mehr vorhanden ist,
4. gegebenenfalls Verweise auf den alten Pfad kontrollieren.

## 7. Verzeichnisse

Git verwaltet keine leeren Verzeichnisse.

Ein Verzeichnis existiert im Repository nur, wenn sich darin mindestens eine versionierte Datei befindet.

Wenn durch das Verschieben die letzte Datei aus einem Verzeichnis entfernt wird, kann dieses Verzeichnis daher anschließend nicht mehr angezeigt werden.

## 8. Verweise beachten

Beim Verschieben einer Dokumentationsdatei können Links oder andere Verweise auf den alten Pfad betroffen sein.

Nach einer Verschiebung sollte deshalb insbesondere geprüft werden:

- Links in `README.md`
- Links aus anderen Markdown-Dateien
- Verweise in Inhaltsverzeichnissen
- relative Pfadangaben

## 9. Wann ist Online-Verschieben sinnvoll?

Die Funktion eignet sich für:

- einzelne Dateien
- kleine Dokumentationsänderungen
- Korrekturen der Repository-Struktur

Bei vielen Dateien oder umfangreichen Umstrukturierungen sollte die Änderung lokal mit Git durchgeführt werden.

## 10. Merksatz

> Beim Verschieben einer Datei in GitHub wird der neue Dateipfad festgelegt und die Änderung anschließend per Commit versioniert.