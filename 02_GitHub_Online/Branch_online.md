# Branch direkt in GitHub erstellen und verwenden

## 1. Zweck

Ein Branch ermöglicht es, Änderungen unabhängig vom bestehenden Hauptstand eines Repositorys durchzuführen.

Branches sind ein grundlegendes Werkzeug für eine kontrollierte Zusammenarbeit mit Git und GitHub.

## 2. Was ist ein Branch?

Ein Branch ist vereinfacht gesagt ein eigener Entwicklungszweig innerhalb der Git-Historie.

Der häufig verwendete Hauptbranch heißt:

```text
main
```

Ein zusätzlicher Branch kann beispielsweise für eine Dokumentationsänderung erstellt werden:

```text
main
 │
 └── documentation-update
```

Die Änderungen im neuen Branch verändern `main` zunächst nicht.

## 3. Wann sollte ein Branch verwendet werden?

Ein eigener Branch ist insbesondere sinnvoll bei:

- größeren Änderungen
- mehreren zusammengehörenden Änderungen
- Änderungen mit Prüfbedarf
- Änderungen durch mehrere Personen
- Änderungen, die vor der Übernahme kontrolliert werden sollen
- Vorbereitung eines Pull Requests

Für eine kleine, unkritische Korrektur kann – sofern die Repository-Regeln dies erlauben – direkt auf `main` gearbeitet werden.

## 4. Branch über GitHub erstellen

Ein Branch kann direkt über die GitHub-Weboberfläche erstellt werden.

Ausgangspunkt ist der gewünschte Ausgangsbranch, beispielsweise:

```text
main
```

Über die Branch-Auswahl wird ein neuer Branch angelegt.

Beispiel:

```text
documentation-update
```

Danach kann in diesem Branch gearbeitet werden.

## 5. Geeignete Branch-Namen

Branch-Namen sollten eindeutig und verständlich sein.

Beispiele:

```text
documentation-update
add-github-howto
fix-readme
update-security-guide
```

Branch-Namen sollten möglichst:

- kurz
- beschreibend
- eindeutig
- ohne Umlaute

sein.

## 6. In einem Branch arbeiten

Nach dem Wechsel auf den neuen Branch können Dateien bearbeitet oder erstellt werden.

Beispiel:

```text
main
 │
 └── documentation-update
          │
          ├── Datei ändern
          └── Commit erstellen
```

Die Änderungen befinden sich zunächst nur in diesem Branch.

## 7. Branch kontrollieren

Vor Änderungen sollte immer geprüft werden, auf welchem Branch gearbeitet wird.

Besonders wichtig ist dies bei mehreren parallelen Branches.

Ein versehentlich auf `main` durchgeführter Commit kann einen eigentlich vorgesehenen Prüfprozess umgehen.

## 8. Branch nach Abschluss

Nach Abschluss der Arbeiten gibt es grundsätzlich zwei Möglichkeiten:

### Änderung direkt weiterverwenden

Der Branch bleibt bestehen und wird weiterbearbeitet.

### Änderung über Pull Request übernehmen

Die Änderungen werden zur Prüfung eingereicht und anschließend nach `main` übernommen.

Der zweite Weg ist bei kontrollierten Arbeitsabläufen zu bevorzugen.

## 9. Branch löschen

Ein abgeschlossener Branch kann nach erfolgreicher Übernahme gelöscht werden.

Die darin enthaltenen Commits gehen dadurch nicht automatisch verloren, wenn sie bereits in `main` übernommen wurden.

## 10. Merksatz

> Ein Branch trennt Änderungen vom Hauptstand und ermöglicht einen kontrollierten Änderungsprozess.