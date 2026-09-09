# SharePoint Berechtigungen

## Grundprinzip

Berechtigungen werden im DWD-Modell rollen- und gruppenbasiert aufgebaut. Eine Site verfuegt grundsaetzlich ueber Owner-, Members- und Visitors-Gruppen.

Beispiel:

```text
Site
├── SP-<SITE>-OWNERS
├── SP-<SITE>-MEMBERS
└── SP-<SITE>-VISITORS
```

## Referenzprojekt

Im `DWD-SharePoint-M365` werden Gruppen im Core-Modell ueber Beziehungen wie `Groups.SourceSiteId` und `Groups.SourceSite` der jeweiligen Site zugeordnet.

## Grundsaetze

- Least Privilege
- Gruppen statt individueller Berechtigungsvergabe als Standard
- fachliche Verantwortlichkeit bestimmt den Zugriff
- Vererbung bevorzugen; individuelle Berechtigungsdurchbrueche nur bei begruendetem Bedarf
- Lesen und Schreiben fachlich unterscheiden
- privilegierte Rollen gesondert pruefen
- Berechtigungen mit Datenschutz, Klassifikation und Lifecycle abstimmen

## Provisionierung

Die technische Abhaengigkeit des Referenzmodells lautet `Groups -> Sites -> Teams -> Channels`. Damit sind erforderliche Gruppen vor der Site-Provisionierung zu beruecksichtigen.

## Abgrenzung

Die hier beschriebenen Prinzipien sind Knowledgebase-Regeln. Die konkreten Gruppen, Rollen und Zuordnungen verbleiben als Stammdaten im Referenzprojekt.

## Quelle

`DWD-SharePoint-M365/05_Documentation/02_Architektur/SharePoint-Informationsarchitektur.md` sowie die Dokumentation `05_Documentation/03_Berechtigungskonzept`.
