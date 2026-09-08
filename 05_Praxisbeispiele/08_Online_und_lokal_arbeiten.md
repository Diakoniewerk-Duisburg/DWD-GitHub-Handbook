# Praxisbeispiel 08 – Online und lokal arbeiten

## Situation

Ein GitHub-Repository wird sowohl direkt über die GitHub-Weboberfläche als auch lokal mit Git bearbeitet.

Diese Arbeitsweise ist möglich, erfordert aber Aufmerksamkeit.

## 1. Online wurde eine Änderung durchgeführt

Beispielsweise wurde auf GitHub `README.md` bearbeitet und committed.

Damit enthält GitHub jetzt einen neuen Commit.

## 2. Lokales Repository kennt diesen Commit noch nicht

Vereinfacht:

```text
Lokal:   A ── B ── C
GitHub:  A ── B ── C ── D
```

Der lokale Stand ist damit hinter dem Remote-Stand.

## 3. Vor lokaler Weiterarbeit synchronisieren

Wenn lokal keine offenen Änderungen vorhanden sind:

```powershell
git status
git pull
```

Danach enthält das lokale Repository ebenfalls Commit `D`.

## 4. Lokal weiterarbeiten

Jetzt kann beispielsweise eine weitere Datei geändert werden.

Danach:

```powershell
git status
git diff
```

## 5. Lokalen Commit erstellen

```powershell
git add .
git diff --staged
git commit -m "Add new GitHub workflow guide"
```

## 6. Nach GitHub übertragen

```powershell
git push
```

Jetzt enthält GitHub beide Änderungen.

## 7. Problemfall: Online und lokal wurden gleichzeitig geändert

GitHub:

```text
A ── B ── C ── D
```

Lokal:

```text
A ── B ── C ── E
```

Beide Seiten haben nach Commit `C` unabhängig weitergearbeitet.

Ein Push kann abgelehnt werden.

## 8. Richtige Reaktion

Nicht:

```powershell
git push --force
```

Sondern zunächst:

```powershell
git status
git remote -v
git branch --show-current
```

Danach – sofern der lokale Zustand dies zulässt:

```powershell
git pull
```

Git versucht, die Änderungen zusammenzuführen.

## 9. Konflikt möglich

Wenn dieselbe Stelle in einer Datei unterschiedlich geändert wurde, kann ein Merge Conflict entstehen.

Dann:

```powershell
git status
```

und die betroffenen Dateien prüfen.

Siehe:

[Merge Conflict](../08_Troubleshooting/Merge_Conflict.md)

## 10. Grundregel für gemischte Arbeitsweise

Wenn ein Repository hauptsächlich lokal bearbeitet wird:

> **Vor Beginn der lokalen Arbeit `git pull`.**

Wenn zwischendurch direkt auf GitHub gearbeitet wurde:

> **Vor der nächsten lokalen Arbeit erneut synchronisieren.**

Wenn lokal gearbeitet wurde:

> **Vor dem Push Änderungen prüfen und anschließend `git push`.**

# Empfohlener Ablauf

```text
GitHub
  │
  │ git pull
  ▼
lokal arbeiten
  │
  ▼
git status
  │
  ▼
git diff
  │
  ▼
git add
  │
  ▼
git diff --staged
  │
  ▼
git commit
  │
  ▼
git push
  │
  ▼
GitHub
```

# Merksatz

> **Online und lokal kann man parallel arbeiten – aber man muss wissen, dass dadurch unterschiedliche Stände entstehen können.**

Die sicherste Gewohnheit ist:

> **Vor lokaler Arbeit synchronisieren, vor dem Push prüfen.**
