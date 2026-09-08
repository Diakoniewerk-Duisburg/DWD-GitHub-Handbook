# Praxisbeispiel 05 – Push abgelehnt

## Situation

Eine lokale Änderung wurde committed und anschließend soll sie nach GitHub übertragen werden. Der Push wird jedoch abgelehnt.

```powershell
git push
```

Git meldet, dass der Remote-Branch Änderungen enthält, die lokal noch nicht vorhanden sind.

## 1. Was bedeutet das?

Git verhindert den Push, weil dadurch Änderungen auf GitHub überschrieben werden könnten. Das ist zunächst ein Schutzmechanismus.

## 2. Nicht sofort Force Push verwenden

Nicht einfach:

```powershell
git push --force
```

verwenden.

Zuerst muss geklärt werden, warum die Stände voneinander abweichen.

## 3. Lokalen Zustand prüfen

```powershell
git status
git branch --show-current
git remote -v
```

## 4. Häufige Ursache

Ein häufiger Grund ist eine Änderung direkt auf GitHub, während lokal ebenfalls weitergearbeitet und committed wurde.

## 5. Remote-Änderungen holen

Wenn das lokale Arbeitsverzeichnis sauber ist:

```powershell
git pull
```

Git ruft die Änderungen vom Remote ab und integriert sie in den aktuellen lokalen Branch.

## 6. Fall A – Git kann automatisch zusammenführen

Nach erfolgreicher Integration:

```powershell
git status
git push
```

## 7. Fall B – Merge Conflict

Wenn Git die Änderungen nicht automatisch zusammenführen kann, entsteht ein Merge-Konflikt.

Beispielsweise:

```text
<<<<<<< HEAD
Lokale Version
=======
GitHub Version
>>>>>>> origin/main
```

Die Konfliktmarkierungen müssen entfernt und die gewünschte endgültige Version hergestellt werden.

Danach:

```powershell
git add <Datei>
```

und den von Git erwarteten Abschluss des Merge-Vorgangs durchführen.

Anschließend:

```powershell
git status
git push
```

Siehe auch:

[Merge Conflict](../08_Troubleshooting/Merge_Conflict.md)

## 8. Fall C – GitHub wurde versehentlich separat initialisiert

Ein häufiger Sonderfall entsteht, wenn lokal bereits eine vollständige Git-Historie existiert und auf GitHub zusätzlich eine README oder ein anderer Initial-Commit angelegt wurde.

Dann können zwei unabhängige Historien entstanden sein. In diesem Fall die Situation zuerst analysieren und nicht blind mit `--force` überschreiben.

## 9. Kontrolle nach der Lösung

```powershell
git status
git log --oneline -5
git remote -v
```

Schließlich das GitHub-Repository kontrollieren.

# Merksatz

> **Ein abgelehnter Push ist zunächst eine Aufforderung zur Prüfung – nicht zur Verwendung von `--force`.**
