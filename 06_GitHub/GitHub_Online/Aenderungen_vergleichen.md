# Änderungen in GitHub vergleichen

## 1. Zweck

Git und GitHub speichern Änderungen nachvollziehbar.

Über GitHub können Änderungen zwischen verschiedenen Ständen betrachtet und miteinander verglichen werden.

Dies ist insbesondere bei Dokumentationsänderungen wichtig.

## 2. Warum Änderungen vergleichen?

Vor dem Übernehmen einer Änderung sollte möglichst nachvollziehbar sein:

- welche Zeilen geändert wurden
- welche Dateien betroffen sind
- was hinzugefügt wurde
- was entfernt wurde
- ob unbeabsichtigte Änderungen enthalten sind

## 3. Commit anzeigen

In der Commit-Historie kann ein einzelner Commit geöffnet werden.

Dort zeigt GitHub die Änderungen dieses Commits an.

Typischerweise wird zwischen:

```text id="5g2h0b"
hinzugefügt
```

und:

```text id="m1s2f7"
entfernt
```

unterschieden.

## 4. Änderungen vor dem Commit prüfen

Bei Änderungen über die GitHub-Weboberfläche sollte vor dem Commit geprüft werden, ob tatsächlich nur die gewünschten Inhalte verändert wurden.

Besonders wichtig bei:

- Markdown-Dateien
- Konfigurationsdateien
- JSON-Dateien
- YAML-Dateien
- Skripten

## 5. Commit-Historie

Die Commit-Historie ermöglicht die zeitliche Nachverfolgung der Änderungen.

Beispiel:

```text id="i6y7ww"
Commit 3
   │
   ├── Dokumentation erweitert
   │
Commit 2
   │
   ├── HowTo korrigiert
   │
Commit 1
   │
   └── Dokumentation erstellt
```

Dadurch kann nachvollzogen werden, wie sich ein Repository entwickelt hat.

## 6. Änderungen zwischen Versionen

Bei Bedarf können unterschiedliche Stände miteinander verglichen werden.

Dies ist hilfreich, wenn beispielsweise festgestellt werden soll:

> Was hat sich zwischen zwei Entwicklungsständen geändert?

oder:

> Welche Änderungen wurden mit diesem Commit eingeführt?

## 7. Praktische Kontrolle

Bei einer Dokumentationsänderung sollte die Kontrolle möglichst folgende Punkte umfassen:

```text id="e0n5uw"
Datei richtig?
      ↓
Inhalt richtig?
      ↓
Formatierung richtig?
      ↓
Keine unbeabsichtigten Änderungen?
      ↓
Commit-Nachricht passend?
      ↓
Commit durchführen
```

## 8. Merksatz

> Vor dem Commit sollte immer klar sein, welche Änderung tatsächlich gespeichert wird.