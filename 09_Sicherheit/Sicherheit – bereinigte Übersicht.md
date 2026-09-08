# Sicherheit

Dieser Bereich beschreibt die Sicherheitsregeln für die Arbeit mit Git und GitHub.

Der Schwerpunkt liegt auf der Frage:

> Welche Informationen dürfen in ein Repository und welche nicht?

## Themen

### Was gehört nicht in GitHub?

[Was nicht in GitHub gehört](Was_nicht_in_GitHub_gehoert.md)

Hier werden insbesondere behandelt:

- Passwörter
- Tokens
- API Keys
- private Schlüssel
- personenbezogene Daten
- vertrauliche Informationen
- Produktionsdaten
- lokale Geheimnisse

---

### Personal Access Token

Die technische Beschreibung von Personal Access Tokens befindet sich im Bereich [Authentifizierung](../06_Authentifizierung/README.md).

Direkt:

[Personal Access Token](../06_Authentifizierung/Personal_Access_Token.md)

---

# Sicherheitsprüfung vor dem Commit

Vor einem Commit:

```powershell
git status
```

Danach:

```powershell
git diff
```

Nach dem Staging:

```powershell
git diff --staged
```

Dabei prüfen:

```text
[ ] Keine Zugangsdaten
[ ] Keine Tokens
[ ] Keine API Keys
[ ] Keine privaten Schlüssel
[ ] Keine personenbezogenen Daten
[ ] Keine vertraulichen Dateien
[ ] Keine unerwarteten Dateien
```

---

# `.gitignore`

`.gitignore` kann Dateien vom normalen Git-Tracking ausschließen.

Beispiele:

```text
.env
*.log
bin/
obj/
```

Die konkrete Konfiguration hängt vom jeweiligen Projekt ab.

Wichtig:

> `.gitignore` ist kein Ersatz für eine Sicherheitsprüfung.

Eine bereits committed Datei wird durch einen späteren `.gitignore`-Eintrag nicht automatisch aus der Git-Historie entfernt.

---

# Grundregel

> **Sicherheit beginnt vor `git add`.**

Nicht erst GitHub prüfen, nachdem etwas bereits veröffentlicht wurde.

Der sichere Ablauf lautet:

```text
Ändern
  ↓
Prüfen
  ↓
Sicherheit prüfen
  ↓
git add
  ↓
git diff --staged
  ↓
commit
  ↓
push
```