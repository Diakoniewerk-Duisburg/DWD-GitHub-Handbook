# Repository klonen

## 1. Zweck

Beim Klonen wird ein GitHub-Repository als vollständige lokale Arbeitskopie auf den eigenen Computer übertragen.

Dabei wird nicht nur der aktuelle Dateistand übernommen, sondern auch die Git-Versionshistorie.

## 2. Voraussetzungen

- Git ist lokal installiert.
- Zugriff auf das gewünschte GitHub-Repository besteht.
- Ein geeigneter lokaler Speicherort ist vorhanden.

## 3. Repository-URL ermitteln

Das gewünschte Repository auf GitHub öffnen.

Über **Code** wird die Repository-Adresse angezeigt.

Beispiel:

```text
https://github.com/Organisation/Repository.git
```

Die genaue Adresse des Repositorys verwenden.

## 4. Lokalen Zielordner auswählen

In PowerShell in den gewünschten übergeordneten Ordner wechseln.

Beispiel:

```powershell
cd "D:\GitHub"
```

## 5. Repository klonen

Der grundlegende Befehl lautet:

```powershell
git clone <Repository-URL>
```

Beispiel:

```powershell
git clone https://github.com/Organisation/Repository.git
```

Git erstellt dabei normalerweise einen neuen Ordner mit dem Repository-Namen.

## 6. In das Repository wechseln

Anschließend:

```powershell
cd "Repository"
```

## 7. Repository prüfen

Mit:

```powershell
git status
```

kann geprüft werden, ob das Repository korrekt eingerichtet wurde.

Zusätzlich:

```powershell
git remote -v
```

zeigt die Verbindung zum entfernten Repository.

## 8. Was wurde beim Klonen erstellt?

Nach dem Klonen existiert lokal unter anderem:

```text
Repository/
│
├── Dateien
├── Dokumentation
└── .git/
```

Der Ordner `.git` enthält die lokale Git-Verwaltung einschließlich der Versionshistorie.

## 9. Typischer Ablauf

```text
GitHub Repository
       │
       │ git clone
       ▼
Lokaler Computer
       │
       ▼
Lokales Repository
```

## 10. Nach dem Klonen

Das Repository ist anschließend eine normale lokale Git-Arbeitskopie.

Änderungen können durchgeführt und anschließend mit:

```powershell
git add
git commit
git push
```

nach GitHub übertragen werden.

## 11. Merksatz

> `git clone` erstellt eine lokale Arbeitskopie eines bestehenden Git-Repositorys einschließlich seiner Git-Historie.