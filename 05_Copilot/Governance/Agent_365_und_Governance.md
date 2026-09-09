# Agent 365 und Governance

## Einordnung

Mit der zunehmenden Zahl von Agents wird neben der Erstellung auch deren zentrale Verwaltung wichtig. Microsoft baut dafuer Agent 365 als Governance- und Verwaltungsrahmen aus.

Die Knowledgebase trennt deshalb:

- **Agent-Funktion** – was kann der Agent?
- **Agent-Laufzeit** – wie wird der Agent ausgefuehrt?
- **Agent-Verwaltung** – wie wird der Agent registriert, abgesichert, beobachtet und betrieben?

## Governance-Felder

| Feld | Leitfrage |
|---|---|
| Identitaet | Unter welcher Identitaet arbeitet der Agent? |
| Berechtigungen | Welche Daten und Aktionen darf er erreichen? |
| Daten | Welche Wissensquellen und Unternehmensdaten werden verwendet? |
| Tools | Welche Connectoren, APIs und MCP-Server darf er nutzen? |
| Lebenszyklus | Wer erstellt, testet, genehmigt, veroeffentlicht und deaktiviert ihn? |
| Registrierung | Wo wird der Agent inventarisiert? |
| Beobachtung | Wie werden Nutzung, Fehler und Risiken erkannt? |
| Compliance | Welche Datenschutz-, Sicherheits- und Aufbewahrungsregeln gelten? |
| Kosten | Welche Lizenz- oder Verbrauchskosten entstehen? |

## DWD-Grundsatz

Ein produktiver Agent muss wie eine technische Anwendung behandelt werden. Eine reine Funktionsbeschreibung reicht nicht aus.

Vor der Freigabe sind mindestens Zweck, Besitzer, Zielgruppe, Datenquellen, Identitaet, Berechtigungen, Tools, Aktionen, Testnachweise, Freigabe, Monitoring und Abschaltverfahren zu dokumentieren.

## Abgrenzung

Agent 365 ist keine neue fachliche Agentenklasse wie Finance oder Security. Es ist als Verwaltungs- und Governance-Ebene zu betrachten.

Damit bleibt die Architektur:

**Copilot-Erfahrung -> Agent -> Harness/Laufzeit -> Wissen/Tools -> Aktionen -> Governance/Verwaltung**

## Primaerquelle

Microsoft Learn: [Microsoft Copilot Studio – Agents](https://learn.microsoft.com/de-de/microsoft-copilot-studio/agents-overview)
