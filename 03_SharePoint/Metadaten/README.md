# SharePoint Metadaten

## Rolle

Metadaten beschreiben fachliche Eigenschaften von Dokumenten und anderen Inhalten und machen Informationen unabhaengig von einer reinen Ordnerstruktur auffindbar, filterbar und steuerbar.

## DWD-Grundsaetze

- Metadaten werden fachlich definiert und zentral wiederverwendbar gehalten.
- Pflichtfelder werden nur dort eingesetzt, wo sie fuer fachliche Vollstaendigkeit erforderlich sind.
- Werte aus kontrollierten Referenzmengen werden bevorzugt.
- Schluesselfelder und Beziehungen werden stabil modelliert; Anzeigenamen sind keine fachliche Identitaet.
- Metadaten muessen mit Inhaltstypen, Berechtigungen, Lifecycle und Suche abgestimmt werden.

## Bezug zum Referenzprojekt

Das Core-Modell des Projekts `DWD-SharePoint-M365` trennt fachliche Stammdaten, Governance-/Entscheidungsdaten, Provisionierungs-/Laufzeitinformationen sowie Audit-/Lifecycle-Informationen. Diese Trennung ist auch fuer SharePoint-Metadaten relevant.

## Source-of-Truth-Prinzip

Fachliche Stammwerte sollen nicht parallel in mehreren Listen oder Bibliotheken gepflegt werden. Die jeweilige Primaerquelle ist vor der Modellierung festzulegen.

## Beispiel

Eine Beschaffungsunterlage kann beispielsweise folgende Metadaten besitzen:

- Vorgangsnummer
- Organisationseinheit
- Kostenstelle
- Dokumenttyp
- Status
- Schutz-/Klassifikationsinformation
- Verantwortlicher
- Erstell- und Freigabestatus

## Quelle

`DWD-SharePoint-M365/00_Core/01_Core_Workbook/Core_Workbook.xlsx` sowie die Fach- und Architekturdokumentation des Referenzprojekts.
