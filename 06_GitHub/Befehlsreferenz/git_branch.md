# git branch

## Zweck

`git branch` dient zur Anzeige und Verwaltung von Branches.

Branches ermöglichen voneinander getrennte Entwicklungs- oder Arbeitsstände.

## Branches anzeigen

```powershell
git branch
```

Der aktuell verwendete Branch wird normalerweise mit `*` gekennzeichnet.

Beispiel:

```text
* main
  documentation-update
```

## Neuen Branch erstellen

```powershell
git branch documentation-update
```

Damit wird ein neuer Branch erstellt.

Der aktuelle Branch wird dadurch nicht automatisch gewechselt.

## Branch wechseln

```powershell
git switch documentation-update
```

## Branch erstellen und direkt wechseln

```powershell
git switch -c documentation-update
```

Dies ist für neue Arbeiten häufig der praktischste Weg.

## Branch löschen

Nach abgeschlossener Arbeit kann ein lokaler Branch gelöscht werden:

```powershell
git branch -d documentation-update
```

## Wichtiger Hinweis

Ein Branch kann lokal und auf dem Remote-Repository vorhanden sein.

Diese beiden Zustände sind nicht automatisch identisch.

Beispiel:

```text
Lokales Repository
└── documentation-update

GitHub
└── documentation-update
```

## Branch kontrollieren

Vor einer Änderung sollte immer bekannt sein, auf welchem Branch gearbeitet wird.

Dafür:

```powershell
git status
```

oder:

```powershell
git branch
```

## Merksatz

> Ein Branch ist ein eigener Arbeitszweig innerhalb der Git-Historie.