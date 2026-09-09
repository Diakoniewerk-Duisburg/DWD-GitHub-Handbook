# Wissensquellen – Grundlagen

## Grundsatz

Die Qualitaet eines Agents haengt wesentlich von den verwendeten Wissensquellen ab. Wissensquellen muessen deshalb fachlich geeignet, aktuell, berechtigt und nachvollziehbar sein.

## Typische Wissensquellen

Je nach Agent und Produkt stehen unterschiedliche Quellen zur Verfuegung, unter anderem:

- SharePoint-Dateien, Ordner und Sites
- OneDrive-Inhalte
- Microsoft Teams-Inhalte
- Outlook-Inhalte
- eingebettete Dateien
- oeffentliche Webseiten
- Microsoft 365 Copilot Connectoren
- weitere Unternehmensdatenquellen ueber Copilot Studio

## Berechtigungen

Wissensquellen sind keine Abkuerzung fuer Berechtigungen. Ein Agent muss innerhalb der fuer den Benutzer geltenden Zugriffsgrenzen arbeiten.

Besonders bei SharePoint und OneDrive ist deshalb vor der Freigabe zu pruefen, ob die zugrunde liegende Informationsarchitektur und Berechtigungsstruktur bereits sauber ist.

## Auswahlkriterien

Eine Wissensquelle sollte nur verwendet werden, wenn sie:

1. fuer die Aufgabe fachlich erforderlich ist,
2. eine ausreichende Qualitaet besitzt,
3. aktuell gehalten wird,
4. fuer die Zielgruppe freigegeben ist,
5. keine unnoetigen oder sensiblen Daten einbezieht,
6. eindeutig einem Verantwortlichen zugeordnet werden kann.

## Grounding

Der Agent soll seine Antworten soweit moeglich auf definierte Wissensquellen stuetzen. Allgemeines Modellwissen und organisationsspezifisches Wissen sind deshalb gedanklich zu unterscheiden.

## DWD-Regel fuer Wissensquellen

Vor Aufnahme einer Quelle wird dokumentiert:

| Feld | Inhalt |
|---|---|
| Quelle | Name oder System |
| Zweck | Warum wird die Quelle benoetigt? |
| Besitzer | Fachlich verantwortliche Stelle |
| Berechtigung | Wer darf die Inhalte sehen? |
| Aktualisierung | Wie bleibt die Quelle aktuell? |
| Sensibilitaet | Schutzbedarf / Klassifizierung |
| Agent | Welcher Agent nutzt die Quelle? |
| Status | Entwurf / Freigegeben / Gesperrt |

## Primaerquelle

Microsoft Learn: [Wissensquellen fuer deklarative Agents](https://learn.microsoft.com/de-de/microsoft-365-copilot/extensibility/knowledge-sources)
