# git init

## Zweck

Mit `git init` wird ein bestehendes lokales Verzeichnis in ein neues lokales Git-Repository umgewandelt.

Der Befehl wird insbesondere verwendet, wenn ein Projekt bereits lokal existiert, aber bisher noch nicht von Git verwaltet wird.

## Grundsyntax

```powershell
git init
```

Der Befehl wird im Verzeichnis ausgeführt, das zum Git-Repository werden soll.

## Beispiel

```powershell
cd "D:\GitHub\Mein-Projekt"
git init
```

Git legt dabei den versteckten Ordner `.git` an. Dieser enthält unter anderem die lokale Git-Historie, Konfiguration und Referenzen.

## Danach prüfen

```powershell
git status
```

Bei einem neuen Repository kann beispielsweise angezeigt werden:

```text
No commits yet
Untracked files:
```

Das bedeutet, dass Git erfolgreich initialisiert wurde, aber noch kein Commit existiert.

## Hauptbranch auf `main` setzen

```powershell
git branch -M main
git branch --show-current
```

Erwartetes Ergebnis:

```text
main
```

## Erste Dateien committen

```powershell
git add .
git diff --staged
git commit -m "Initial repository import"
```

Damit existiert der erste Commit zunächst lokal.

## GitHub anbinden

`git init` stellt noch keine Verbindung zu GitHub her.

Dazu wird ein Remote eingerichtet:

```powershell
git remote add origin https://github.com/Benutzername/Mein-Projekt.git
git remote -v
```

Anschließend kann das lokale Repository übertragen werden:

```powershell
git push -u origin main
```

## `git init` oder `git clone`?

| Situation | Befehl |
|---|---|
| Lokaler Ordner existiert, noch kein Git | `git init` |
| GitHub-Repository existiert bereits | `git clone` |
| Lokales Repository erstmals zu GitHub übertragen | `git init` + Remote + Commit + Push |

## Typischer Ablauf

```powershell
cd "D:\GitHub\Mein-Projekt"
git init
git status
git add .
git diff --staged
git commit -m "Initial repository import"
git branch -M main
git remote add origin https://github.com/Benutzername/Mein-Projekt.git
git push -u origin main
```

## Wichtige Hinweise

`git init` sollte im richtigen Projektverzeichnis ausgeführt werden. Vorher kann mit folgendem Befehl geprüft werden, wo man sich befindet:

```powershell
Get-Location
```

Wenn bereits ein Git-Repository vorhanden ist, sollte zunächst mit `git status` geprüft werden, bevor erneut initialisiert wird.

Wenn GitHub bereits separat initialisiert wurde, können zwei unabhängige Historien entstehen. In diesem Fall nicht blind mit `git push --force` arbeiten, sondern zuerst den Zustand analysieren.

## Merksatz

> **`git init` macht einen lokalen Ordner zu einem Git-Repository. Es verbindet ihn noch nicht mit GitHub.**
