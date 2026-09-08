# Personal Access Token

## 1. Zweck

Ein Personal Access Token (PAT) kann zur Authentifizierung gegenüber GitHub verwendet werden.

Ein Token ist ein Geheimnis und muss entsprechend geschützt werden.

## 2. Grundregel

> Ein Personal Access Token ist wie ein Passwort zu behandeln.

Ein Token darf niemals:

- in ein Repository committed werden
- in Markdown-Dateien dokumentiert werden
- in Screenshots sichtbar sein
- per E-Mail weitergegeben werden
- in Chatnachrichten veröffentlicht werden
- in Skripten im Klartext hinterlegt werden

## 3. Verwendung

Wenn GitHub eine Authentifizierung über ein Token benötigt, sollte das Token über einen geeigneten sicheren Mechanismus bereitgestellt werden.

Das Token selbst gehört nicht in den Projektinhalt.

## 4. Dokumentation

Wenn ein HowTo die Verwendung eines Tokens beschreibt, werden ausschließlich Platzhalter verwendet.

Beispiel:

```text id="6aq6dx"
<PERSONAL_ACCESS_TOKEN>
```

Nicht:

```text id="z1ib5u"
ghp_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```

## 5. Versehentlich veröffentlichtes Token

Wenn ein Token versehentlich in Git oder GitHub gespeichert wurde:

1. Token nicht weiterverwenden.
2. Token unverzüglich widerrufen.
3. Neues Token erzeugen, falls erforderlich.
4. Prüfen, wo das Token gespeichert wurde.
5. Git-Historie auf das Vorkommen prüfen.
6. Betroffene Systeme kontrollieren.

Das bloße Löschen der Datei reicht nicht aus.

## 6. Token und Git-Historie

Wurde ein Token committed, kann es weiterhin in einem älteren Commit vorhanden sein.

Beispiel:

```text id="w1op5j"
Commit A
└── config.txt
      └── Token

Commit B
└── config.txt geändert
```

Auch wenn der aktuelle Stand das Token nicht mehr enthält, kann es in Commit A weiterhin vorhanden sein.

## 7. Dokumentationsregel

In diesem Repository werden niemals echte Tokens dokumentiert.

Verwendet werden ausschließlich Platzhalter.

Beispiel:

```text id="gslfki"
TOKEN=<PERSONAL_ACCESS_TOKEN>
```

## 8. Merksatz

> Ein Token, das einmal veröffentlicht wurde, muss als kompromittiert betrachtet werden.