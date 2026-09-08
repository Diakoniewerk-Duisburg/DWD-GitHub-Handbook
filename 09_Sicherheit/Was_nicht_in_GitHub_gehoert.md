# Was gehört nicht in GitHub?

## 1. Grundregel

Nicht jede Datei eines Projekts gehört in ein GitHub-Repository.

Ein Repository sollte nur die Dateien enthalten, die für das jeweilige Projekt tatsächlich benötigt werden.

## 2. Geheimnisse

Nicht in GitHub speichern:

- Passwörter
- Tokens
- API-Schlüssel
- Private Keys
- Secrets
- Zugangsdaten

## 3. Lokale und temporäre Dateien

Typischerweise gehören auch lokale Arbeitsdateien nicht in das Repository.

Beispiele:

- temporäre Dateien
- Editor-Dateien
- lokale Cache-Dateien
- Build-Ausgaben
- Debug-Ausgaben
- persönliche Konfigurationen

## 4. Lokale Konfiguration

Konfigurationsdateien können problematisch sein, wenn sie beispielsweise:

- Zugangsdaten
- lokale Pfade
- interne Servernamen
- Tokens
- persönliche Einstellungen

enthalten.

Eine sichere Alternative ist eine Beispielkonfiguration.

Beispiel:

```text id="6z7ujt"
config.example.json
```

anstelle einer produktiven Konfiguration mit Secrets.

## 5. Persönliche Daten

Personenbezogene Daten dürfen nicht ohne Prüfung in einem Repository gespeichert werden.

Das betrifft beispielsweise:

- Namen
- Kontaktdaten
- E-Mail-Adressen
- Benutzerinformationen
- personenbezogene Exportdaten
- Protokolle mit personenbezogenen Informationen

## 6. Produktionsdaten

Produktive Daten gehören grundsätzlich nicht in ein Entwicklungs- oder Dokumentationsrepository.

Dazu können gehören:

- Datenbankexporte
- Benutzerexporte
- Produktionslogs
- Konfigurations-Backups
- vollständige Datenbestände

## 7. Vor dem Commit

Vor einem Commit sollte daher immer geprüft werden:

```text id="i9f9z6"
git status
     ↓
Neue Dateien?
     ↓
Vertrauliche Inhalte?
     ↓
Persönliche Daten?
     ↓
Secrets?
     ↓
git diff
     ↓
Commit
```

## 8. `.gitignore`

Eine `.gitignore`-Datei kann verhindern, dass bestimmte Dateien versehentlich von Git berücksichtigt werden.

Beispielsweise können damit lokale oder temporäre Dateien ausgeschlossen werden.

Wichtig:

> `.gitignore` ist kein Ersatz für Sicherheitsprüfungen.

Eine Datei, die bereits committed wurde, wird durch das nachträgliche Eintragen in `.gitignore` nicht aus der Git-Historie entfernt.

## 9. Grundsatz

> GitHub ist kein allgemeiner Dateispeicher. Nur bewusst ausgewählte und für das Repository bestimmte Dateien gehören hinein.