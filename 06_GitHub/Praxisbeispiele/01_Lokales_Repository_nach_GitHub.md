# Praxisbeispiel 01 – Lokales Repository nach GitHub übertragen

## Situation

Ein Projekt existiert bereits lokal:

```text
D:\GitHub\Mein-Projekt
```

Das Verzeichnis ist bereits ein Git-Repository.

Nun soll auf GitHub ein neues Repository erstellt und der lokale Stand dorthin übertragen werden.

---

## 1. Lokales Repository öffnen

```powershell
cd "D:\GitHub\Mein-Projekt"
```

## 2. Zustand prüfen

```powershell
git status
git branch --show-current
git remote -v
```

Damit wird festgestellt:

- Bin ich im richtigen Repository?
- Welcher Branch ist aktiv?
- Existiert bereits ein Remote?

## 3. GitHub Repository erstellen

Auf GitHub ein neues Repository erstellen.

Für diesen Fall sollte das Repository möglichst leer angelegt werden.

Beispiel:

```text
Mein-Projekt
```

## 4. Remote einrichten

Wenn noch kein `origin` vorhanden ist:

```powershell
git remote add origin https://github.com/Benutzername/Mein-Projekt.git
```

Kontrolle:

```powershell
git remote -v
```

## 5. Dateien prüfen

```powershell
git status
```

Falls Dateien noch nicht versioniert wurden:

```powershell
git add .
```

Danach:

```powershell
git diff --staged
```

Jetzt wird kontrolliert, was tatsächlich in den Commit aufgenommen wird.

## 6. Commit erstellen

Falls erforderlich:

```powershell
git commit -m "Initial repository import"
```

## 7. Branch kontrollieren

```powershell
git branch --show-current
```

Beispiel:

```text
main
```

## 8. Push

```powershell
git push -u origin main
```

## 9. Kontrolle

Lokal:

```powershell
git status
```

Danach GitHub öffnen und prüfen:

- Dateien vorhanden?
- Verzeichnisstruktur korrekt?
- Branch `main` vorhanden?
- Commit-Historie vorhanden?

# Ergebnis

Das lokale Repository ist jetzt mit GitHub verbunden:

```text
Lokal
  │
  │ git push
  ▼
GitHub
```

Für zukünftige Änderungen reicht grundsätzlich:

```powershell
git pull

# arbeiten

git status
git add .
git diff --staged
git commit -m "Beschreibung der Änderung"
git push
```

# Wichtig

Dieses Beispiel gilt für ein **neues beziehungsweise leeres GitHub-Repository**.

Wenn GitHub bereits eigene Commits enthält, kann die Historie auseinanderlaufen.

Dann nicht einfach:

```powershell
git push --force
```

verwenden.

Stattdessen zunächst die Situation analysieren.

Siehe:

- [Push abgelehnt](05_Push_abgelehnt.md)
- [Push abgelehnt – Troubleshooting](../08_Troubleshooting/Push_abgelehnt.md)
- [HowTo: Lokales Repository nach GitHub übertragen](../04_HowTos/Lokales_Repository_nach_GitHub_uebertragen.md)
