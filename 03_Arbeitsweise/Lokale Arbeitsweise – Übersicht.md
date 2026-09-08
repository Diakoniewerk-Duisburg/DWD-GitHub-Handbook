# Lokale Arbeitsweise mit Git

Dieser Bereich beschreibt den typischen Arbeitsablauf mit einem lokal vorhandenen Git-Repository.

Die lokale Arbeitsweise ist insbesondere dann sinnvoll, wenn mehrere Dateien bearbeitet, Skripte entwickelt, Änderungen getestet oder größere Umstrukturierungen vorgenommen werden.

## Standardablauf

Der grundlegende Ablauf lautet:

```text
git pull
   ↓
Arbeiten
   ↓
git status
   ↓
git diff
   ↓
git add
   ↓
git diff --staged
   ↓
git commit
   ↓
git push
   ↓
Kontrolle
```

## Anleitungen

### Repository klonen

Wenn ein Repository von GitHub lokal bereitgestellt werden soll:

[Repository klonen](Repository_klonen.md)

---

### Änderungen prüfen

Vor einem Commit sollte immer geprüft werden, was geändert wurde:

[Änderungen prüfen](Aenderungen_pruefen.md)

---

### Commit erstellen

Änderungen werden zunächst für den Commit vorgemerkt und anschließend lokal committed:

[Commit erstellen](Commit_erstellen.md)

---

### Repository synchronisieren

Der vollständige Ablauf von `git pull` und `git push` wird hier beschrieben:

[Repository synchronisieren](Repository_synchronisieren.md)

## Die vier wichtigen Zustände

Für das Verständnis von Git ist die Unterscheidung zwischen diesen Zuständen entscheidend:

```text
Arbeitsverzeichnis
      ↓ git add
Staging
      ↓ git commit
lokales Repository
      ↓ git push
GitHub Repository
```

### Arbeitsverzeichnis

Hier befinden sich die Dateien, an denen gearbeitet wird.

### Staging

Hier werden Änderungen für den nächsten Commit vorgemerkt.

### Lokales Repository

Hier befinden sich die lokalen Commits und die Git-Historie.

### GitHub Repository

Hier befindet sich das Remote-Repository.

## Merksatz

> `git add` bereitet vor.  
> `git commit` speichert lokal.  
> `git push` überträgt zu GitHub.  
> `git pull` holt Änderungen von GitHub.

## Vor jedem Push

Mindestens diese Prüfungen durchführen:

```powershell
git status
git diff
git diff --staged
```

Zusätzlich sollte geprüft werden:

```powershell
git remote -v
git branch --show-current
```

Damit ist bekannt:

- was geändert wurde,
- was committed werden soll,
- wohin gepusht wird,
- welcher Branch verwendet wird.

## Standardabschluss

Nach einem erfolgreichen Push:

```powershell
git status
```

Ein sauberer Zustand ist beispielsweise:

```text
nothing to commit, working tree clean
```

Das bedeutet, dass lokal keine offenen Änderungen mehr vorhanden sind.