# SSH

## Zweck

SSH ermöglicht die Authentifizierung von Git gegenüber GitHub über ein Schlüsselpaar.

Beispiel für ein SSH-Remote:

```text
git@github.com:Benutzername/Mein-Projekt.git
```

## Grundprinzip

Es werden zwei Schlüssel verwendet:

- privater Schlüssel: bleibt ausschließlich auf dem lokalen Rechner
- öffentlicher Schlüssel: wird bei GitHub hinterlegt

Der private Schlüssel darf niemals in ein Repository gelangen.

## Remote prüfen

```powershell
git remote -v
```

## HTTPS oder SSH?

| Verfahren | Merkmal |
|---|---|
| HTTPS | Verbindung über HTTPS; Authentifizierung beispielsweise über Credential Manager und PAT |
| SSH | Authentifizierung über SSH-Schlüssel |

Beide Verfahren können für die tägliche Git-Arbeit verwendet werden.

## Sicherheitsregeln

- privaten Schlüssel niemals veröffentlichen
- private Schlüssel niemals committen
- SSH-Schlüssel mit geeigneter Schutzphrase absichern
- bei Verlust oder Verdacht auf Kompromittierung den Schlüssel ersetzen

## Authentifizierung und Berechtigung

Ein erfolgreicher SSH-Verbindungsaufbau bedeutet nicht automatisch, dass das gewünschte Repository beschrieben werden darf.

Das verwendete GitHub-Konto beziehungsweise die zugehörige Identität benötigt weiterhin die erforderlichen Repository-Berechtigungen.
