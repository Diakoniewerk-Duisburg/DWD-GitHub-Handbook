# Unterschied zwischen Git und GitHub

## 1. Kurz erklärt

Git und GitHub gehören zusammen, sind aber unterschiedliche Dinge.

**Git** ist ein Versionsverwaltungssystem.

**GitHub** ist eine Plattform für Git-Repositorys und die Zusammenarbeit an diesen Repositorys.

## 2. Vergleich

| Git | GitHub |
|---|---|
| Software zur Versionsverwaltung | Plattform für Git-Repositorys |
| läuft lokal | läuft als Onlinedienst |
| verwaltet Versionen | stellt Repositorys online bereit |
| funktioniert ohne Internet | benötigt für die Online-Nutzung eine Verbindung |
| arbeitet mit lokalen Repositorys | stellt entfernte Repositorys bereit |
| `git commit` | Commit über GitHub-Weboberfläche möglich |
| `git branch` | Branches über GitHub verwaltbar |
| `git push` | empfängt Änderungen |
| `git pull` | stellt Änderungen bereit |

## 3. Zusammenspiel

In der typischen Arbeitsweise werden Git und GitHub gemeinsam verwendet.

```text
             Lokaler Computer
                    │
                    ▼
             Lokales Git
                    │
             ┌──────┴──────┐
             │             │
          commit         status
             │
             ▼
        git push
             │
             ▼
          GitHub
             │
        git pull
             │
             ▼
        Lokales Git
```

## 4. Beispiel

Eine Markdown-Datei wird lokal geändert.

Danach:

```powershell
git status
```

zeigt die Änderung.

Anschließend:

```powershell
git add README.md
```

bereitet die Änderung vor.

Dann:

```powershell
git commit -m "Update README"
```

speichert die Änderung in der lokalen Git-Historie.

Und:

```powershell
git push
```

überträgt den Commit nach GitHub.

## 5. Arbeiten ohne GitHub

Git kann vollständig ohne GitHub verwendet werden.

Beispiel:

```text
Computer
└── Projekt
    └── .git
```

Die komplette Versionshistorie liegt lokal vor.

## 6. Arbeiten ohne lokales Git

Viele einfache Änderungen können auch direkt auf GitHub durchgeführt werden.

Beispiel:

```text
GitHub Repository
      │
      ▼
Datei bearbeiten
      │
      ▼
Commit erstellen
```

Für diese Arbeitsweise ist kein lokales Git erforderlich.

## 7. Merksatz

> **Git verwaltet die Versionen. GitHub stellt Git-Repositorys online bereit und ermöglicht Zusammenarbeit.**

## 8. Warum die Unterscheidung wichtig ist

Viele Fehlermeldungen und Probleme entstehen durch eine Vermischung der Begriffe.

Beispielsweise bedeutet:

```text
git status
```

eine lokale Git-Abfrage.

Dagegen ist die Bearbeitung einer Datei über die GitHub-Weboberfläche eine direkte Arbeit mit dem entfernten Repository.

Beide Arbeitsweisen können jedoch miteinander kombiniert werden.

## 9. Praktische Konsequenz

Für die tägliche Arbeit sollte immer klar sein:

**Wo arbeite ich gerade?**

```text
LOCAL
→ Lokales Repository
→ Git
→ PowerShell

oder

ONLINE
→ GitHub Repository
→ Browser
→ GitHub-Weboberfläche
```

Diese Unterscheidung ist eine der wichtigsten Grundlagen für die sichere Arbeit mit Git und GitHub.