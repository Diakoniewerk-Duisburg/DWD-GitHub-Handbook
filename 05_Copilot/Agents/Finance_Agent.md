# Finance Agent

## Einordnung

Der Finance Agent ist ein spezialisierter Fachagent fuer Finanzaufgaben im Microsoft-Copilot-Umfeld. Er ist nicht mit dem allgemeinen Microsoft 365 Copilot und auch nicht mit einem selbst gebauten DWD-Agenten gleichzusetzen.

Microsoft beschreibt den aktuellen Finance Agent als zentrale Copilot-Erfahrung fuer finanzielle Erkenntnisse, Business Intelligence und die Interaktion mit ERP-Daten.

## Kernfunktionen

### Finance Home

Zentraler Einstiegspunkt fuer finanzbezogene Aufgaben innerhalb von Copilot Chat.

### Business Intelligence

Der Agent kann Informationen und Erkenntnisse zu oeffentlichen und privaten Unternehmen recherchieren.

### Business Brief

Der Agent kann strukturierte Unternehmensprofile bzw. Entscheidungsunterlagen erstellen und dabei oeffentliche Informationen und interne ERP-Daten zusammenfuehren.

Moegliche Anwendungsobjekte sind beispielsweise:

- Lieferanten
- Kunden
- Wettbewerber
- Partner

### ERP-Daten

Die aktuell dokumentierte ERP-Integration umfasst insbesondere:

- Accounts Payable (Kreditoren)
- Accounts Receivable (Debitoren)
- Abfragen zu Rechnungsstatus und Zahlungshistorie
- bestimmte Aktionen und Aktualisierungen im ERP

Die ERP-Interaktion verwendet Microsofts MCP-basierte Integration.

## Was unterscheidet Finance Agent von Analyst?

| Merkmal | Analyst | Finance Agent |
|---|---|---|
| Hauptzweck | Datenanalyse | Finanzfachliche Arbeit |
| Daten | Tabellen, Dateien, Datenquellen | Finanz- und ERP-Daten plus Unternehmensinformationen |
| Fachmodell | allgemein | Finanzdomäne |
| ERP-Aktionen | nicht der Kern | Bestandteil des Konzepts |
| Unternehmensrecherche | moeglich | zentraler Bestandteil |
| DWD-Einordnung | Analysewerkzeug | Fachagent |

## DWD-Relevanz

Der Finance Agent ist fuer den DWD insbesondere dann interessant, wenn Finanzinformationen nicht nur ausgewertet, sondern mit ERP-Prozessen verbunden werden sollen.

Vor einer Nutzung sind mindestens zu pruefen:

1. Welche ERP-Systeme sind im Einsatz?
2. Welche Daten sollen eingebunden werden?
3. Welche Benutzer und Rollen duerfen diese Daten sehen?
4. Welche Aktionen duerfen ausgefuehrt werden?
5. Welche Aktionen benoetigen zusaetzliche Genehmigung?
6. Welche Daten duerfen nicht ueber den Agenten verarbeitet werden?
7. Welche Audit- und Compliance-Anforderungen bestehen?

## Governance-Grundsatz

Ein Fachagent mit Schreib- oder Aktionsrechten ist deutlich hoeher zu bewerten als ein reiner Informationsagent. Finanzielle Aktionen muessen deshalb fachlich, technisch und berechtigungsseitig kontrolliert werden.

## Status

Der Finance Agent wird von Microsoft derzeit als Frontier-/Preview-Funktion dokumentiert. Deshalb muss vor einer produktiven Nutzung die konkrete Verfuegbarkeit und der aktuelle Funktionsumfang im Tenant geprueft werden.

## Primaerquellen

- Microsoft Learn: Finance Agent overview – https://learn.microsoft.com/en-us/copilot/finance/agent-in-copilot-chat/agent-chat-overview
- Microsoft Learn: Finance Agent – Neuerungen – https://learn.microsoft.com/en-us/copilot/finance/whats-new/whats-new-may-2026
