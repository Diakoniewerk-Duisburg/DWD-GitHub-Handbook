# SharePoint Listen

## Rolle

SharePoint-Listen sind die strukturierte Datenebene fuer fachliche Vorgangsdaten, Stammdaten und steuernde Prozessinformationen.

Im DWD-Zielmodell werden strukturierte Daten nicht automatisch als Dokumente behandelt. Die Entscheidung zwischen Liste, Bibliothek und anderen Datenspeichern richtet sich nach dem Informationsobjekt.

## Bezug zum Referenzprojekt

Das Referenzprojekt trennt fachliche Stammdaten, Governance-/Entscheidungsdaten, Provisionierungs-/Laufzeitinformationen sowie Audit-/Lifecycle-Daten. Diese Trennung ist bei der Modellierung von SharePoint-Listen zu beruecksichtigen.

## Grundsaetze

- stabile Schluesselfelder statt Anzeige-/Namenwerte als Join-Schluessel
- kontrollierte Auswahlwerte fuer definierte Fachwerte
- Trennung von Stammdaten und Laufzeitdaten
- nachvollziehbare Status- und Lifecycle-Felder
- Berechtigungen nach fachlicher Notwendigkeit
- keine redundante Pflege derselben Source-of-Truth-Daten

## Beispiel

Ein Beschaffungsvorgang kann als Liste modelliert werden, waehrend die zugehoerigen Angebote und Dokumente in einer Bibliothek liegen.

## Quelle

`DWD-SharePoint-M365/00_Core/01_Core_Workbook/Core_Workbook.xlsx` sowie die Architektur- und Fachanforderungsdokumentation.
