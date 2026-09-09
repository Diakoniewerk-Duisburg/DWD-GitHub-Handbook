# Connectoren und Aktionen

## Zweck

Connectoren und Aktionen bilden die Bruecke zwischen einem Agenten und den Systemen, in denen Wissen gelesen oder Veraenderungen ausgefuehrt werden.

## Grundmodell

**Agent -> Harness/Laufzeit -> Wissen oder Tool -> Connector/API/MCP -> Zielsystem**

Dabei sind Wissenszugriff und Aktionszugriff getrennt zu bewerten. Ein Agent, der Daten lesen darf, darf deshalb nicht automatisch Daten veraendern.

## Connectoren

Connectoren stellen standardisierte Verbindungen zu Diensten und Datenquellen bereit. Vor ihrer Verwendung sind mindestens zu pruefen:

- Zielsystem und Zweck
- verwendete Identitaet
- benoetigte Berechtigungen
- Datenumfang
- Schreibrechte
- Fehler- und Timeout-Verhalten
- Protokollierung und Nachvollziehbarkeit
- Datenschutz und Compliance

## Aktionen

Eine Aktion ist ein kontrollierter Vorgang, den ein Agent ausfuehren kann, zum Beispiel:

- Datensatz anlegen oder aktualisieren
- Workflow starten
- Anfrage erzeugen
- Nachricht oder Benachrichtigung ausloesen
- Provisionierung anstossen
- Status aendern

Jede schreibende Aktion muss fachlich eindeutig definiert, technisch begrenzt und testbar sein.

## MCP und APIs

MCP, REST APIs und andere Integrationsmechanismen sind technische Wege zur Bereitstellung von Tools. Sie ersetzen nicht die fachliche Freigabe des Agenten und fuehren nicht automatisch zu erweiterten Berechtigungen.

## DWD-Regeln

1. Least Privilege.
2. Lesen und Schreiben getrennt betrachten.
3. Keine implizite Berechtigungserweiterung durch Agenten.
4. Jede Aktion braucht einen nachvollziehbaren Zweck.
5. Kritische Aktionen benoetigen Human-in-the-Loop oder eine ausdruecklich freigegebene Autonomiestufe.
6. Fehler muessen sicher behandelt werden; Teilfehler duerfen keinen unkontrollierten Folgeprozess ausloesen.
7. Aktionen sind zu protokollieren, soweit dies fuer Betrieb, Audit und Nachvollziehbarkeit erforderlich ist.

## Verwandte Standards

- [Agenten-Spezifikation](Agenten_Spezifikation.md)
- [Autonomiestufen](Autonomiestufen.md)
- [Human-in-the-Loop](../Patterns/Human_in_the_Loop.md)
- [Agenten-Orchestrierung](../Patterns/Agenten_Orchestrierung.md)
- [Governance](../Governance/Grundlagen.md)
