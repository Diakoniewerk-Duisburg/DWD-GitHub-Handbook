# git status

## Zweck

`git status` zeigt den aktuellen Zustand des lokalen Git-Repositorys.

## Syntax

```powershell
git status
```

## Typische Informationen

Der Befehl zeigt unter anderem:

- aktuellen Branch
- geänderte Dateien
- neue Dateien
- gelöschte Dateien
- gestagte Änderungen
- nicht gestagte Änderungen
- Informationen zur Synchronisation mit dem Remote-Repository

## Beispiel

```powershell
git status
```

Mögliche Ausgabe:

```text
On branch main
Changes not staged for commit:
  modified: README.md
```

Das bedeutet, dass `README.md` geändert wurde, aber noch nicht für einen Commit vorgemerkt wurde.

## Sauberer Zustand

Eine typische Ausgabe bei einem sauberen Working Tree ist:

```text
nothing to commit, working tree clean
```

Das bedeutet, dass keine lokalen Änderungen vorhanden sind, die noch committed werden müssen.

## Wichtig

`git status` verändert keine Dateien und erstellt keinen Commit.

Es ist daher ein sicherer und empfehlenswerter Befehl zur Kontrolle.

## Merksatz

> Wenn du nicht weißt, was gerade im Repository los ist: `git status`.