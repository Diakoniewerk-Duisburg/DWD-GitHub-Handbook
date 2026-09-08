# DWD GitHub Handbook

Dokumentation zum Verständnis und zur praktischen Nutzung von **Git und GitHub**.

Dieses Handbuch beschreibt die Arbeit mit Git und GitHub von den Grundlagen über die direkte Bearbeitung im GitHub-Webinterface bis zur lokalen Arbeit mit Git und PowerShell.

Der Schwerpunkt liegt auf einer **praktischen, nachvollziehbaren und sicheren Arbeitsweise**.

---

## Ziel des Handbuchs

Das Handbook soll insbesondere folgende Fragen beantworten:

- Was ist Git?
- Was ist GitHub?
- Was ist der Unterschied zwischen Git und GitHub?
- Wie arbeite ich direkt im GitHub-Repository?
- Wie arbeite ich lokal mit Git?
- Wie übertrage ich ein lokales Repository nach GitHub?
- Wie synchronisiere ich mein lokales Repository mit GitHub?
- Was bedeuten die wichtigsten Git-Befehle?
- Wie gehe ich mit typischen Fehlern um?
- Was darf nicht in ein GitHub-Repository?
- Wie kann ich einen Git/GitHub-Vorgang anhand einer Checkliste durchführen?

---

# Inhaltsverzeichnis

## 00 – Governance

Grundlegende Regeln für die Erstellung und Pflege der Dokumentation.

- [Dokumentationsstandard](00_Governance/DOCUMENTATION_STANDARD.md)

---

## 01 – Grundlagen

Grundverständnis von Git und GitHub.

- [Was ist Git?](01_Grundlagen/Was_ist_Git.md)
- [Was ist GitHub?](01_Grundlagen/Was_ist_GitHub.md)
- [Unterschied zwischen Git und GitHub](01_Grundlagen/Unterschied_Git_und_GitHub.md)

**Empfohlene Reihenfolge:**

```text
Was ist Git?
      ↓
Was ist GitHub?
      ↓
Unterschied Git und GitHub
```

---

## 02 – Arbeiten direkt in GitHub

Dieser Bereich beschreibt die Arbeit **direkt im GitHub-Webinterface**, ohne ein lokales Repository verwenden zu müssen.

- [Übersicht GitHub Online](02_GitHub_Online/README.md)
- [Dateien anlegen](02_GitHub_Online/Dateien_anlegen.md)
- [Dateien bearbeiten](02_GitHub_Online/Dateien_bearbeiten.md)
- [Dateien verschieben](02_GitHub_Online/Dateien_verschieben.md)
- [Dateien löschen](02_GitHub_Online/Dateien_loeschen.md)
- [Änderungen vergleichen](02_GitHub_Online/Aenderungen_vergleichen.md)
- [Commit online erstellen](02_GitHub_Online/Commit_online.md)
- [Branch online verwenden](02_GitHub_Online/Branch_online.md)
- [Pull Request online](02_GitHub_Online/Pull_Request_online.md)

**Typischer Online-Arbeitsablauf:**

```text
Repository öffnen
      ↓
Datei auswählen
      ↓
Änderung durchführen
      ↓
Änderung prüfen
      ↓
Commit
      ↓
Ergebnis kontrollieren
```

---

## 03 – Lokale Arbeitsweise

Dieser Bereich beschreibt die Arbeit mit einem lokal vorhandenen Repository.

- [Übersicht lokale Arbeitsweise](03_Arbeitsweise/README.md)
- [Repository klonen](03_Arbeitsweise/Repository_klonen.md)
- [Änderungen prüfen](03_Arbeitsweise/Aenderungen_pruefen.md)
- [Commit erstellen](03_Arbeitsweise/Commit_erstellen.md)
- [Repository synchronisieren](03_Arbeitsweise/Repository_synchronisieren.md)

**Standardablauf:**

```text
git pull
   ↓
Arbeiten
   ↓
git status
   ↓
git diff
   ↓
git add
   ↓
git diff --staged
   ↓
git commit
   ↓
git push
   ↓
Kontrolle
```

---

## 04 – HowTos

Vollständige Schritt-für-Schritt-Anleitungen für typische Aufgaben.

- [HowTos – Übersicht](04_HowTos/README.md)
- [Lokales Repository nach GitHub übertragen](04_HowTos/01_Repository/Lokales_Repository_nach_GitHub_uebertragen.md)

Die HowTos sind für konkrete Aufgaben gedacht.

Beispiel:

> Ich habe ein lokales Repository und möchte es in ein neues GitHub-Repository übertragen.

Dann wird nicht die gesamte Dokumentation durchsucht, sondern direkt das entsprechende HowTo verwendet.

---

## 07 – Befehlsreferenz

Schnellreferenz für häufig verwendete Git-Befehle.

- [Befehlsreferenz](07_Befehlsreferenz/README.md)
- [git status](07_Befehlsreferenz/git_status.md)
- [git add](07_Befehlsreferenz/git_add.md)
- [git commit](07_Befehlsreferenz/git_commit.md)
- [git pull](07_Befehlsreferenz/git_pull.md)
- [git push](07_Befehlsreferenz/git_push.md)
- [git clone](07_Befehlsreferenz/git_clone.md)
- [git diff](07_Befehlsreferenz/git_diff.md)
- [git log](07_Befehlsreferenz/git_log.md)
- [git branch](07_Befehlsreferenz/git_branch.md)
- [git remote](07_Befehlsreferenz/git_remote.md)

