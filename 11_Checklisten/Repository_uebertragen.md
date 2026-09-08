# Checkliste – Lokales Repository nach GitHub übertragen

## 1. Ausgangssituation

- [ ] Lokales Repository vorhanden
- [ ] Git funktioniert
- [ ] Repository enthält die gewünschten Dateien
- [ ] Arbeitsverzeichnis geprüft

## 2. Lokalen Stand prüfen

```powershell
git status
```

- [ ] Richtiger Ordner geöffnet
- [ ] Richtiger Branch geprüft
- [ ] Änderungen geprüft
- [ ] Keine unerwünschten Dateien vorhanden

## 3. GitHub Repository

- [ ] Neues GitHub Repository erstellt
- [ ] Repository-Name geprüft
- [ ] Sichtbarkeit geprüft
- [ ] Repository-URL kopiert

## 4. Remote konfigurieren

```powershell
git remote -v
```

- [ ] Bestehendes Remote geprüft
- [ ] Remote-Adresse korrekt
- [ ] Bei Bedarf `origin` eingerichtet oder angepasst

## 5. Änderungen committen

```powershell
git add .
git status
git commit -m "Initial repository import"
```

- [ ] Dateien geprüft
- [ ] Keine Secrets enthalten
- [ ] Commit erstellt

## 6. Nach GitHub übertragen

```powershell
git push -u origin main
```

- [ ] Push erfolgreich
- [ ] GitHub Repository geöffnet
- [ ] Dateien sichtbar

## 7. Abschlusskontrolle

```powershell
git status
```

- [ ] Working Tree sauber
- [ ] Richtiger Branch
- [ ] Remote korrekt
- [ ] GitHub enthält erwarteten Stand