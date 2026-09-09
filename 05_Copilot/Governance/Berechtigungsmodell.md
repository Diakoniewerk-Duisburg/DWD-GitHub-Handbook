# Berechtigungsmodell fuer Agents

## Grundsatz

Ein Agent erbt keine pauschale Berechtigung, nur weil ein Benutzer oder ein Dienst technisch Zugriff besitzt. Datenzugriff und Aktionsberechtigung sind getrennt zu bewerten.

## Ebenen

1. **Benutzerberechtigung** – darf die anfragende Person auf die Information zugreifen?
2. **Agentenberechtigung** – darf der Agent diese Datenquelle verwenden?
3. **Toolberechtigung** – darf das konkrete Tool auf das Zielsystem zugreifen?
4. **Aktionsberechtigung** – darf der Agent die konkrete Veraenderung ausfuehren?
5. **Freigabeberechtigung** – muss ein Mensch die Aktion bestaetigen?

## Least Privilege

Es gelten mindestens:

- nur erforderliche Datenquellen
- nur erforderliche Tools
- nur erforderliche API-Rechte
- keine pauschalen Administratorrechte
- getrennte Identitaeten fuer unterschiedliche Verantwortungsbereiche, wenn erforderlich
- regelmaessige Ueberpruefung der Berechtigungen

## Kritische Aktionen

Berechtigungsänderungen, Loeschungen, Provisionierung, finanzielle Vorgänge und andere wesentliche Prozessaktionen sind besonders zu schuetzen. Fuer solche Aktionen ist mindestens Schutzklasse R3 zu pruefen.

## Keine implizite Eskalation

Ein Agent darf keine Rechte aus einem Tool, Connector, MCP-Server oder Zielsystem ableiten, die nicht ausdruecklich freigegeben wurden.