### Die wichtigsten Befehle

| Befehl | Bedeutung |
|---|---|
| `git status` | Zustand prüfen |
| `git add` | Änderungen für Commit vormerken |
| `git commit` | Änderungen lokal speichern |
| `git pull` | Änderungen von GitHub holen |
| `git push` | lokale Commits zu GitHub übertragen |
| `git clone` | Repository lokal kopieren |
| `git diff` | Änderungen anzeigen |
| `git log` | Historie anzeigen |
| `git branch` | Branches verwalten |
| `git remote` | Remote-Verbindungen verwalten |

---

## 08 – Troubleshooting

Hier werden typische Fehler und Warnungen erklärt.

- [Troubleshooting – Übersicht](08_Troubleshooting/README.md)
- [Nothing to commit](08_Troubleshooting/Nothing_to_commit.md)
- [Push abgelehnt](08_Troubleshooting/Push_abgelehnt.md)
- [Merge Conflict](08_Troubleshooting/Merge_Conflict.md)
- [LF/CRLF-Warnung](08_Troubleshooting/LF_CRLF_Warnung.md)

### Grundprinzip der Fehleranalyse

```text
Fehlermeldung
      ↓
Bedeutung verstehen
      ↓
Repository-Zustand prüfen
      ↓
Ursache feststellen
      ↓
Gezielte Lösung
      ↓
Ergebnis kontrollieren
```

**Nicht blind Befehle ausführen.**

Insbesondere sollten destruktive Befehle wie `git reset --hard` oder `git push --force` nicht ohne vorherige Prüfung eingesetzt werden.

---

## 09 – Sicherheit

Sicherheitsrelevante Regeln für die Arbeit mit Git und GitHub.

- [Sicherheit – Übersicht](09_Sicherheit/README.md)
- [Personal Access Token](09_Sicherheit/Personal_Access_Token.md)
- [Was gehört nicht in GitHub?](09_Sicherheit/Was_nicht_in_GitHub_gehoert.md)

Grundregel:

> **Alles, was mit `git add` vorgemerkt und anschließend committed wird, kann Bestandteil der Git-Historie werden.**

Deshalb muss vor einem Commit geprüft werden, welche Dateien tatsächlich übertragen werden.

---

## 11 – Checklisten

Kurze operative Checklisten für wiederkehrende Aufgaben.

- [Checklisten – Übersicht](11_Checklisten/README.md)
- [Repository anlegen](11_Checklisten/Repository_anlegen.md)
- [Repository übertragen](11_Checklisten/Repository_uebertragen.md)
- [Repository synchronisieren](11_Checklisten/Repository_synchronisieren.md)

Die Checklisten sind bewusst kurz gehalten.

Sie ersetzen die ausführlichen HowTos nicht.

---

# Welchen Bereich sollte ich verwenden?

| Wenn ich ... | Dann gehe ich zu ... |
|---|---|
| Git grundsätzlich verstehen möchte | [01 – Grundlagen](01_Grundlagen/) |
| direkt auf GitHub arbeiten möchte | [02 – GitHub Online](02_GitHub_Online/) |
| lokal mit Git arbeiten möchte | [03 – Arbeitsweise](03_Arbeitsweise/) |
| eine konkrete Aufgabe durchführen möchte | [04 – HowTos](04_HowTos/) |
| einen einzelnen Git-Befehl nachschlagen möchte | [07 – Befehlsreferenz](07_Befehlsreferenz/) |
| einen Fehler analysieren möchte | [08 – Troubleshooting](08_Troubleshooting/) |
| wissen möchte, was sicherheitskritisch ist | [09 – Sicherheit](09_Sicherheit/) |
| eine kurze Schrittfolge brauche | [11 – Checklisten](11_Checklisten/) |

---

# Empfohlene Lernreihenfolge

Wer Git und GitHub neu kennenlernt, sollte das Handbook in dieser Reihenfolge verwenden:

```text
01 Grundlagen
      ↓
02 GitHub Online
      ↓
03 Lokale Arbeitsweise
      ↓
04 HowTos
      ↓
07 Befehlsreferenz
      ↓
08 Troubleshooting
      ↓
09 Sicherheit
      ↓
11 Checklisten
```

---

# Grundprinzip des Handbooks

Das Handbook folgt einem einfachen Grundsatz:

> **Erst verstehen, dann durchführen, anschließend kontrollieren.**

Git und GitHub sind keine Sammlung isolierter Befehle.

Entscheidend ist das Verständnis des Zusammenspiels zwischen:

```text
Arbeitsverzeichnis
      ↓
Staging
      ↓
lokaler Commit
      ↓
lokales Repository
      ↓
GitHub Repository
```

---

# Dokumentationsgrundsätze

Die Dokumentation soll:

- verständlich sein
- praktische Beispiele enthalten
- reale Arbeitsabläufe abbilden
- Risiken sichtbar machen
- Prüfungen ausdrücklich beschreiben
- keine Zugangsdaten oder Geheimnisse enthalten
- nachvollziehbare und reproduzierbare Vorgehensweisen verwenden

Die verbindlichen Regeln stehen im [Dokumentationsstandard](00_Governance/DOCUMENTATION_STANDARD.md).

---

# Status

Das Handbook wird fortlaufend erweitert.

Neue Inhalte werden nach Themenbereichen eingeordnet und über diese zentrale Navigation erreichbar gemacht.