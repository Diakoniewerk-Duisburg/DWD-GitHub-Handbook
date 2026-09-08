# Was ist Git?

## 1. Zweck

Git ist ein verteiltes Versionsverwaltungssystem.

Git wird verwendet, um Änderungen an Dateien und insbesondere an Quellcode und Dokumentationen nachvollziehbar zu speichern.

Git ermöglicht unter anderem:

- Änderungen zu verfolgen
- frühere Stände wiederherzustellen
- Änderungen miteinander zu vergleichen
- verschiedene Entwicklungsstände parallel zu verwalten
- Änderungen eindeutig zu dokumentieren
- lokal ohne permanente Verbindung zu einem Server zu arbeiten

Git ist eine Software, die auf dem eigenen Computer ausgeführt wird.

## 2. Warum wird Git benötigt?

Bei der Arbeit an Dateien entstehen regelmäßig Änderungen.

Ohne Versionsverwaltung kann beispielsweise schnell unklar werden:

- Was wurde geändert?
- Wann wurde es geändert?
- Wer hat es geändert?
- Warum wurde es geändert?
- Welcher Stand ist aktuell?
- Wie kann ich einen früheren Stand wiederherstellen?

Git beantwortet diese Fragen über eine Versionshistorie.

## 3. Repository

Git speichert die Versionsinformationen in einem sogenannten Repository.

Ein Repository enthält:

- die verwalteten Dateien
- die Git-Versionshistorie
- Informationen über Branches
- Informationen über Commits
- Verweise auf entfernte Repositorys

Ein Repository kann vollständig lokal auf einem Computer existieren.

Beispiel:

```text
D:\GitHub\MeinProjekt\
```

## 4. Working Tree

Das Arbeitsverzeichnis eines Git-Repositorys wird als Working Tree bezeichnet.

Hier befinden sich die Dateien, an denen gearbeitet wird.

Beispiel:

```text
MeinProjekt/
├── README.md
├── Dokumentation/
└── Scripts/
```

Wenn eine Datei verändert wird, erkennt Git diese Änderung.

Mit:

```powershell
git status
```

kann der aktuelle Zustand geprüft werden.

## 5. Staging

Änderungen werden vor einem Commit zunächst für die Aufnahme vorbereitet.

Dieser Bereich wird Staging Area oder Index genannt.

Beispiel:

```powershell
git add README.md
```

Damit wird die Änderung an `README.md` für den nächsten Commit vorgemerkt.

## 6. Commit

Ein Commit speichert einen definierten Stand der vorbereiteten Änderungen in der Git-Historie.

Beispiel:

```powershell
git commit -m "Update documentation"
```

Ein Commit enthält unter anderem:

- die enthaltenen Änderungen
- Zeitpunkt
- Autor
- Commit-Nachricht
- eine eindeutige Kennung

Ein Commit stellt damit einen nachvollziehbaren Punkt in der Versionshistorie dar.

## 7. Branch

Ein Branch ermöglicht es, unabhängig vom Hauptentwicklungsstand an Änderungen zu arbeiten.

Der häufig verwendete Hauptbranch heißt beispielsweise:

```text
main
```

Weitere Branches können beispielsweise für neue Funktionen oder Änderungen angelegt werden.

## 8. Git ist zunächst lokal

Ein wichtiger Punkt:

**Git und GitHub sind nicht dasselbe.**

Git kann vollständig lokal verwendet werden.

Zum Beispiel:

```text
Lokaler Computer
      │
      ▼
   Git
      │
      ▼
Lokales Repository
```

Eine Internetverbindung ist für viele Git-Arbeiten nicht erforderlich.

## 9. Git und entfernte Repositorys

Git kann lokale Repositorys mit einem entfernten Repository synchronisieren.

Ein entferntes Repository wird häufig als `origin` bezeichnet.

Beispiel:

```powershell
git remote -v
```

zeigt die hinterlegten Verbindungen.

Mit:

```powershell
git push
```

werden lokale Commits zu einem entfernten Repository übertragen.

Mit:

```powershell
git pull
```

werden Änderungen aus einem entfernten Repository abgerufen und in den lokalen Stand integriert.

## 10. Grundprinzip

Der typische lokale Git-Arbeitsablauf ist:

```text
Datei bearbeiten
      │
      ▼
git status
      │
      ▼
git add
      │
      ▼
git commit
      │
      ▼
git push
```

Git sorgt dabei für die lokale Versionsverwaltung.

GitHub kann anschließend als zentraler bzw. gemeinsam genutzter Speicherort für das Repository dienen.