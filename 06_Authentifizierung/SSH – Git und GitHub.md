# SSH – Git und GitHub

## 1. Was ist SSH?

SSH ermöglicht eine authentifizierte Verbindung zwischen dem lokalen Git-Client und GitHub.

Eine typische SSH-Remote-URL sieht beispielsweise so aus:

```text
git@github.com:Benutzername/Mein-Projekt.git
```

---

# 2. Schlüsselprinzip

SSH verwendet ein Schlüsselpaar:

```text
SSH-Schlüsselpaar
       │
       ├── Privater Schlüssel
       │       └── bleibt auf dem lokalen Rechner
       │
       └── Öffentlicher Schlüssel
               └── wird bei GitHub hinterlegt
```

Der private Schlüssel darf niemals weitergegeben werden.

---

# 3. Warum gibt es zwei Schlüssel?

Der öffentliche Schlüssel dient dazu, die Identität des lokalen Rechners beziehungsweise Benutzers gegenüber GitHub zu verifizieren.

Der private Schlüssel bleibt geheim.

Vereinfacht:

```text
Lokaler Rechner
      │
      │ privater Schlüssel
      ▼
   SSH-Client
      │
      │ SSH
      ▼
    GitHub
      │
      │ öffentlicher Schlüssel bekannt
      ▼
Authentifizierung
```

---

# 4. Remote prüfen

Bei einem SSH-Repository:

```powershell
git remote -v
```

kann beispielsweise erscheinen:

```text
origin  git@github.com:Benutzername/Mein-Projekt.git (fetch)
origin  git@github.com:Benutzername/Mein-Projekt.git (push)
```

Damit ist erkennbar, dass das Repository über SSH angesprochen wird.

---

# 5. Private Schlüssel schützen

Der private Schlüssel darf nicht:

- in GitHub hochgeladen werden
- in ein Repository committed werden
- per E-Mail weitergegeben werden
- in Dokumentationen veröffentlicht werden
- in Screenshots sichtbar sein

Auch nicht in einem privaten Repository.

---

# 6. SSH und Repository-Berechtigung

Eine erfolgreiche SSH-Authentifizierung bedeutet nicht automatisch:

> Der Benutzer darf auf jedes Repository schreiben.

Nach der Identifizierung wird zusätzlich geprüft, welche Berechtigungen die Identität besitzt.

---

# 7. HTTPS oder SSH?

Für das Handbook reicht zunächst folgende Orientierung:

| HTTPS | SSH |
|---|---|
| Web-URL | SSH-URL |
| weit verbreitet | sehr gut für dauerhafte lokale Nutzung |
| Authentifizierung über Credential-/Token-Mechanismen | Authentifizierung über SSH-Key |
| einfach verständlich | etwas mehr Einrichtung |
| URL beginnt mit `https://` | URL beginnt typischerweise mit `git@github.com:` |

Es gibt kein allgemeines „richtig“ für alle Situationen.

Entscheidend ist, dass das verwendete Verfahren verstanden und sicher konfiguriert ist.

---

# Merksatz

> **Der öffentliche SSH-Key darf zu GitHub. Der private SSH-Key bleibt geheim und lokal.**