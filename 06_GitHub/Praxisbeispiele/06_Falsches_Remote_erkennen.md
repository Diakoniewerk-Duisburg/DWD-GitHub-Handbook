# Praxisbeispiel 06 – Falsches Remote erkennen

## Situation

Ein lokales Repository soll nach GitHub übertragen werden. Vor dem Push fällt auf, dass `origin` möglicherweise auf das falsche Repository zeigt.

Beispiel:

```powershell
git remote -v
```

zeigt:

```text
origin  https://github.com/AlterAccount/Altes-Projekt.git (fetch)
origin  https://github.com/AlterAccount/Altes-Projekt.git (push)
```

Das gewünschte Ziel ist jedoch:

```text
https://github.com/NeuerAccount/Neues-Projekt.git
```

## 1. Nicht pushen

Solange das Ziel nicht eindeutig ist:

> **Keinen Push durchführen.**

## 2. Lokalen Pfad prüfen

```powershell
Get-Location
```

Damit wird zunächst festgestellt, welches lokale Projekt tatsächlich geöffnet ist.

## 3. Git-Repository prüfen

```powershell
git status
git branch --show-current
```

## 4. Remote prüfen

```powershell
git remote -v
```

Fetch und Push sollten bei einer normalen Konfiguration auf dasselbe Repository zeigen.

## 5. Remote korrigieren

Wenn `origin` bereits existiert:

```powershell
git remote set-url origin https://github.com/NeuerAccount/Neues-Projekt.git
```

Danach unbedingt erneut:

```powershell
git remote -v
```

prüfen.

## 6. Alternative: Remote neu anlegen

Wenn kein `origin` vorhanden ist:

```powershell
git remote add origin https://github.com/NeuerAccount/Neues-Projekt.git
```

Danach:

```powershell
git remote -v
```

## 7. Vor dem Push nochmals prüfen

```powershell
git status
git branch --show-current
git remote -v
```

Erst wenn alle drei Angaben korrekt sind, darf der Push erfolgen.

```powershell
git push -u origin main
```

## 8. Warum diese Prüfung wichtig ist

Ein lokales Repository weiß nicht anhand des Projektordners, welches GitHub-Repository „gemeint“ ist.

Die Zuordnung wird über das Remote hergestellt.

Vereinfacht:

```text
Lokales Repository
        │
        │ origin
        ▼
GitHub Repository
```

`origin` ist eine konfigurierte Verbindung und keine automatische Projektidentifikation.

## 9. Typischer Praxisfall

Ein Projekt wurde aus einem bestehenden Repository kopiert und das `.git`-Verzeichnis wurde dabei ebenfalls übernommen.

Das neue lokale Projekt kann dadurch noch auf das alte GitHub-Repository zeigen.

Prüfung:

```powershell
git remote -v
```

Wenn dort das alte Repository steht:

> **Nicht pushen.**

Remote zuerst korrigieren.

## 10. Endkontrolle

```powershell
git remote -v
git branch --show-current
git status
```

Erst danach:

```powershell
git push
```

# Merksatz

> **Vor jedem Push muss klar sein: In welchem Repository bin ich, auf welchem Branch bin ich und wohin zeigt `origin`?**
