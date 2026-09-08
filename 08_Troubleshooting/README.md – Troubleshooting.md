# Git und GitHub – Troubleshooting

## 1. Zweck

Dieser Bereich dokumentiert typische Probleme bei der Arbeit mit Git und GitHub.

Die Dokumentation soll helfen, Fehlermeldungen zunächst zu verstehen und anschließend systematisch zu beheben.

## 2. Grundprinzip

Bei einem Problem sollte nicht sofort ein weiterer Git-Befehl ausgeführt werden.

Zunächst den aktuellen Zustand feststellen:

```powershell
git status
```

Anschließend – je nach Problem – beispielsweise:

```powershell
git remote -v
git branch
git log --oneline -5
```

## 3. Systematische Fehleranalyse

```text
Fehlermeldung
      │
      ▼
Was bedeutet sie?
      │
      ▼
Aktuellen Zustand prüfen
      │
      ▼
Ursache bestimmen
      │
      ▼
Gezielte Lösung durchführen
      │
      ▼
Ergebnis kontrollieren
```

## 4. Häufige Situationen

### Lokale Änderungen

- `nothing to commit, working tree clean`
- Änderungen werden nicht angezeigt
- falsche Dateien wurden gestaged

### Synchronisation

- `git push` wird abgelehnt
- `git pull` führt zu Konflikten
- lokales Repository ist nicht aktuell

### Repository

- falsches Remote
- falscher Branch
- Repository wurde im falschen Verzeichnis geöffnet

### Dateien

- LF/CRLF-Warnungen
- Datei versehentlich gelöscht
- Datei wurde an der falschen Stelle angelegt

### Merge

- Merge Conflict
- Änderungen können nicht automatisch zusammengeführt werden

## 5. Sicherheitsregel

Bei unbekannten Fehlermeldungen sollte insbesondere nicht blind mit Befehlen wie:

```powershell
git reset --hard
```

oder:

```powershell
git push --force
```

gearbeitet werden.

Diese Befehle können Änderungen dauerhaft verwerfen oder die Historie eines Remote-Repositorys verändern.

## 6. Grundregel

> Erst verstehen, dann ändern.

Die folgenden Dokumente beschreiben die wichtigsten bekannten Fälle.