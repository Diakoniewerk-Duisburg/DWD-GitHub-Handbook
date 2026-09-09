# Änderungen prüfen

## 1. Zweck

Vor einem Commit sollten Änderungen immer geprüft werden.

Git stellt dafür mehrere Befehle zur Verfügung.

## 2. Status prüfen

Der wichtigste erste Befehl:

```powershell
git status
```

Er zeigt unter anderem:

- geänderte Dateien
- neue Dateien
- gelöschte Dateien
- gestagte Änderungen
- nicht gestagte Änderungen
- den aktuellen Branch

## 3. Inhaltliche Änderungen anzeigen

Mit:

```powershell
git diff
```

werden Änderungen angezeigt, die noch nicht gestaged wurden.

## 4. Gestagte Änderungen anzeigen

Nach:

```powershell
git add .
```

kann mit:

```powershell
git diff --staged
```

geprüft werden, welche Änderungen tatsächlich für den Commit vorgemerkt wurden.

## 5. Empfohlene Reihenfolge

```powershell
git status
git diff
git add .
git diff --staged
```

Erst danach sollte der Commit erstellt werden.

## 6. Warum diese Kontrolle wichtig ist

Insbesondere bei:

```powershell
git add .
```

können mehrere Dateien für den Commit vorgemerkt werden.

Daher sollte geprüft werden:

- Gehören alle Änderungen zusammen?
- Ist eine Datei versehentlich verändert worden?
- Sind temporäre Dateien enthalten?
- Sind lokale Konfigurationsdateien enthalten?
- Wurden vertrauliche Informationen hinzugefügt?

## 7. Beispiel

Angenommen, Git zeigt:

```text
modified: README.md
modified: Dokumentation.md
```

Dann sollte geprüft werden, ob beide Änderungen gemeinsam in den Commit gehören.

Falls nur eine Datei committen werden soll:

```powershell
git add README.md
```

## 8. Merksatz

> `git status` zeigt, was sich geändert hat. `git diff` zeigt, was genau geändert wurde.