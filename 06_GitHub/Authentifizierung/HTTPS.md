# HTTPS

## Zweck

Git kann über HTTPS mit GitHub verbunden werden.

Beispiel für ein Remote:

```text
https://github.com/Benutzername/Mein-Projekt.git
```

## Remote prüfen

```powershell
git remote -v
```

## Authentifizierung

Die URL beschreibt das Ziel-Repository. Sie enthält nicht automatisch die Zugangsdaten.

Für GitHub wird das normale GitHub-Kontopasswort nicht als Git-Passwort verwendet. Je nach verwendeter Umgebung kommen beispielsweise Credential Manager und ein Personal Access Token zum Einsatz.

Siehe [Personal Access Token](Personal_Access_Token.md).

## Sicherheitsregeln

Zugangsdaten, Tokens und andere Geheimnisse niemals in Dateien, Commit-Nachrichten oder Repository-Inhalte eintragen.

Bei Verdacht auf eine Veröffentlichung eines Tokens muss dieser unverzüglich widerrufen beziehungsweise ersetzt werden.

## Typische Prüfung

Bei Authentifizierungsproblemen zuerst:

```powershell
git remote -v
git status
```

Danach prüfen:

- richtige Repository-URL
- richtiges GitHub-Konto
- vorhandene Repository-Berechtigung
- gültige Authentifizierung
