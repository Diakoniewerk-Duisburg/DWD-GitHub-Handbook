# DWD GitHub Handbook

Dokumentation zum Verständnis und zur praktischen Nutzung von Git und GitHub.

Dieses Handbuch beschreibt die grundlegenden Konzepte sowie die praktische Arbeit mit Git und GitHub. Der Schwerpunkt liegt auf einer nachvollziehbaren und sicheren Arbeitsweise unter Windows mit Git, PowerShell und der GitHub-Weboberfläche.

## Inhalt

### 00 – Governance

Dokumentationsstandards und verbindliche Regeln für Aufbau, Benennung und Pflege des Handbuchs.

### 01 – Grundlagen

Grundlegende Begriffe und Zusammenhänge:

- [Was ist Git?](01_Grundlagen/Was_ist_Git.md)
- [Was ist GitHub?](01_Grundlagen/Was_ist_GitHub.md)
- [Unterschied zwischen Git und GitHub](01_Grundlagen/Unterschied_Git_und_GitHub.md)

### 02 – GitHub Online

Arbeiten direkt über die GitHub-Weboberfläche:

- [Übersicht](02_GitHub_Online/README.md)
- [Dateien anlegen](02_GitHub_Online/Dateien_anlegen.md)
- [Dateien bearbeiten](02_GitHub_Online/Dateien_bearbeiten.md)
- [Dateien verschieben](02_GitHub_Online/Dateien_verschieben.md)
- [Dateien löschen](02_GitHub_Online/Dateien_loeschen.md)
- [Änderungen vergleichen](02_GitHub_Online/Aenderungen_vergleichen.md)
- [Online committen](02_GitHub_Online/Commit_online.md)
- [Branch online](02_GitHub_Online/Branch_online.md)
- [Pull Request online](02_GitHub_Online/Pull_Request_online.md)

### 03 – Arbeitsweise

Der praktische Standardablauf für die tägliche lokale Arbeit:

- [Übersicht](03_Arbeitsweise/README.md)
- [Repository klonen](03_Arbeitsweise/Repository_klonen.md)
- [Änderungen prüfen](03_Arbeitsweise/Aenderungen_pruefen.md)
- [Commit erstellen](03_Arbeitsweise/Commit_erstellen.md)
- [Repository synchronisieren](03_Arbeitsweise/Repository_synchronisieren.md)

### 04 – HowTos

Schritt-für-Schritt-Anleitungen für konkrete Aufgaben:

- [HowTo-Übersicht](04_HowTos/README.md)
- [GitHub Repository anlegen](04_HowTos/GitHub_Repository_anlegen.md)
- [Lokales Repository nach GitHub übertragen](04_HowTos/Lokales_Repository_nach_GitHub_uebertragen.md)

### 05 – Praxisbeispiele

Konkrete Situationen aus der täglichen Arbeit mit Git und GitHub.

- [Übersicht](05_Praxisbeispiele/README.md)

### 06 – Authentifizierung

- [Übersicht](06_Authentifizierung/README.md)
- [HTTPS](06_Authentifizierung/HTTPS.md)
- [Personal Access Token](06_Authentifizierung/Personal_Access_Token.md)
- [SSH](06_Authentifizierung/SSH.md)

### 07 – Befehlsreferenz

Referenz der wichtigsten Git-Befehle mit Syntax, Erklärung und Beispielen.

- [Befehlsreferenz](07_Befehlsreferenz/README.md)

### 08 – Troubleshooting

Typische Fehlermeldungen und Probleme bei der Arbeit mit Git und GitHub sowie deren Ursachen und Lösungen.

- [Troubleshooting-Übersicht](08_Troubleshooting/README.md)

### 09 – Sicherheit

Grundlagen und Regeln für einen sicheren Umgang mit GitHub, Zugangsdaten, Tokens und vertraulichen Informationen.

- [Sicherheitsübersicht](09_Sicherheit/README.md)
- [Was gehört nicht in GitHub?](09_Sicherheit/Was_nicht_in_GitHub_gehoert.md)

### 10 – Lernpfad

Ein strukturierter Weg vom ersten Verständnis bis zur sicheren täglichen Arbeit mit Git und GitHub.

- [Lernpfad](10_Lernpfad/README.md)
- [Git und GitHub von Anfang bis Ende](10_Lernpfad/01_Git_und_GitHub_von_Anfang_bis_Ende.md)

### 11 – Checklisten

Kurze Checklisten für wiederkehrende Aufgaben und Kontrollpunkte.

- [Checklisten-Übersicht](11_Checklisten/README.md)
- [Repository anlegen](11_Checklisten/Repository_anlegen.md)
- [Repository übertragen](11_Checklisten/Repository_uebertragen.md)
- [Repository synchronisieren](11_Checklisten/Repository_synchronisieren.md)

## Zentrales Arbeitsmodell

Die lokale Arbeit mit Git lässt sich vereinfacht als Kette darstellen:

```text
Arbeitsverzeichnis
       ↓
    Staging
       ↓
Lokales Repository
       ↓
Remote Repository
       ↓
      GitHub
```

Dabei sind insbesondere folgende Begriffe zu unterscheiden:

- **Working Tree / Arbeitsverzeichnis:** Dateien, an denen gerade gearbeitet wird.
- **Staging:** Auswahl der Änderungen für den nächsten Commit.
- **Commit:** Ein nachvollziehbarer Versionsstand im lokalen Repository.
- **Remote Repository:** Das entfernte Repository, beispielsweise auf GitHub.
- **Push:** Übertragung lokaler Commits zum Remote.
- **Pull:** Abrufen von Änderungen vom Remote und deren Integration in den aktuellen lokalen Branch.

## Zentrale Regeln

### Commit ist nicht Push

Ein `git commit` speichert Änderungen zunächst lokal. Erst `git push` überträgt die lokalen Commits zum Remote-Repository.

### `git status` ist die erste Prüfung

Bei Unsicherheit über den aktuellen Zustand zuerst:

```powershell
git status
```

Danach bei Bedarf:

```powershell
git branch --show-current
git remote -v
git diff
```

### Vor dem Push prüfen

Vor einem Push sollte immer geprüft werden:

- Bin ich im richtigen Repository?
- Bin ich auf dem richtigen Branch?
- Ist das richtige Remote hinterlegt?
- Sind die gewünschten Änderungen committed?
- Enthält der Commit keine Geheimnisse oder vertraulichen Daten?

## Ziel des Handbuchs

Das Handbuch soll nicht nur einzelne Git-Befehle dokumentieren, sondern das Verständnis für die Arbeitsweise mit Git und GitHub vermitteln.

Die Dokumentation beantwortet deshalb sowohl:

- **Was mache ich?**
- **Wie mache ich es?**
- **Warum mache ich es so?**
- **Was kann dabei schiefgehen?**
- **Wie prüfe ich das Ergebnis?**

## Dokumentationssprache

Die Dokumentation wird grundsätzlich in deutscher Sprache erstellt.

Technische Begriffe, Git-Befehle, GitHub-Bezeichnungen und Quellcode werden in ihrer originalen Schreibweise übernommen.

## Dokumentationsprinzip

Dokumentationen sollen möglichst:

1. verständlich,
2. nachvollziehbar,
3. reproduzierbar,
4. praxisorientiert und
5. aktuell

sein.

Änderungen an der Dokumentation werden über Git versioniert und nachvollziehbar gespeichert.
