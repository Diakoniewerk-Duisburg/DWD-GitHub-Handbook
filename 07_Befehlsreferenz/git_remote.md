# git remote

## Zweck

`git remote` verwaltet die Verbindungen eines lokalen Git-Repositorys zu entfernten Repositorys.

Das ist besonders wichtig, wenn ein lokales Repository mit GitHub verbunden ist.

## Remote anzeigen

```powershell
git remote
```

Eine typische Ausgabe:

```text
origin
```

`origin` ist der übliche Standardname für das entfernte Repository.

## Remote-URL anzeigen

```powershell
git remote -v
```

Beispiel:

```text
origin  https://github.com/Organisation/Repository.git (fetch)
origin  https://github.com/Organisation/Repository.git (push)
```

Damit lässt sich schnell kontrollieren, mit welchem GitHub-Repository das lokale Repository verbunden ist.

## Warum ist diese Prüfung wichtig?

Insbesondere bei mehreren Projekten kann versehentlich im falschen lokalen Repository gearbeitet werden.

Vor einem Push sollte deshalb bei Unsicherheit geprüft werden:

```powershell
git remote -v
```

Damit wird die tatsächlich hinterlegte Remote-Adresse angezeigt.

## Remote hinzufügen

Ein Remote kann beispielsweise mit:

```powershell
git remote add origin <Repository-URL>
```

angelegt werden.

## Remote ändern

Eine bestehende URL kann geändert werden:

```powershell
git remote set-url origin <Repository-URL>
```

## Remote entfernen

```powershell
git remote remove origin
```

## Typischer Prüfablauf

```powershell
git status
git remote -v
git branch
```

Damit können drei wichtige Fragen beantwortet werden:

1. Wie ist mein lokales Repository beschaffen?
2. Mit welchem GitHub-Repository bin ich verbunden?
3. Auf welchem Branch arbeite ich?

## Merksatz

> `git remote -v` zeigt, wohin `git pull` und `git push` gehen.