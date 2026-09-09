# Praxisbeispiel 03 – Lokale Änderung committen und pushen

## Situation

Im lokalen Repository wurde eine oder mehrere Dateien geändert.

Die Änderungen sollen nachvollziehbar gespeichert und anschließend zu GitHub übertragen werden.

Beispiel:

```text
D:\GitHub\Mein-Projekt
        │
        └── README.md geändert
```

## 1. Repository öffnen

```powershell
cd "D:\GitHub\Mein-Projekt"
```

## 2. Vorhandene Änderungen prüfen

```powershell
git status
git diff
```

Prüfen:

- Was wurde geändert?
- Ist die Änderung beabsichtigt?
- Sind nur die erwarteten Dateien betroffen?

## 3. Änderung für den Commit vormerken

Eine einzelne Datei:

```powershell
git add README.md
```

Oder mehrere bewusst ausgewählte Dateien:

```powershell
git add Datei1.md Datei2.md
```

Bei einem größeren, bewusst geprüften Änderungsumfang kann auch:

```powershell
git add .
```

verwendet werden.

## 4. Staging prüfen

```powershell
git status
git diff --staged
```

`git diff --staged` zeigt die Änderungen, die tatsächlich in den nächsten Commit aufgenommen werden.

## 5. Commit erstellen

```powershell
git commit -m "Update project documentation"
```

Eine Commit-Nachricht sollte beschreiben, **was geändert wurde**.

## 6. Commit kontrollieren

```powershell
git log --oneline -3
git status
```

## 7. Push durchführen

```powershell
git push
```

Falls für den Branch noch kein Upstream eingerichtet wurde:

```powershell
git push -u origin main
```

## 8. Push kontrollieren

```powershell
git status
```

Anschließend das Repository auf GitHub öffnen und prüfen:

- Dateiänderung vorhanden?
- Commit vorhanden?
- richtiger Branch?
- erwarteter Inhalt?

# Gesamtablauf

```powershell
cd "D:\GitHub\Mein-Projekt"

git status
git diff

git add .
git status
git diff --staged
git commit -m "Update project documentation"
git log --oneline -3
git status
git push
git status
```

# Was passiert dabei?

```text
Datei ändern
    ↓
Working Tree
    ↓
git add
    ↓
Staging
    ↓
git commit
    ↓
lokale Git-Historie
    ↓
git push
    ↓
GitHub
```

## Merksatz

> **Commit speichert lokal. Push überträgt zu GitHub.**

Ein erfolgreicher Commit bedeutet deshalb noch nicht, dass die Änderung bereits auf GitHub vorhanden ist.
