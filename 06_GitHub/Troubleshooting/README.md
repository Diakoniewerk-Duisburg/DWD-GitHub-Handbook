# Troubleshooting

## Zweck

Dieser Bereich hilft bei typischen Problemen mit Git und GitHub.

Die Vorgehensweise ist immer systematisch:

```text
Fehlermeldung
     ↓
Bedeutung verstehen
     ↓
Repository-Zustand prüfen
     ↓
Ursache eingrenzen
     ↓
Gezielt korrigieren
     ↓
Ergebnis kontrollieren
```

## Häufige Situationen

- [Nothing to commit](Nothing_to_commit.md)
- [Push abgelehnt](Push_abgelehnt.md)
- [Merge Conflict](Merge_Conflict.md)
- [LF/CRLF-Warnung](LF_CRLF_Warnung.md)

## Erste Diagnose

Bei fast jedem unbekannten Problem zuerst:

```powershell
git status
git branch --show-current
git remote -v
```

Danach bei Bedarf:

```powershell
git diff
git diff --staged
git log --oneline -5
```

## Wichtige Regeln

Nicht blind verwenden:

```powershell
git reset --hard
git push --force
```

Solche Befehle können lokale oder entfernte Änderungen dauerhaft verändern oder verlieren lassen.

Erst den Zustand verstehen, dann handeln.

## Merksatz

> **Fehlerbehebung beginnt mit `git status`, nicht mit einem zufällig ausprobierten Git-Befehl.**
