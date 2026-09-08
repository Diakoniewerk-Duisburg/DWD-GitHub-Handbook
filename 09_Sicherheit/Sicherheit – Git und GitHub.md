# Sicherheit

Git speichert nicht nur den aktuellen Zustand eines Projekts.

Die Git-Historie kann frühere Zustände und damit auch versehentlich committed Daten enthalten.

Deshalb beginnt Sicherheit bereits **vor `git add`**.

## Grundregel

> **Was in Git committed wird, kann Bestandteil der Repository-Historie werden.**

## Niemals in ein Repository einchecken

Insbesondere nicht:

- Passwörter
- Personal Access Tokens
- API Keys
- private Schlüssel
- Zertifikats-Private-Keys
- Zugangsdaten
- Secrets
- personenbezogene Daten
- vertrauliche Produktionsdaten
- nicht freigegebene Konfigurationsdateien
- lokale Sicherungs- oder Exportdateien mit vertraulichen Inhalten

Siehe:

[Was nicht in GitHub gehört](Was_nicht_in_GitHub_gehoert.md)

## Personal Access Tokens

Ein Personal Access Token muss wie ein Passwort behandelt werden.

[Personal Access Token](Personal_Access_Token.md)

## Vor jedem Commit

Mindestens:

```powershell id="i5g3x4"
git status
```

prüfen.

Anschließend:

```powershell id="1k6k3j"
git diff
```

und nach dem Staging:

```powershell id="f7q2ab"
git diff --staged
```

Damit wird kontrolliert, was tatsächlich Bestandteil des nächsten Commits werden soll.

## `.gitignore`

Eine `.gitignore` kann Dateien und Verzeichnisse vom normalen Git-Tracking ausschließen.

Sie ist sinnvoll für beispielsweise:

- temporäre Dateien
- lokale Build-Ausgaben
- IDE-Dateien
- lokale Konfiguration
- Umgebungsdateien

Sie ersetzt jedoch keine Sicherheitsprüfung.

> Eine Datei, die bereits committed wurde, wird durch einen späteren Eintrag in `.gitignore` nicht aus der Git-Historie entfernt.

## Bereits veröffentlichtes Secret

Wenn ein Secret versehentlich nach GitHub übertragen wurde:

1. Secret sofort ungültig machen beziehungsweise widerrufen.
2. Neues Secret erzeugen.
3. Betroffene Systeme prüfen.
4. Repository-Historie analysieren.
5. Erforderliche Bereinigung durchführen.
6. Ursache beseitigen.

**Das Löschen der Datei allein reicht nicht aus.**

## Private Repositorys

Ein privates Repository reduziert die Sichtbarkeit, macht den Inhalt aber nicht automatisch sicher.

Auch in privaten Repositorys gelten die gleichen Grundregeln für Secrets und vertrauliche Daten.

## Grundprinzip

```text id="i7yr6a"
Bearbeiten
    ↓
Prüfen
    ↓
git add
    ↓
git diff --staged
    ↓
Commit
    ↓
Push
```

Die Sicherheitsprüfung gehört in diesen Ablauf und nicht erst danach.