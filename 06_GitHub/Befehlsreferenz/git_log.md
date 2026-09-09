# git log

## Zweck

`git log` zeigt die Commit-Historie eines Git-Repositorys.

Damit kann nachvollzogen werden, welche Änderungen in welcher Reihenfolge gespeichert wurden.

## Standardaufruf

```powershell
git log
```

Zeigt die ausführliche Commit-Historie.

## Kompakte Darstellung

Für die tägliche Kontrolle ist häufig übersichtlicher:

```powershell
git log --oneline
```

Beispiel:

```text
a82f31c Update GitHub documentation
4c72b19 Add online workflow
19d8a41 Initial documentation
```

## Nur die letzten Commits anzeigen

Beispielsweise die letzten fünf:

```powershell
git log --oneline -5
```

## Informationen eines Commits

Ein Commit kann anschließend anhand seiner Commit-ID genauer untersucht werden.

Beispiel:

```powershell
git show a82f31c
```

## Wofür ist `git log` praktisch?

Insbesondere für:

- Kontrolle der Änderungshistorie
- Suche nach früheren Änderungen
- Nachvollziehen von Änderungen
- Ermittlung eines bestimmten Commits
- Fehleranalyse

## Merksatz

> `git log` zeigt die Geschichte des Repositorys.