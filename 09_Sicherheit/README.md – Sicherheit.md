# Git und GitHub – Sicherheit

## 1. Zweck

Git-Repositorys können sensible Informationen enthalten. Ein GitHub-Repository muss deshalb immer als Teil der IT-Sicherheits- und Datenschutzanforderungen betrachtet werden.

Dieses Kapitel beschreibt grundlegende Sicherheitsregeln für die Arbeit mit Git und GitHub.

## 2. Grundregel

> Was nicht in einem Repository veröffentlicht oder gespeichert werden darf, darf auch nicht durch Git versioniert werden.

Das gilt unabhängig davon, ob das Repository öffentlich oder privat ist.

## 3. Niemals in ein Repository speichern

Insbesondere dürfen keine folgenden Informationen in einem Repository abgelegt werden:

- Passwörter
- Personal Access Tokens
- API-Schlüssel
- private SSH-Schlüssel
- Zertifikats-Private-Keys
- Zugangsdaten
- Connection Strings mit Zugangsdaten
- Secrets
- personenbezogene Daten, sofern nicht ausdrücklich erforderlich und zulässig
- vertrauliche Unternehmensinformationen
- produktive Konfigurationsdaten mit Geheimnissen

## 4. Warum Löschen nicht ausreicht

Eine Datei kann aus dem aktuellen Repository-Stand gelöscht werden.

Die vorherige Version kann jedoch weiterhin Bestandteil der Git-Historie sein.

Beispiel:

```text id="5f7z5j"
Commit 1
└── secret.txt

Commit 2
└── secret.txt gelöscht
```

Das Secret kann dadurch weiterhin in Commit 1 vorhanden sein.

Deshalb gilt:

> Ein versehentlich gespeichertes Secret muss als kompromittiert betrachtet werden.

Das Secret muss gegebenenfalls sofort ungültig gemacht und ersetzt werden.

## 5. Private Repositorys

Ein privates Repository ist nicht öffentlich sichtbar.

Das bedeutet jedoch nicht, dass dort beliebige vertrauliche Informationen gespeichert werden dürfen.

Zusätzlich müssen berücksichtigt werden:

- Berechtigungen
- Benutzer
- Organisation
- Repository-Einstellungen
- Unternehmensrichtlinien
- Datenschutzanforderungen

## 6. Zugangsdaten

Zugangsdaten dürfen niemals direkt in Dateien gespeichert werden.

Nicht zulässig:

```text id="e2kg2g"
username=admin
password=MeinPasswort
```

Auch nicht in:

- Markdown
- JSON
- YAML
- PowerShell
- Konfigurationsdateien
- Beispieldateien

## 7. Beispielwerte

Für Dokumentation und Beispiele müssen Platzhalter verwendet werden.

Beispiel:

```text id="0l6j0k"
https://github.com/Organisation/Repository.git
```

oder:

```text id="7z6w8n"
<Repository-URL>
```

Echte Zugangsdaten gehören niemals in Beispiele.

## 8. Vor dem Commit prüfen

Vor jedem Commit sollte geprüft werden:

```text id="qup5i1"
Welche Dateien wurden geändert?
          ↓
Enthalten sie sensible Informationen?
          ↓
Sind neue Dateien enthalten?
          ↓
Sind Konfigurationsdateien betroffen?
          ↓
git diff
          ↓
Commit
```

## 9. Vor dem Push prüfen

Besonders vor einem Push nach GitHub:

```powershell id="aqn9v3"
git status
git diff --staged
```

Bei Unsicherheit sollte der Push nicht durchgeführt werden.

## 10. Force Push

Befehle wie:

```powershell id="z4s3j7"
git push --force
```

dürfen nicht ohne vorherige Prüfung verwendet werden.

Ein Force Push kann die Historie eines Remote-Repositorys überschreiben.

## 11. Reset

Auch destruktive Befehle wie:

```powershell id="2l9w5m"
git reset --hard
```

dürfen nicht blind eingesetzt werden.

Sie können lokale Änderungen verwerfen.

## 12. Grundsatz

Sicherheit beginnt nicht erst bei den GitHub-Einstellungen.

Sie beginnt bereits bei der Frage:

> Welche Datei nehme ich überhaupt in Git auf?