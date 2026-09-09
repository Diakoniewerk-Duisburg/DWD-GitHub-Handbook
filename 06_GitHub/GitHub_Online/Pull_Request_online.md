# Pull Request direkt in GitHub erstellen

## 1. Zweck

Ein Pull Request (PR) ermöglicht es, Änderungen eines Branches zur Prüfung und Übernahme in einen anderen Branch vorzuschlagen.

Ein typischer Anwendungsfall ist:

```text
documentation-update
        │
        ▼
   Pull Request
        │
        ▼
       main
```

## 2. Warum Pull Requests verwenden?

Ein Pull Request schafft einen kontrollierten Übergang zwischen zwei Branches.

Dabei können:

- Änderungen betrachtet werden
- Unterschiede geprüft werden
- Kommentare hinterlassen werden
- Änderungen diskutiert werden
- Prüfungen ausgeführt werden
- Änderungen anschließend übernommen werden

## 3. Typischer Ablauf

```text
Branch erstellen
      │
      ▼
Änderung durchführen
      │
      ▼
Commit erstellen
      │
      ▼
Pull Request erstellen
      │
      ▼
Änderungen prüfen
      │
      ▼
Freigabe
      │
      ▼
Merge nach main
```

## 4. Pull Request erstellen

Nach dem Commit auf dem Arbeitsbranch kann GitHub die Möglichkeit anbieten, einen Pull Request zu erstellen.

Dabei werden insbesondere festgelegt:

- Ausgangsbranch
- Zielbranch
- Titel
- Beschreibung

Beispiel:

```text
Quelle:
documentation-update

Ziel:
main
```

## 5. Titel

Der Titel sollte kurz beschreiben, was geändert wurde.

Beispiel:

```text
Update GitHub documentation
```

## 6. Beschreibung

Die Beschreibung sollte bei größeren Änderungen erklären:

- Was wurde geändert?
- Warum wurde es geändert?
- Welche Bereiche sind betroffen?
- Gibt es offene Punkte?
- Was sollte geprüft werden?

## 7. Änderungen prüfen

Vor dem Merge sollte der Pull Request geprüft werden.

Dabei insbesondere:

- Sind die richtigen Dateien geändert?
- Gibt es unbeabsichtigte Änderungen?
- Sind Links korrekt?
- Ist die Dokumentation verständlich?
- Gibt es Konflikte?
- Sind automatische Prüfungen erfolgreich?

## 8. Review

Ein Pull Request kann durch eine andere Person geprüft werden.

Bei einer Einzelperson kann der Pull Request auch als eigener Kontrollmechanismus genutzt werden.

Das Ziel ist dabei nicht zwingend eine formale Freigabe durch eine zweite Person, sondern die **Trennung von Bearbeitung und Übernahme**.

## 9. Merge

Nach erfolgreicher Prüfung kann der Pull Request in den Zielbranch übernommen werden.

Beispiel:

```text
documentation-update
        │
        │ Merge
        ▼
       main
```

Danach enthält `main` die Änderungen.

## 10. Nach dem Merge

Nach erfolgreichem Merge sollte geprüft werden:

- Änderung in `main` vorhanden?
- Inhalt korrekt?
- Pull Request abgeschlossen?
- Arbeitsbranch noch erforderlich?

Nicht mehr benötigte Branches können anschließend gelöscht werden.

## 11. Pull Request versus direkter Commit

### Direkter Commit

```text
Datei
 ↓
Commit
 ↓
main
```

Schnell und einfach.

Geeignet für kleine, unkritische Änderungen, sofern erlaubt.

### Pull Request

```text
Datei
 ↓
Branch
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

Geeignet für kontrollierte Änderungen.

## 12. Merksatz

> Ein Pull Request ist ein Vorschlag, Änderungen aus einem Branch in einen anderen Branch zu übernehmen.