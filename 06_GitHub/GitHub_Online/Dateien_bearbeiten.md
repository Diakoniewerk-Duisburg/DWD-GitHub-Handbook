# Datei direkt in GitHub bearbeiten

## 1. Zweck

Dieses HowTo beschreibt, wie eine bestehende Datei direkt über die GitHub-Weboberfläche bearbeitet und anschließend versioniert gespeichert wird.

Ein lokales Git-Repository ist für diesen Vorgang nicht erforderlich.

## 2. Voraussetzungen

- GitHub-Konto
- Zugriff auf das Repository
- Berechtigung zum Bearbeiten der Datei

## 3. Datei öffnen

1. Das gewünschte Repository in GitHub öffnen.
2. Zum Verzeichnis der Datei navigieren.
3. Die zu bearbeitende Datei öffnen.

## 4. Bearbeitungsmodus öffnen

Über die Bearbeitungsfunktion der GitHub-Weboberfläche den Editor öffnen.

Die Datei wird anschließend in einem Online-Editor angezeigt.

## 5. Änderung durchführen

Die gewünschte Änderung im Editor durchführen.

Dabei sollte möglichst nur die tatsächlich erforderliche Änderung vorgenommen werden.

Beispiel:

```text
Vorher:

# GitHub

GitHub ist eine Plattform.
```

Nachher:

```text
# GitHub

GitHub ist eine Plattform für Git-Repositorys und Zusammenarbeit.
```

## 6. Änderungen kontrollieren

Vor dem Commit prüfen:

- Wurde die richtige Datei bearbeitet?
- Wurde nur die gewünschte Stelle verändert?
- Ist die Formatierung korrekt?
- Sind Links und Verweise weiterhin gültig?
- Enthält die Änderung vertrauliche Informationen?

Bei Markdown-Dateien sollte zusätzlich die Vorschau kontrolliert werden.

## 7. Commit vorbereiten

Nach der Bearbeitung wird die Änderung als Commit gespeichert.

Dazu eine aussagekräftige Commit-Nachricht verwenden.

Beispiel:

```text
Update GitHub documentation
```

## 8. Commit durchführen

Die Änderung entsprechend den im Repository geltenden Regeln committen.

Bei einer direkten Änderung am Hauptbranch wird der Commit unmittelbar in diesen Branch geschrieben, sofern dies durch die Repository-Einstellungen erlaubt ist.

Alternativ kann die Änderung über einen neuen Branch erfolgen.

## 9. Ergebnis kontrollieren

Nach dem Commit:

1. Datei erneut öffnen.
2. Änderung kontrollieren.
3. Commit-Historie prüfen.
4. Sicherstellen, dass auf dem richtigen Branch gearbeitet wurde.

## 10. Wann ist die Online-Bearbeitung sinnvoll?

Die Bearbeitung direkt in GitHub eignet sich insbesondere für:

- Dokumentationskorrekturen
- Tippfehler
- kleinere Ergänzungen
- README-Dateien
- einzelne Markdown-Dateien
- schnelle Änderungen

Für umfangreiche Änderungen sollte die lokale Bearbeitung mit Git bevorzugt werden.

## 11. Wichtiger Hinweis

Bei einer direkten Änderung in GitHub wird der Commit auf dem GitHub-Repository erstellt.

Wenn zusätzlich ein lokales Repository existiert, kennt dieses den neuen Commit zunächst nicht.

Bei der nächsten lokalen Arbeit muss deshalb auf die Synchronisation geachtet werden.

```text
GitHub
   │
   │ neuer Commit
   ▼
GitHub Repository

Lokales Repository
   │
   │ kennt den Commit noch nicht
   ▼
Synchronisation erforderlich
```

Die Synchronisation wird im Bereich `03_Arbeitsweise` beschrieben.