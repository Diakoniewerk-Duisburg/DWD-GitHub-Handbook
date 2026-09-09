# Personal Access Token

## Zweck

Ein Personal Access Token (PAT) kann bei HTTPS-Verbindungen zur Authentifizierung gegenüber GitHub verwendet werden.

## Sicherheitsregel

Ein PAT ist wie ein Passwort zu behandeln.

Er darf niemals:

- committed werden,
- in README-Dateien eingetragen werden,
- in Screenshots veröffentlicht werden,
- per Chat oder E-Mail weitergegeben werden.

## Verwendung

Wenn eine Git-Umgebung einen Token als Zugangsdaten verlangt, wird der PAT als geheimes Authentifizierungsmerkmal verwendet.

Der Token selbst gehört nicht in die Repository-Konfiguration oder in eine versionierte Datei.

## Berechtigungen

Ein Token sollte nur die für die Aufgabe erforderlichen Berechtigungen besitzen.

Zusätzlich zur Token-Berechtigung muss das verwendete GitHub-Konto Zugriff auf das Ziel-Repository besitzen.

## Wenn ein Token veröffentlicht wurde

Wenn ein PAT versehentlich in ein Repository, einen Commit, ein Log, einen Screenshot oder einen anderen öffentlich zugänglichen Bereich gelangt ist:

1. Token sofort widerrufen.
2. Ersatz-Token erzeugen, falls weiterhin benötigt.
3. Betroffene Zugangsdaten beziehungsweise Systeme prüfen.
4. Repository-Historie und weitere Kopien prüfen.
5. Den ursprünglichen Token nicht weiterverwenden.

Das spätere Löschen einer Datei macht einen bereits veröffentlichten Token nicht automatisch sicher.

## Grundsatz

> **Ein PAT ist ein Geheimnis und wird niemals Teil der Git-Historie.**
