# SharePoint Lifecycle

## Grundsatz

SharePoint-Informationsraeume benoetigen einen definierten Lebenszyklus von Planung ueber Provisionierung und Nutzung bis zu Aenderung, Stilllegung und gegebenenfalls Loeschung oder Archivierung.

## Bezug zum Referenzprojekt

Das Projekt `DWD-SharePoint-M365` trennt Stammdaten, Governance/Entscheidungen, Provisionierungs-/Laufzeitinformationen sowie Audit-/Lifecycle-Daten. Diese Trennung ist auch fuer den SharePoint-Lifecycle relevant.

## Lebenszyklus

```text
Planung
  -> Pruefung
  -> Freigabe
  -> Provisionierung
  -> Betrieb
  -> Aenderung / Review
  -> Stilllegung
  -> Archivierung / Loeschung
```

## Regeln

- geplante Objekte sind nicht automatisch produktiv
- jede wesentliche Aenderung wird nachvollziehbar dokumentiert
- Owner und fachliche Verantwortung muessen bekannt sein
- Berechtigungen werden bei Rollen-/Organisationsaenderungen erneut bewertet
- Lifecycle, Aufbewahrung und Loeschung werden mit Datenschutz und Compliance abgestimmt
- technische Runtime-IDs werden erst nach erfolgreicher Provisionierung uebernommen

## Quelle

`DWD-SharePoint-M365/00_Core/01_Core_Workbook/Core_Workbook.xlsx` sowie die Projektbereiche Architektur, Governance, Berechtigung und Betrieb.
