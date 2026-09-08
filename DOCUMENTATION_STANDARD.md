# Documentation Standard

## Zweck

Dieses Dokument definiert die grundlegenden Regeln für die Erstellung und Pflege der Dokumentation im Repository `DWD-GitHub-Handbook`.

Ziel ist eine einheitliche, verständliche und langfristig wartbare Dokumentation.

## Sprache

Die Dokumentation wird grundsätzlich in deutscher Sprache erstellt.

Englische Begriffe werden verwendet, wenn sie Bestandteil der Git- oder GitHub-Terminologie sind.

Beispiele:

- Repository
- Branch
- Commit
- Pull Request
- Merge
- Remote
- Working Tree

Git-Befehle werden unverändert dargestellt.

Beispiel:

```powershell
git status
git add .
git commit -m "Update documentation"
git push
```

## Dateinamen

Dateinamen werden:

- ohne Umlaute,
- ohne Sonderzeichen,
- mit verständlichen Begriffen,
- möglichst eindeutig und
- ohne Versionsnummer

erstellt.

Beispiel:

```text
Repository_synchronisieren.md
```

Nicht:

```text
Repository_synchronisieren_v1.2.md
```

Versionen werden über Git und die Repository-Historie nachvollziehbar.

## Verzeichnisstruktur

Die Verzeichnisstruktur folgt einer thematischen Ordnung.

Die Nummerierung dient der Orientierung und der stabilen Strukturierung des Handbuchs.

```text
00_Governance
01_Grundlagen
02_GitHub_Online
03_Arbeitsweise
04_HowTos
07_Befehlsreferenz
08_Troubleshooting
09_Sicherheit
11_Checklisten
```

Freie Nummernbereiche können später für weitere Themen verwendet werden.

## HowTos

HowTos beschreiben konkrete Aufgaben Schritt für Schritt.

Ein HowTo soll nach Möglichkeit folgende Struktur verwenden:

1. Zweck
2. Voraussetzungen
3. Ausgangssituation
4. Durchführung
5. Kontrolle
6. Typische Fehler
7. Ergebnis

## Troubleshooting

Fehlerbeschreibungen sollen nach Möglichkeit folgende Informationen enthalten:

- Fehlermeldung
- Bedeutung
- mögliche Ursache
- Prüfung
- Lösung
- Kontrolle nach der Lösung

## Beispiele

Beispiele müssen eindeutig als Beispiele erkennbar sein.

Konkrete Zugangsdaten, Tokens, Passwörter oder andere vertrauliche Informationen dürfen niemals in Beispielen dokumentiert werden.

## Änderungen

Dokumentationsänderungen werden grundsätzlich über Git versioniert.

Größere Änderungen sollen mit einer aussagekräftigen Commit Message versehen werden.

Beispiel:

```text
Add GitHub online workflow documentation
```

## Qualität

Vor dem Commit soll geprüft werden:

- Ist der Inhalt verständlich?
- Sind die beschriebenen Schritte nachvollziehbar?
- Sind Befehle korrekt dargestellt?
- Sind Pfade und Dateinamen korrekt?
- Enthält die Dokumentation vertrauliche Informationen?
- Ist die Dokumentation an der richtigen Stelle abgelegt?

## Grundsatz

Die Dokumentation soll die tatsächliche Arbeitsweise abbilden.

Theoretische Inhalte werden aufgenommen, wenn sie zum Verständnis oder zur sicheren Anwendung von Git und GitHub erforderlich sind.