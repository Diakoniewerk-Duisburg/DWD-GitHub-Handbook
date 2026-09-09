# Audit und Monitoring fuer Agents

## Ziel

Produktive Agents muessen hinsichtlich Nutzung, Fehlern, Aktionen und relevanten Aenderungen beobachtbar sein.

## Mindestumfang

- Betriebsstatus
- relevante Agentenaenderungen
- Tool- und Aktionsaufrufe, soweit technisch und datenschutzrechtlich zulaessig
- Fehler und Abbrueche
- sicherheitsrelevante Ereignisse
- Freigabe- und Berechtigungsänderungen
- Eskalationen an Menschen

## Monitoring

Monitoring soll nicht nur Verfuegbarkeit messen. Es soll auch fachliche und sicherheitsrelevante Auffaelligkeiten erkennbar machen, zum Beispiel:

- unerwartet viele Aktionsaufrufe
- wiederholte Fehlversuche
- ungewoehnliche Datenzugriffe
- unerwartete Zielsysteme
- haeufige Human-in-the-Loop-Ablehnungen
- Verhalten ausserhalb des vorgesehenen Anwendungsfalls

## Audit

Fuer relevante Aktionen muss nachvollziehbar sein, welcher Agent, welche Identitaet, welches Tool und welcher Prozessschritt beteiligt waren. Die konkrete Protokollierung richtet sich nach Plattform, Schutzklasse, Datenschutz und Aufbewahrungsregeln.

## Abschaltung

Bei schwerwiegendem Fehlverhalten muss eine kontrollierte Deaktivierung oder Sperrung moeglich sein.
