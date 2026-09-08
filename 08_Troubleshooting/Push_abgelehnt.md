# Push abgelehnt

## 1. Typische Meldung

Ein `git push` kann beispielsweise mit einer Meldung wie dieser abgelehnt werden:

```text
! [rejected] main -> main
```

Häufig wird zusätzlich darauf hingewiesen, dass das Remote-Repository Änderungen enthält, die lokal noch nicht vorhanden sind.

## 2. Bedeutung

Git verhindert damit, dass lokale Änderungen den aktuelleren Stand des Remote-Repositorys überschreiben.

Beispiel:

```text
GitHub:
A ─ B ─ C

Lokal:
A ─ B ─ D
```

Beide Seiten haben unterschiedliche Änderungen.

## 3. Nicht einfach erneut pushen

Ein wiederholtes:

```powershell
git push
```

löst das Problem normalerweise nicht.

Zuerst muss der Unterschied zwischen lokalem und Remote-Stand verstanden werden.

## 4. Zustand prüfen

```powershell
git status
```

Remote kontrollieren:

```powershell
git remote -v
```

Branch prüfen:

```powershell
git branch
```

## 5. Remote-Änderungen abrufen

In einer normalen Situation:

```powershell
git pull
```

Git versucht anschließend, die Änderungen zusammenzuführen.

## 6. Konflikt möglich

Wenn Git die Änderungen nicht automatisch zusammenführen kann, entsteht ein Merge Conflict.

Dann nicht einfach weitere Befehle ausführen, sondern zunächst den Konflikt untersuchen.

Siehe:

`Merge_Conflict.md`

## 7. Nach erfolgreicher Integration

Wenn die lokalen und Remote-Änderungen erfolgreich zusammengeführt wurden:

```powershell
git push
```

## 8. Sonderfall: Remote enthält bewusst andere Historie

Wenn ein Repository beispielsweise neu erstellt und anschließend mit einem bereits vorhandenen lokalen Repository verbunden wurde, kann die Historie unterschiedlich sein.

Dieser Fall muss gesondert bewertet werden.

Es sollte **nicht** automatisch mit `--force` gearbeitet werden.

## 9. Merksatz

> Ein abgelehnter Push ist zunächst ein Schutzmechanismus. Erst die Ursache klären, dann synchronisieren.