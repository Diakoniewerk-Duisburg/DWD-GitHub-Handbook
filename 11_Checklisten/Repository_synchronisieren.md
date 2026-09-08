# Checkliste – Repository synchronisieren

## 1. Vor der Arbeit

```powershell
git status
```

- [ ] Richtiger Repository-Ordner
- [ ] Richtiger Branch
- [ ] Lokaler Zustand bekannt

## 2. GitHub-Stand abrufen

```powershell
git pull
```

- [ ] Pull erfolgreich
- [ ] Keine Konflikte
- [ ] Lokaler Stand aktuell

## 3. Arbeiten

- [ ] Dateien geändert
- [ ] Nur gewünschte Dateien betroffen

## 4. Änderungen prüfen

```powershell
git status
git diff
```

- [ ] Änderungen bekannt
- [ ] Keine unerwünschten Änderungen

## 5. Commit vorbereiten

```powershell
git add .
git diff --staged
```

- [ ] Richtige Dateien gestaged
- [ ] Inhalt geprüft
- [ ] Keine Secrets enthalten

## 6. Commit

```powershell
git commit -m "Beschreibung der Änderung"
```

- [ ] Commit erfolgreich erstellt

## 7. Push

```powershell
git push
```

- [ ] Push erfolgreich
- [ ] GitHub enthält die Änderung

## 8. Abschluss

```powershell
git status
```

- [ ] Working Tree sauber
- [ ] Erwarteter Branch aktiv
- [ ] Änderung auf GitHub kontrolliert

## Merksatz

> Pull → Arbeiten → Prüfen → Add → Commit → Push → Kontrolle