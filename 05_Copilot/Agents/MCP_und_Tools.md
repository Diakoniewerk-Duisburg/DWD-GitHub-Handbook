# MCP und Tools

## Einordnung

Tools erweitern einen Agenten um konkrete Faehigkeiten. MCP (Model Context Protocol) ist ein standardisierter Integrationsweg, ueber den Agenten Tools und Datenquellen anbinden koennen.

MCP ist dabei eine technische Integrationsschicht, keine fachliche Berechtigung. Die Entscheidung, was ein Agent tun darf, bleibt Teil von Agentenspezifikation, Identitaet, Berechtigungsmodell und Governance.

## Tool-Kategorien

- Informationszugriff
- Suche und Abfrage
- Berechnung und Analyse
- Dateiverarbeitung
- Prozess- und Workflow-Aktionen
- Schreibende Systemaktionen
- Kommunikation und Benachrichtigung

## DWD-Pruefung eines Tools

Vor einer Freigabe sind mindestens festzuhalten:

| Pruefpunkt | Frage |
|---|---|
| Zweck | Welches fachliche Problem loest das Tool? |
| Identitaet | Unter welcher Identitaet wird es ausgefuehrt? |
| Rechte | Welche minimalen Rechte sind erforderlich? |
| Eingaben | Welche Daten darf das Tool erhalten? |
| Ausgaben | Welche Daten liefert es zurueck? |
| Nebenwirkungen | Welche Veraenderungen kann es ausloesen? |
| Fehler | Was passiert bei Fehlern oder Teilerfolg? |
| Audit | Wie wird die Nutzung nachvollziehbar? |
| Freigabe | Wer verantwortet die fachliche und technische Freigabe? |

## Sicherheitsgrundsatz

Ein Tool darf niemals als vertrauenswuerdig gelten, nur weil es ueber einen standardisierten Protokollweg erreichbar ist. Tool-Beschreibung, Endpunkt, Identitaet, Berechtigungen, Datenfluss und Nebenwirkungen muessen bewertet werden.

## Bezug zu GitHub

GitHub Copilot kann agentische Funktionen mit Skills und MCP verbinden. Fuer DWD ist daher zwischen der technischen Nutzung von Tools und der fachlichen Verantwortung fuer Repository-Inhalte, Codeaenderungen, Pull Requests und Releases zu unterscheiden.

## Verwandte Dokumente

- [Connectoren und Aktionen](Connectoren_und_Aktionen.md)
- [Agenten-Spezifikation](Agenten_Spezifikation.md)
- [Agenten-Orchestrierung](../Patterns/Agenten_Orchestrierung.md)
- [GitHub Agents](GitHub_Agents.md)
