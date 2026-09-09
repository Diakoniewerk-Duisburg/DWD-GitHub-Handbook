# Checklisten

## Zweck

Die Checklisten dienen als kurze operative Kontrolle für wiederkehrende Git- und GitHub-Aufgaben.

Sie ersetzen keine ausführlichen HowTos, sondern helfen dabei, vor und nach einer Aktion die wichtigsten Punkte zu prüfen.

## Verfügbare Checklisten

- [Repository anlegen](Repository_anlegen.md)
- [Repository übertragen](Repository_uebertragen.md)
- [Repository synchronisieren](Repository_synchronisieren.md)

## Standardkontrollen

Vor einer Änderung:

```powershell
git status
git branch --show-current
git remote -v
```

Vor einem Commit:

- richtige Dateien geändert?
- unnötige Dateien ausgeschlossen?
- keine Geheimnisse oder vertraulichen Daten enthalten?
- `git diff` geprüft?
- `git diff --staged` geprüft?
- sinnvolle Commit-Nachricht gewählt?

Vor einem Push:

- richtiger Branch?
- richtiges Remote?
- Commit geprüft?
- keine vertraulichen Daten?
- Push bewusst durchführen.

Nach einem Push:

- `git status` prüfen
- GitHub öffnen
- Branch prüfen
- Dateien prüfen
- Commit-Historie prüfen

## Standardablauf

```text
Pull
  ↓
Arbeiten
  ↓
Prüfen
  ↓
Add
  ↓
Commit
  ↓
Push
  ↓
Kontrolle
```

## Merksatz

> **Nicht nur ausführen – vor und nach jeder wichtigen Git-Aktion den Zustand prüfen.**
