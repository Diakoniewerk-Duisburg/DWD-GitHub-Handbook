# Git Befehlsreferenz

## Zweck

Dieser Bereich dient als schnelle Referenz für die wichtigsten Git-Befehle.

Die ausführlichen Erklärungen zur Arbeitsweise befinden sich im Bereich `03_Arbeitsweise`.

## Häufig verwendete Befehle

| Befehl | Zweck |
|---|---|
| `git status` | Zustand des lokalen Repositorys anzeigen |
| `git add` | Änderungen für einen Commit vormerken |
| `git commit` | vorgemerkte Änderungen lokal speichern |
| `git pull` | Änderungen von GitHub abrufen |
| `git push` | lokale Commits nach GitHub übertragen |
| `git clone` | Repository lokal klonen |
| `git diff` | Änderungen anzeigen |
| `git log` | Commit-Historie anzeigen |
| `git branch` | Branches anzeigen oder verwalten |
| `git remote` | Verbindungen zu entfernten Repositorys anzeigen oder verwalten |

## Standardablauf

```powershell
git pull
git status

# Dateien bearbeiten

git status
git diff

git add .
git diff --staged

git commit -m "Beschreibung der Änderung"

git push

git status
```

## Grundregel

> `status` → prüfen  
> `add` → vorbereiten  
> `commit` → speichern  
> `push` → übertragen  
> `pull` → aktualisieren