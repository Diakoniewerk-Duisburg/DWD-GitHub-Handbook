# Authentifizierung

## Zweck

Dieser Bereich beschreibt die Anmeldung und Authentifizierung bei der Arbeit mit Git und GitHub.

Wichtig ist die Unterscheidung zwischen:

- Anmeldung an GitHub über die Weboberfläche
- Authentifizierung von lokalem Git gegenüber GitHub
- Berechtigung zum Zugriff auf ein Repository

## Verfahren

| Verfahren | Typischer Einsatz |
|---|---|
| HTTPS | Standard für einfache Git-Verbindungen |
| Personal Access Token | Authentifizierung bei HTTPS, wenn ein Token erforderlich ist |
| SSH | Authentifizierung über einen SSH-Schlüssel |

## Dokumente

- [HTTPS](HTTPS.md)
- [Personal Access Token](Personal_Access_Token.md)
- [SSH](SSH.md)

## Authentifizierung ist nicht Autorisierung

Die erfolgreiche Authentifizierung bedeutet nur, dass GitHub die Identität akzeptiert.

Zusätzlich muss das verwendete Konto die erforderlichen Berechtigungen auf dem Repository besitzen.

## Typische Probleme

- falsches GitHub-Konto
- ungültige oder abgelaufene Zugangsdaten
- ungültiger Personal Access Token
- fehlende Repository-Berechtigung
- falsches Remote
- fehlerhafte SSH-Konfiguration

## Sicherheitsregel

Authentifizierungsdaten gehören niemals in das Repository.

Insbesondere dürfen niemals committed werden:

- Passwörter
- Personal Access Tokens
- private SSH-Schlüssel
- API Keys
- andere Zugangsdaten
