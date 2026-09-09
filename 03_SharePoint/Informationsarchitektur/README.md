# SharePoint Informationsarchitektur

## Referenz

Die Informationsarchitektur folgt dem im Referenzprojekt `DWD-SharePoint-M365` beschriebenen Modell aus Organisationsstruktur, Hub Sites, Sites, Teams und Navigation.

## Hub-Modell

```text
HUB-UNTERNEHMEN
├── HUB-LEITUNG
├── HUB-QUERSCHNITT
├── HUB-VERWALTUNG
└── weitere Hubs / Sites
```

Die konkrete Zuordnung wird im Core-Modell ueber `HubSite` gefuehrt.

## Organisationsbezug

Die fachliche Organisationsstruktur und die technische SharePoint-Struktur sind zu unterscheiden. Nicht jede fachliche Organisationsebene benoetigt einen eigenen Hub. Untergeordnete Strukturen koennen ueber eigenstaendige Sites, Teams und Navigation abgebildet werden.

Das Referenzprojekt beschreibt dies am Beispiel KJF: `HUB-KJF` dient als technischer Hub; die fachlich tiefer gegliederte Struktur wird ueber OrganizationUnits, Sites, Teams und Navigation abgebildet.

## Site-Typen

Der dokumentierte Referenzstand umfasst:

| SiteType | Referenzanzahl |
|---|---:|
| Hub Site | 10 |
| Team Site | 69 |
| Project Site | 7 |
| Communication Site | 3 |
| Gesamt | 89 |

Die Zahlen sind Projektstand und keine technischen SharePoint-Grenzwerte.

## Quelle

`DWD-SharePoint-M365/05_Documentation/02_Architektur/SharePoint-Informationsarchitektur.md`
