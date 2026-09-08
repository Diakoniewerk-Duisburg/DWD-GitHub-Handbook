# Merge Conflict

## 1. Zweck

Ein Merge Conflict entsteht, wenn Git zwei Änderungen nicht automatisch zusammenführen kann.

Das kann beispielsweise passieren, wenn dieselbe Stelle einer Datei auf zwei unterschiedlichen Branches geändert wurde.

## 2. Beispiel

```text
main
 │
 ├── Änderung A
 │
 └── Änderung B
```

Wenn beide Änderungen denselben Bereich betreffen, kann Git die richtige Variante nicht selbst bestimmen.

## 3. Typische Situation

Beispielsweise:

```text
GitHub:
README.md → Abschnitt geändert

Lokal:
README.md → derselbe Abschnitt ebenfalls geändert
```

Beim Zusammenführen erkennt Git den Konflikt.

## 4. Konflikt erkennen

Git meldet den betroffenen Bereich.

Anschließend:

```powershell
git status
```

ausführen.

Dort werden Dateien mit Konflikten angezeigt.

## 5. Konfliktdatei öffnen

In der betroffenen Datei können Konfliktmarkierungen erscheinen:

```text
<<<<<<< HEAD
Lokale Änderung
=======
Änderung aus dem anderen Branch
>>>>>>> branch-name
```

Diese Markierungen müssen bei der Konfliktauflösung berücksichtigt werden.

## 6. Inhalt entscheiden

Es muss entschieden werden:

- lokale Änderung behalten
- andere Änderung behalten
- beide Änderungen kombinieren
- Änderung vollständig neu formulieren

Die Entscheidung sollte fachlich getroffen werden und nicht lediglich nach dem Prinzip „eine Seite auswählen“.

## 7. Konflikt abschließen

Nach der manuellen Bearbeitung:

```powershell
git add <Datei>
```

Anschließend den vorgesehenen Abschluss des Merge-Vorgangs durchführen.

## 8. Kontrolle

Vor dem Abschluss:

```powershell
git status
```

und gegebenenfalls:

```powershell
git diff
```

prüfen.

## 9. Wichtiger Hinweis

Bei Unsicherheit sollte der Konflikt nicht durch einen destruktiven Befehl „gelöst“ werden.

Insbesondere:

```powershell
git reset --hard
```

nicht ohne vorherige Prüfung verwenden.

## 10. Merksatz

> Ein Merge Conflict bedeutet nicht, dass Git kaputt ist. Git benötigt eine Entscheidung darüber, wie widersprüchliche Änderungen zusammengeführt werden sollen.