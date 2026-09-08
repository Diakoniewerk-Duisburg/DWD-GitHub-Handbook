# `nothing to commit, working tree clean`

## 1. Meldung

Eine typische Ausgabe lautet:

```text
nothing to commit, working tree clean
```

## 2. Bedeutung

Git meldet damit, dass im lokalen Working Tree keine nicht gespeicherten Änderungen vorhanden sind.

Es gibt aktuell nichts, was noch committed werden müsste.

## 3. Das ist normalerweise kein Fehler

Die Meldung bedeutet grundsätzlich:

```text
Keine offenen lokalen Änderungen
          ↓
Working Tree sauber
```

Das Repository kann sich damit in einem völlig normalen Zustand befinden.

## 4. Typischer Ablauf

Nach:

```powershell
git add .
git commit -m "Update documentation"
```

kann anschließend:

```powershell
git status
```

folgende Meldung liefern:

```text
nothing to commit, working tree clean
```

Das ist in diesem Fall das erwartete Ergebnis.

## 5. Wichtig: Commit ≠ Push

Ein sauberer Working Tree bedeutet nicht automatisch, dass GitHub ebenfalls den gewünschten Stand enthält.

Beispiel:

```text
Lokaler Commit
      │
      ▼
Working Tree clean
      │
      │ aber noch kein Push
      ▼
GitHub möglicherweise älter
```

Daher bei Bedarf:

```powershell
git push
```

## 6. Wenn eine Änderung erwartet wurde

Wenn eine Datei geändert wurde, Git aber keine Änderung erkennt, sollte geprüft werden:

```powershell
git status
```

und:

```powershell
git diff
```

Mögliche Ursachen:

- Datei wurde gar nicht geändert
- Änderung wurde bereits committed
- Änderung wurde verworfen
- falsches Repository geöffnet
- falsche Datei bearbeitet
- Änderung wurde bereits von GitHub übernommen

## 7. Commit-Historie prüfen

```powershell
git log --oneline -5
```

Damit kann geprüft werden, ob die erwartete Änderung bereits committed wurde.

## 8. Merksatz

> `nothing to commit, working tree clean` bedeutet zunächst: Dein lokales Repository hat keine offenen Änderungen.