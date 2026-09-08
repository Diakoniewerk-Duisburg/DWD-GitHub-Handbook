# git clone

## Zweck

`git clone` erstellt eine lokale Kopie eines bestehenden Git-Repositorys.

## Syntax

```powershell
git clone <Repository-URL>
```

## Beispiel

```powershell
git clone https://github.com/Organisation/Repository.git
```

## Was wird übernommen?

Beim Klonen werden unter anderem übernommen:

- Dateien
- Git-Historie
- Branch-Informationen
- Remote-Konfiguration

## Nach dem Klonen

```powershell
cd Repository
git status
```

## Merksatz

> `git clone` erstellt eine lokale Arbeitskopie eines bestehenden Repositorys.