# Troubleshooting

Dieser Bereich beschreibt typische Fehler, Warnungen und unerwartete Zustände bei der Arbeit mit Git und GitHub.

Ziel ist nicht, Fehlermeldungen einfach mit einem weiteren Befehl zu übergehen, sondern den tatsächlichen Zustand des Repositorys zu verstehen.

## Grundprinzip

Bei einem Problem gilt immer:

```text id="d3j9r2"
Fehlermeldung
      ↓
Bedeutung verstehen
      ↓
Repository-Zustand prüfen
      ↓
Ursache bestimmen
      ↓
Gezielte Lösung
      ↓
Ergebnis kontrollieren
```

## Typische Situationen

| Situation | Dokumentation |
|---|---|
| `nothing to commit, working tree clean` | [Nothing to commit](Nothing_to_commit.md) |
| Push wird abgelehnt | [Push abgelehnt](Push_abgelehnt.md) |
| Merge-Konflikt | [Merge Conflict](Merge_Conflict.md) |
| LF/CRLF-Warnung | [LF/CRLF-Warnung](LF_CRLF_Warnung.md) |

## Erste Prüfungen

Bei einem unbekannten Problem zunächst:

```powershell id="z6r7qt"
git status
```

Danach gegebenenfalls:

```powershell id="t7q3vh"
git branch --show-current
git remote -v
git log --oneline -5
```

Damit lassen sich bereits viele Ursachen erkennen.

## Häufige Ursachen

### Falsches Repository

Der Befehl wurde möglicherweise in einem anderen Projektordner ausgeführt.

Prüfen:

```powershell id="h8m2m9"
Get-Location
git status
```

---

### Falscher Branch

Prüfen:

```powershell id="g8n1c4"
git branch --show-current
```

---

### Falsches Remote

Prüfen:

```powershell id="4j8b0w"
git remote -v
```

---

### Änderungen nicht committed

Prüfen:

```powershell id="q3u9af"
git status
```

---

### Remote enthält neuere Änderungen

Ein Push kann abgelehnt werden.

Nicht sofort:

```powershell id="y7k1ec"
git push --force
```

Stattdessen zuerst die Situation analysieren.

Siehe:

[Push abgelehnt](Push_abgelehnt.md)

---

## Vorsicht bei destruktiven Befehlen

Besondere Vorsicht gilt bei Befehlen wie:

```text id="8x1s0r"
git reset --hard
git push --force
```

Diese Befehle können lokale oder entfernte Änderungen verwerfen beziehungsweise überschreiben.

Sie sollten nicht als allgemeine Problemlösung verwendet werden.

## Grundregel

> **Erst verstehen, dann ändern.**

Eine Fehlermeldung ist häufig bereits eine wichtige Information über den Zustand des Repositorys.