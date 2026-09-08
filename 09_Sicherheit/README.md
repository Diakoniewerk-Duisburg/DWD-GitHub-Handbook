# Sicherheit

## Zweck

Dieser Bereich beschreibt die wichtigsten Sicherheitsregeln für die Arbeit mit Git und GitHub.

Sicherheit beginnt nicht erst beim Push. Sie beginnt bereits bei der Auswahl der Dateien, die mit `git add` in den nächsten Commit aufgenommen werden.

## Grundregeln

Nicht in ein öffentliches oder unkontrolliertes Repository gehören insbesondere:

- Passwörter
- Personal Access Tokens
- API Keys
- private Schlüssel
- Zugangsdaten
- vertrauliche Konfigurationsdateien
- personenbezogene Daten
- Produktionsdaten
- interne Informationen, die nicht veröffentlicht werden dürfen

Weitere Details:

- [Was gehört nicht in GitHub?](Was_nicht_in_GitHub_gehoert.md)
- [Personal Access Token](../06_Authentifizierung/Personal_Access_Token.md)

## Vor dem Commit

Prüfen:

```powershell
git status
git diff
git diff --staged
```

Besonders wichtig ist die Kontrolle des Staging-Bereichs:

```powershell
git diff --staged
```

Denn genau diese Änderungen werden Bestandteil des nächsten Commits.

## `.gitignore`

Eine `.gitignore` kann dabei helfen, lokale oder nicht zu versionierende Dateien vom Staging auszuschließen.

Sie ist jedoch **kein Sicherheitsmechanismus**.

Wenn ein Geheimnis bereits committed wurde, entfernt ein späterer Eintrag in `.gitignore` das Geheimnis nicht aus der Git-Historie.

## Personal Access Token

Ein Personal Access Token ist wie ein Passwort zu behandeln:

- niemals in Dateien eintragen, die committed werden,
- niemals in Screenshots oder Dokumentation veröffentlichen,
- niemals per Chat oder E-Mail weitergeben,
- bei einer Veröffentlichung sofort widerrufen beziehungsweise ersetzen.

Die technische Beschreibung befindet sich im Bereich [06 – Authentifizierung](../06_Authentifizierung/Personal_Access_Token.md).

## Vor dem Push

Vor `git push` sollte geprüft werden:

1. Ist das richtige Repository aktiv?
2. Ist der richtige Branch aktiv?
3. Ist das richtige Remote konfiguriert?
4. Sind nur die gewünschten Dateien committed?
5. Enthält der Commit keine Geheimnisse oder vertraulichen Daten?

## Wichtige Erkenntnis

> **Ein Geheimnis gehört nicht deshalb nach GitHub, weil es durch `.gitignore` geschützt werden könnte. Es gehört gar nicht erst in den Commit.**
