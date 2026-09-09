# SharePoint Sites

## Grundmodell

Sites sind die konkreten Informations- und Arbeitsraeume innerhalb der SharePoint-Zielarchitektur. Die fachlichen und technischen Attribute werden im Referenzprojekt im `Core_Workbook.xlsx` gepflegt.

## Site-Typen im Referenzmodell

- Hub Site
- Team Site
- Project Site
- Communication Site

Im dokumentierten Core-Stand sind 89 Sites vorgesehen: 10 Hub Sites, 69 Team Sites, 7 Project Sites und 3 Communication Sites.

## Beziehungen

Eine Site kann einer Hub Site zugeordnet sein. Owner-, Members- und Visitors-Gruppen werden je Site als eigene Berechtigungsobjekte modelliert. Das Core-Modell fuehrt dafuer unter anderem `HubSite` sowie Referenzen zwischen Sites und Groups.

## Lifecycle und Provisionierung

Die technische Ableitung erfolgt im Referenzprojekt in der Reihenfolge:

`Groups -> Sites -> Teams -> Channels`

Eine geplante Site ist nicht automatisch produktiv. Runtime-IDs werden erst nach erfolgreicher Provisionierung aus Microsoft 365 uebernommen.

## Source of Truth

Die konkreten Site-Stammdaten liegen im `DWD-SharePoint-M365/00_Core/01_Core_Workbook/Core_Workbook.xlsx`.
