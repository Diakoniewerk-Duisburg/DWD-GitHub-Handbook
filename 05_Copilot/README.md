# Copilot

Diese Wissensdomäne beschreibt Microsoft 365 Copilot, Agents, Copilot Studio, Wissensquellen, Prompts und Governance. GitHub Copilot und Security Copilot werden als eigene agentische Produktfamilien eingeordnet und mit den jeweils fachlich zustaendigen Wissensdomänen verknuepft.

## Fachlicher Arbeitsstand

Der bisherige Arbeitsstand ist konsolidiert. Wesentliche Erkenntnisse aus der bisherigen Bearbeitung sollen nicht dauerhaft nur im Chat existieren.

- [Copilot-Konsolidierung](COPILOT_KONSOLIDIERUNG.md) – Audit- und Konsolidierungsnachweis
- [Agenten-Matrix](Agents/Agenten_Matrix.md) – zentrale Vergleichs- und Entscheidungsreferenz

## Struktur

### Microsoft 365 Copilot

Grundlagen zur Nutzung von Microsoft 365 Copilot als Arbeitswerkzeug und zur Abgrenzung von Agent Builder und Copilot Studio.

- [Grundlagen](Microsoft_365_Copilot/Grundlagen.md)
- [Varianten und Funktionen](Microsoft_365_Copilot/Varianten_und_Funktionen.md)

### Agents

Grundlagen zu Zweck, Aufbau, Wissensquellen, Tools, Berechtigungen und Auswahl des geeigneten Erstellungswegs.

- [Grundlagen](Agents/Grundlagen.md)
- [Uebersicht und Einordnung](Agents/Agenten_Uebersicht.md)
- [Agenten-Matrix](Agents/Agenten_Matrix.md)
- [Microsoft Agents](Agents/Microsoft_Agents.md)
- [Finance Agent](Agents/Finance_Agent.md)
- [Security Agents](Agents/Security_Agents.md)
- [GitHub Agents](Agents/GitHub_Agents.md)

### Copilot Studio

Grundlagen fuer anspruchsvollere Agents, Connectoren, Tools, Umgebungen und ALM.

- [Grundlagen](Copilot_Studio/Grundlagen.md)
- [Harnesses und Agententypen](Copilot_Studio/Harnesses_und_Agententypen.md)

### Wissensquellen

Regeln fuer Auswahl, Berechtigung, Qualitaet und Dokumentation von Wissensquellen.

- [Grundlagen](Wissensquellen/Grundlagen.md)

### Prompts

Grundlagen fuer klare, nachvollziehbare und testbare Prompts.

- [Grundlagen](Prompts/Grundlagen.md)

### Governance

Governance fuer Identitaet, Daten, Wissensquellen, Connectoren, Freigabe, Betrieb und Compliance.

- [Grundlagen](Governance/Grundlagen.md)
- [Agent 365 und Governance](Governance/Agent_365_und_Governance.md)

## DWD-Leitgedanke

Copilot wird in dieser Knowledgebase nicht isoliert als KI-Chat dokumentiert. Betrachtet wird die gesamte Kette aus:

**Benutzer -> Copilot -> Agent -> Harness/Laufzeit -> Wissen -> Tool/Connector/MCP -> Aktion -> Prozess -> Governance/Betrieb**

Damit werden spaetere Fachloesungen, insbesondere Agents fuer SharePoint-, Power-Platform- und Geschaeftsprozesse, auf einer gemeinsamen Grundlage dokumentiert.

## Entscheidungsprinzip

Ein eigener Agent wird nicht deshalb gebaut, weil Agententechnik verfuegbar ist. Zuerst wird geprueft, ob Microsoft 365 Copilot oder ein vorhandener spezialisierter Agent ausreicht. Erst danach werden Agent Builder, Copilot Studio oder eine andere agentische Plattform als Loesungsweg bewertet.

Entscheidend sind:

- fachliches Problem
- Zielgruppe
- benoetigtes Wissen
- benoetigte Aktionen
- Integrationen
- Identitaet und Berechtigungen
- Autonomiegrad
- Governance und Lifecycle

## Status

**Konsolidierter fachlicher Arbeitsstand.** Die naechste Ausbaustufe besteht aus konkreten DWD-Anwendungsfaellen, Agent-Steckbriefen, Testfaellen, Governance-Vorlagen und belastbaren Prozessintegrationen.
