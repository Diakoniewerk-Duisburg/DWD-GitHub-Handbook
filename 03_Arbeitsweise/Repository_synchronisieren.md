# Repository synchronisieren

## 1. Zweck

Ein lokales Git-Repository und das zugehörige GitHub-Repository können unterschiedliche Stände besitzen.

Die Synchronisation sorgt dafür, dass Änderungen zwischen beiden Ständen ausgetauscht werden.

## 2. Grundprinzip

```text
             GitHub
               ▲
               │
             push
               │
               │
        Lokales Repository
               │
               │
             pull
               │
               ▼
             GitHub
```

Vereinfacht gilt:

- `git pull` → Änderungen von GitHub holen
- `git push` → lokale Commits zu GitHub übertragen

## 3. Vor der Arbeit

Vor Beginn einer lokalen Arbeit sollte der aktuelle Zustand geprüft werden:

```powershell
git status
```

Danach kann das Repository aktualisiert werden:

```powershell
git pull
```

## 4. Lokale Änderungen

Anschließend werden die gewünschten Dateien bearbeitet.

Danach:

```powershell
git status
```

und:

```powershell
git diff
```

ausführen.

## 5. Commit erstellen

Nach erfolgreicher Prüfung:

```powershell
git add .
git commit -m "Update documentation"
```

Der Commit befindet sich zunächst lokal.

## 6. Änderungen nach GitHub übertragen

Mit:

```powershell
git push
```

wird der lokale Commit nach GitHub übertragen.

## 7. Abschlusskontrolle

Danach:

```powershell
git status
```

ausführen.

Ein sauberer Zustand kann beispielsweise angezeigt werden als:

```text
nothing to commit, working tree clean
```

Das bedeutet:

- keine nicht gespeicherten lokalen Änderungen
- alle lokalen Änderungen sind committed

Für die vollständige Prüfung, dass auch das Remote-Repository den erwarteten Stand enthält, kann zusätzlich die Synchronisation bzw. der Push-Status kontrolliert werden.

## 8. Standardablauf

Für eine normale lokale Änderung:

```powershell
git pull
git status

# Dateien bearbeiten

git status
git diff

git add .
git diff --staged

git commit -m "Update documentation"

git push

git status
```

## 9. Warum `git pull` vor der Arbeit?

Wenn andere Änderungen nach GitHub übertragen haben, kann das lokale Repository veraltet sein.

Beispiel:

```text
Lokaler Stand:  A ─ B

GitHub:         A ─ B ─ C
```

Nach:

```powershell
git pull
```

ist der lokale Stand wieder auf dem aktuellen Stand.

## 10. Was passiert bei unterschiedlichen Änderungen?

Wenn sowohl lokal als auch auf GitHub Änderungen vorgenommen wurden, die nicht automatisch zusammengeführt werden können, kann ein Merge-Konflikt entstehen.

Beispiel:

```text
GitHub:         A ─ B ─ C
                    \
Lokal:              D
```

Git muss dann klären, wie die unterschiedlichen Änderungen zusammengeführt werden.

Die Behandlung solcher Fälle wird im Bereich `08_Troubleshooting` dokumentiert.

## 11. Push kann abgelehnt werden

Ein `git push` kann abgelehnt werden, wenn das Remote-Repository inzwischen Änderungen enthält, die lokal noch nicht vorhanden sind.

Beispielsweise:

```text
! [rejected] main -> main
```

In diesem Fall sollte nicht einfach mehrfach `git push` ausgeführt werden.

Zunächst muss der lokale Stand mit dem Remote-Stand abgeglichen werden.

## 12. Online-Änderungen beachten

Besonders wichtig ist dies, wenn gleichzeitig direkt auf GitHub gearbeitet wurde.

Beispiel:

```text
Lokaler Computer
     │
     │ lokale Änderung
     ▼
   Commit

GitHub
     │
     │ Online-Änderung
     ▼
   Commit
```

Das lokale Repository kennt den Online-Commit zunächst nicht.

Vor dem weiteren lokalen Arbeiten sollte daher:

```powershell
git pull
```

ausgeführt werden.

## 13. Merksatz

> `pull` holt Änderungen, `commit` speichert lokale Änderungen, `push` überträgt lokale Commits nach GitHub.

Der vollständige Ablauf lautet:

```text
PULL
 ↓
ARBEITEN
 ↓
PRÜFEN
 ↓
ADD
 ↓
COMMIT
 ↓
PUSH
 ↓
KONTROLLIEREN
```