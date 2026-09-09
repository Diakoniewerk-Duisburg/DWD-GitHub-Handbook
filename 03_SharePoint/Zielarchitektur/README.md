# SharePoint Zielarchitektur

## Zweck

Dieser Bereich fuehrt die SharePoint-relevanten Architekturentscheidungen und das Zielmodell aus dem Referenzprojekt `DWD-SharePoint-M365` in der zentralen Knowledgebase zusammen.

Die konkrete Objektplanung bleibt im SharePoint-Projekt. Diese Knowledgebase dokumentiert die fachlich und technisch relevanten Regeln als dauerhaftes Wissen.

## Referenzprojekt

`Diakoniewerk-Duisburg/DWD-SharePoint-M365`

## Architekturgrundsaetze

- SharePoint Online bildet Sites, Hub-Struktur und Dokumentablage innerhalb der M365-Zielarchitektur.
- `Core_Workbook.xlsx` ist im Referenzprojekt die Source of Truth fuer fachliche und strukturelle Stammdaten.
- Die Hub-Struktur bildet uebergeordnete Informations- und Navigationsraeume ab; eine fachliche Organisationsebene erzeugt nicht automatisch einen eigenen Hub.
- `HUB-UNTERNEHMEN` ist als uebergeordnete Hub Site definiert.
- Die Provisionierungsabhaengigkeit ist `Groups -> Sites -> Teams -> Channels`.
- Eine bestandene Daten-/Modellvalidierung ist keine automatische Produktionsfreigabe.

## Aktueller Referenzstand

Der im Referenzprojekt dokumentierte Core-Stand beschreibt 89 Sites, darunter 10 Hub Sites, 69 Team Sites, 7 Project Sites und 3 Communication Sites. Zusaetzlich werden 255 Groups, 90 Teams und 90 Channels im aktuellen Core-Stand ausgewiesen.

Diese Werte sind Bestands-/Planungswerte des Referenzprojekts und keine allgemeine SharePoint-Produktgrenze.

## Verwandte Bereiche

- `../Informationsarchitektur/`
- `../Sites/`
- `../Listen/`
- `../Bibliotheken/`
- `../Inhaltstypen/`
- `../Metadaten/`
- `../Berechtigungen/`
- `../Lifecycle/`
