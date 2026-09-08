# Datei direkt in GitHub anlegen

## 1. Zweck

Dieses HowTo beschreibt, wie eine neue Datei direkt über die GitHub-Weboberfläche angelegt und anschließend als Commit gespeichert wird.

Ein lokales Git-Repository ist für diesen Vorgang nicht erforderlich.

## 2. Voraussetzungen

- GitHub-Konto
- Zugriff auf das gewünschte Repository
- Berechtigung zum Erstellen oder Ändern von Dateien

## 3. Repository öffnen

Das gewünschte Repository in GitHub öffnen.

Anschließend in das Verzeichnis navigieren, in dem die neue Datei angelegt werden soll.

## 4. Datei erstellen

Im Repository:

**Add file → Create new file**

auswählen.

GitHub öffnet anschließend den Editor für eine neue Datei.

## 5. Dateiname und Pfad festlegen

Im Feld für den Dateinamen kann neben dem Dateinamen auch ein Pfad angegeben werden.

Beispiel:

```text
02_GitHub_Online/Neue_Anleitung.md
```

Wenn das Verzeichnis noch nicht existiert, wird es durch die Erstellung der Datei automatisch angelegt.

## 6. Inhalt eintragen

Den gewünschten Inhalt im Editor eingeben.

Bei Markdown-Dateien kann anschließend die Vorschau verwendet werden, um die Darstellung zu kontrollieren.

## 7. Änderung prüfen

Vor dem Speichern prüfen:

- Dateiname korrekt?
- Pfad korrekt?
- Inhalt vollständig?
- Markdown-Struktur korrekt?
- Keine vertraulichen Informationen enthalten?

## 8. Commit erstellen

Am Ende der Seite befindet sich der Bereich zum Speichern der Änderung.

Dort eine aussagekräftige Commit-Nachricht eintragen.

Beispiel:

```text
Add GitHub online documentation
```

Anschließend den Commit durchführen.

## 9. Ergebnis kontrollieren

Nach dem Commit sollte die neu erstellte Datei im Repository sichtbar sein.

Zusätzlich kann die Commit-Historie geöffnet werden.

Dort sollte der neue Commit mit seiner Commit-Nachricht erscheinen.

## 10. Verzeichnisse erstellen

GitHub verwaltet Verzeichnisse über Dateien.

Ein leeres Verzeichnis kann daher nicht als eigenständiges Git-Objekt angelegt werden.

Stattdessen wird eine Datei innerhalb des gewünschten Pfades erstellt.

Beispiel:

```text
04_HowTos/README.md
```

Dadurch entsteht das Verzeichnis:

```text
04_HowTos/
```

## 11. Typische Anwendung

Die direkte Erstellung über GitHub eignet sich insbesondere für:

- neue Dokumentationsdateien
- Markdown-Dateien
- README-Dateien
- kleine Konfigurationsdateien
- einzelne Ergänzungen

Bei größeren Änderungen sollte die lokale Arbeitsweise mit Git verwendet werden.

## 12. Merksatz

> Eine Datei kann direkt in GitHub erstellt, bearbeitet und per Commit versioniert werden. Dafür ist kein lokales Git erforderlich.