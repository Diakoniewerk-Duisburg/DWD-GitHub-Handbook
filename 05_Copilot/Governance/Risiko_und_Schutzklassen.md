# Risiko- und Schutzklassen fuer Agents

## Zweck

Nicht jeder Agent benoetigt dieselbe Governance. Die Schutzklasse wird aus Daten, Aktionen, Auswirkungen und Autonomie abgeleitet.

## Klassen

| Klasse | Charakter | Beispiel | Mindestkontrolle |
|---|---|---|---|
| R0 | Informativ | allgemeine Wissensabfrage | Quellen, Qualitaet |
| R1 | Assistiv | Entwurf, Zusammenfassung, Analyse | Benutzerpruefung |
| R2 | Prozessbezogen | Workflow oder strukturierte Aktion | definierte Rechte, Tests, Protokollierung |
| R3 | Kritisch | Berechtigungen, personenbezogene oder wesentliche Prozessentscheidungen | Human-in-the-Loop, starke Freigabe, Audit |
| R4 | Hochkritisch | weitreichende autonome oder irreversible Aktionen | grundsaetzlich keine autonome Ausfuehrung ohne ausdrueckliche Sonderfreigabe |

## Einstufung

Die hoechste relevante Auswirkung bestimmt die Schutzklasse. Zu betrachten sind insbesondere:

- Sensibilitaet der Daten
- Personenbezug
- Umfang der Daten
- Schreib- und Loeschrechte
- finanzielle oder organisatorische Auswirkungen
- Irreversibilitaet
- Autonomiestufe
- Reichweite der Aktion

Die Schutzklasse ist keine Lizenz- oder Produktklassifikation, sondern ein DWD-Governance-Modell.

## Grundsatz

Mit steigender Schutzklasse steigen Nachweis-, Test-, Freigabe- und Kontrollanforderungen.
