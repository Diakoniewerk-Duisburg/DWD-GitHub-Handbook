# HTTPS – Git und GitHub

## 1. Was ist HTTPS?

Bei einer HTTPS-Verbindung kommuniziert Git über HTTPS mit GitHub.

Eine typische Remote-URL sieht beispielsweise so aus:

```text
https://github.com/Benutzername/Mein-Projekt.git
```

Die URL kann mit:

```powershell
git remote -v
```

kontrolliert werden.

---

# 2. HTTPS bedeutet nicht automatisch Anmeldung

Die Remote-URL beschreibt zunächst nur:

> Mit welchem GitHub-Endpunkt soll kommuniziert werden?

Zusätzlich muss GitHub den Benutzer authentifizieren.

Vereinfacht:

```text
Remote-URL
     ↓
GitHub Repository finden
     ↓
Authentifizierung
     ↓
Berechtigung
     ↓
Aktion
```

---

# 3. GitHub-Passwort

Für Git-Operationen über HTTPS wird das normale GitHub-Kontopasswort nicht als Git-Passwort verwendet.

Stattdessen erfolgt die Authentifizierung je nach verwendeter Git-/Credential-Konfiguration beispielsweise über einen Personal Access Token beziehungsweise eine von Git bereitgestellte Anmelde-/Credential-Lösung.

---

# 4. Personal Access Token

Bei einer HTTPS-Konfiguration kann ein Personal Access Token für die Authentifizierung verwendet werden.

Ein Token ist ein Geheimnis.

Deshalb:

```text
PAT
 │
 ├── nicht committen
 ├── nicht veröffentlichen
 ├── nicht weitergeben
 └── nicht in Skripte schreiben
```

Siehe:

[Personal Access Token](Personal_Access_Token.md)

---

# 5. Credential Management

Git kann Anmeldedaten beziehungsweise Zugangsinformationen über Credential-Mechanismen verwalten.

Dadurch muss ein Benutzer nicht zwangsläufig bei jedem Git-Befehl seine Zugangsdaten erneut eingeben.

Die konkrete Speicherung und Verwaltung hängt von Betriebssystem, Git-Version und verwendeter Credential-Lösung ab.

Unter Windows kann beispielsweise der Windows Credential Manager eine Rolle spielen.

---

# 6. Remote prüfen

Wenn ein HTTPS-Zugriff unerwartet funktioniert oder nicht funktioniert:

```powershell
git remote -v
```

prüfen.

Beispiel:

```text
origin  https://github.com/Benutzername/Mein-Projekt.git (fetch)
origin  https://github.com/Benutzername/Mein-Projekt.git (push)
```

Danach:

```powershell
git status
```

und gegebenenfalls:

```powershell
git branch --show-current
```

---

# 7. Typische Fehler

### Falsches Repository

Das Remote zeigt auf das falsche Repository.

Lösung:

```powershell
git remote -v
```

prüfen und gegebenenfalls das Remote korrigieren.

---

### Fehlende Berechtigung

Die Authentifizierung kann erfolgreich sein, obwohl keine Schreibberechtigung für das Repository besteht.

Dann muss die Repository-Berechtigung geprüft werden.

---

### Ungültige Zugangsinformation

Ein Token kann beispielsweise ungültig, abgelaufen oder widerrufen worden sein.

Dann muss die Authentifizierung entsprechend erneuert werden.

---

# 8. Sicherheitsregel

> **Eine HTTPS-URL ist keine Zugangsdaten. Ein Token ist dagegen ein Geheimnis.**

Eine Repository-URL darf in der Dokumentation als Beispiel erscheinen.

Ein echter Token niemals.