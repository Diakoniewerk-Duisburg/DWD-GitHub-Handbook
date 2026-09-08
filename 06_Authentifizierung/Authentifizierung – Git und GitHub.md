# Authentifizierung

Dieser Bereich beschreibt die Authentifizierung beim Zugriff von Git auf GitHub.

Dabei ist zwischen der Anmeldung an der GitHub-Weboberfläche und der Authentifizierung eines lokalen Git-Clients zu unterscheiden.

## Grundverständnis

Wenn Git lokal mit GitHub kommuniziert, muss GitHub feststellen können:

> Wer versucht auf dieses Repository zuzugreifen?

Zusätzlich muss geprüft werden:

> Darf diese Identität die gewünschte Aktion durchführen?

Vereinfacht:

```text
Lokales Git
    │
    │ Verbindung
    ▼
GitHub
    │
    ├── Identität prüfen
    │
    └── Berechtigung prüfen
            │
            ▼
       Zugriff erlauben
```

---

# Authentifizierungsverfahren

Für die lokale Arbeit mit GitHub sind insbesondere folgende Verfahren relevant:

| Verfahren | Verwendung |
|---|---|
| HTTPS | Git-Verbindung über HTTPS |
| Personal Access Token | Authentifizierung bei HTTPS |
| SSH | Authentifizierung über SSH-Key |

Die konkreten Verfahren und deren Einrichtung werden in den folgenden Dokumenten beschrieben.

---

## HTTPS

[HTTPS](HTTPS.md)

HTTPS verwendet eine Web-Verbindung zum GitHub-Repository.

Beispiel:

```text
https://github.com/Benutzername/Mein-Projekt.git
```

Bei der Authentifizierung wird für GitHub nicht das normale GitHub-Passwort als Git-Passwort verwendet.

Stattdessen kann beispielsweise ein Personal Access Token eingesetzt werden.

---

## Personal Access Token

[Personal Access Token](Personal_Access_Token.md)

Ein Personal Access Token (PAT) ist ein Zugangstoken für bestimmte GitHub-Aktionen.

Ein PAT muss wie ein Passwort behandelt werden:

- nicht veröffentlichen
- nicht in Dateien speichern
- nicht committen
- nicht per Chat oder E-Mail weitergeben
- nicht in Screenshots zeigen

---

## SSH

[SSH](SSH.md)

SSH ermöglicht die Authentifizierung über einen SSH-Schlüssel.

Dabei wird ein Schlüsselpaar verwendet:

```text
Privater Schlüssel
       │
       │ bleibt lokal
       ▼
lokaler Rechner


Öffentlicher Schlüssel
       │
       │ wird bei GitHub hinterlegt
       ▼
GitHub
```

Der private Schlüssel darf niemals veröffentlicht oder weitergegeben werden.

---

# Authentifizierung ist nicht Autorisierung

Diese beiden Begriffe dürfen nicht verwechselt werden.

### Authentifizierung

> Wer bist du?

### Autorisierung

> Was darfst du tun?

Beispiel:

```text
Benutzer
   ↓
Authentifizierung
   ↓
GitHub kennt Identität
   ↓
Autorisierung
   ↓
Repository darf gelesen/geschrieben werden
```

Eine erfolgreiche Anmeldung bedeutet deshalb nicht automatisch, dass Schreibzugriff auf jedes Repository besteht.

---

# Typische Probleme

Bei Problemen mit `git pull` oder `git push` können unter anderem folgende Ursachen vorliegen:

- falsche Zugangsdaten
- ungültiger oder abgelaufener Token
- fehlende Repository-Berechtigung
- falsches GitHub-Konto
- falsche Remote-URL
- falsche SSH-Konfiguration
- nicht vorhandener SSH-Key
- falscher SSH-Key
- Repository nicht erreichbar

Die erste Prüfung sollte trotzdem häufig weiterhin sein:

```powershell
git remote -v
```

Denn eine korrekte Authentifizierung nützt nichts, wenn das lokale Repository auf das falsche Remote zeigt.

---

# Sicherheitsgrundsatz

> **Authentifizierungsdaten gehören nicht in die Git-Historie.**

Insbesondere niemals:

```text
Passwort
PAT
API-Key
Private SSH-Key
Private Zertifikatsschlüssel
```

committen.

Siehe auch:

[09 – Sicherheit](../09_Sicherheit/README.md)

---

# Empfohlene Reihenfolge

Wer GitHub lokal verwenden möchte, sollte zunächst verstehen:

```text
Git
 ↓
GitHub
 ↓
Remote
 ↓
HTTPS / SSH
 ↓
Authentifizierung
 ↓
Berechtigung
```

Danach können die jeweiligen Verfahren eingerichtet werden.