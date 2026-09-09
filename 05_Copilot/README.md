# Copilot

Diese Wissensdomäne beschreibt Microsoft 365 Copilot, Agents, Copilot Studio, Wissensquellen, Prompts und Governance. GitHub Copilot und Security Copilot werden als eigene agentische Produktfamilien eingeordnet und mit den jeweils fachlich zustaendigen Wissensdomänen verknuepft.

## Fachlicher Arbeitsstand

Der bisherige Chat-Arbeitsstand wurde mit dem Repository-Inhalt abgeglichen und konsolidiert. Die vollstaendige Konsolidierungsdokumentation steht in:

- [Chat-/Repository-Konsolidierung](CHAT_REPOSITORY_KONSOLIDIERUNG.md) – detaillierter Abgleich von Erkenntnissen und Aufzaehlungen
- [Copilot-Konsolidierung](COPILOT_KONSOLIDIERUNG.md) – bisheriger Audit- und Konsolidierungsnachweis
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
- [Agenten-Spezifikation](Agents/Agenten_Spezifikation.md)
- [Agenten-Lifecycle](Agents/Agenten_Lifecycle.md)
- [Autonomiestufen](Agents/Autonomiestufen.md)
- [Connectoren und Aktionen](Agents/Connectoren_und_Aktionen.md)
- [MCP und Tools](Agents/MCP_und_Tools.md)
- [Umgebungen und ALM](Agents/Umgebungen_und_ALM.md)
- [Testing und Debugging](Agents/Testing_und_Debugging.md)
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
- [Risiko- und Schutzklassen](Governance/Risiko_und_Schutzklassen.md)
- [Freigabeprozess](Governance/Freigabeprozess.md)
- [Berechtigungsmodell](Governance/Berechtigungsmodell.md)
- [Datenschutz und Privatsphaere](Governance/Datenschutz_und_Privatsphaere.md)
- [Audit und Monitoring](Governance/Audit_und_Monitoring.md)
- [Lizenzierung und Kosten](Governance/Lizenzierung_und_Kosten.md)

### DWD-Anwendungsfaelle

Konkrete Kandidaten fuer spaetere Prototypen und produktive Fachloesungen.

- [Uebersicht](DWD_Anwendungsfaelle/README.md)
- [Wissensagent](DWD_Anwendungsfaelle/01_Wissensagent.md)
- [Beschaffungsagent](DWD_Anwendungsfaelle/02_Beschaffungsagent.md)
- [Genehmigungsagent](DWD_Anwendungsfaelle/03_Genehmigungsagent.md)
- [Ticketagent](DWD_Anwendungsfaelle/04_Ticketagent.md)
- [Provisioningagent](DWD_Anwendungsfaelle/05_Provisioningagent.md)
- [Datenmigrationsagent](DWD_Anwendungsfaelle/06_Datenmigrationsagent.md)
- [Adressbuchagent](DWD_Anwendungsfaelle/07_Adressbuchagent.md)

### Patterns

Wiederverwendbare Muster fuer kontrollierte Agentenarchitekturen.

- [Patterns](Patterns/README.md)
- [Human-in-the-Loop](Patterns/Human_in_the_Loop.md)
- [Agenten-Orchestrierung](Patterns/Agenten_Orchestrierung.md)

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

**Konsolidierter fachlicher Arbeitsstand.** Chat-Erkenntnisse und Repository-Wissen sind als dauerhafte Grundlage zusammengefuehrt. Die naechste Ausbaustufe ist nicht mehr die Sicherung des bisherigen Chatwissens, sondern die fachliche und technische Vertiefung konkreter DWD-Loesungen.
