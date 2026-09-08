# git pull

## Zweck

`git pull` ruft Änderungen aus einem entfernten Repository ab und integriert sie in das lokale Repository.

## Syntax

```powershell
git pull
```

## Typische Verwendung

Vor Beginn einer lokalen Arbeit:

```powershell
git pull
git status
```

Damit wird zunächst der aktuelle Stand abgerufen.

## Beispiel

```text
GitHub:
A ─ B ─ C

Lokal:
A ─ B
```

Nach:

```powershell
git pull
```

kann der lokale Stand beispielsweise wieder enthalten:

```text
A ─ B ─ C
```

## Achtung

Wenn lokal eigene, noch nicht sauber gespeicherte Änderungen vorhanden sind, kann ein `git pull` zu Problemen führen.

Deshalb vorher:

```powershell
git status
```

## Merksatz

> `git pull` bringt Änderungen von GitHub in das lokale Repository.