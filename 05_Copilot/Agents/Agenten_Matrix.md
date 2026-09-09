# Copilot- und Agenten-Matrix

## Zweck

Diese Matrix ordnet die wichtigsten Copilot-Varianten und agentischen Funktionen nach Einsatzgebiet, Fähigkeiten, Wissensquellen, Aktionen, Integrationen und Governance ein.

Die Matrix dient als Orientierungs- und Entscheidungsgrundlage. Produktnamen, Funktionsumfang, Lizenzierung und Verfügbarkeit können sich ändern. Preview-/Frontier-Funktionen sind entsprechend zu kennzeichnen und nicht als produktiver Standard zu behandeln.

## Gesamtmatrix

| Variante / Funktion | Fachgebiet | Antworten / Recherche | Analyse | Eigenstaendige Aufgaben | Wissen / Daten | Aktionen / Schreiben | Integrationen | Typische Zielgruppe | Geeigneter Einsatz |
|---|---|---:|---:|---:|---|---:|---|---|---|
| **Microsoft 365 Copilot** | Produktivitaet | Ja | Ja | begrenzt | Microsoft Graph, Arbeitsinhalte | teilweise | M365-Apps | Information Worker | Taegliche Wissens- und Produktivitaetsarbeit |
| **Researcher Agent** | Recherche | **sehr hoch** | **hoch** | mehrstufige Recherche | Web + Arbeitsinhalte | gering | Microsoft 365 | Fachanwender | Berichte, Markt-/Unternehmensrecherche, Entscheidungsgrundlagen |
| **Analyst Agent** | Datenanalyse | Ja | **sehr hoch** | mehrstufig | Unternehmensdaten / Dateien | gering bis mittel | Microsoft 365 / Datenquellen | Fachanwender / Analysten | Datenanalyse, Auswertungen, Ursachenanalyse |
| **Agent Builder** | Organisation / Fachwissen | Ja | mittel | begrenzt | Organisationswissen, z. B. SharePoint | begrenzt | Microsoft 365 | Information Worker / kleine Teams | Schnelle, fokussierte Agents |
| **Copilot Studio** | Prozess / Automatisierung | Ja | hoch | **hoch** | Wissensquellen + Unternehmensdaten | **hoch** | Connectoren, APIs, MCP, Workflows, andere Agents | Maker / Entwickler | Unternehmensweite Agents und komplexe Prozesse |
| **Finance Agent** | Finanzen | **hoch** | **hoch** | mittel bis hoch | Finanz-/ERP-Daten + oeffentliche Daten | **Ja**, je nach Szenario | ERP, u. a. AR/AP | Finance | Finanzrecherche, Business Briefs, ERP-Fragen und Aktionen |
| **Security Copilot** | IT-Sicherheit | **hoch** | **sehr hoch** | **hoch** | Security-Signale, Microsoft Security, Partnerdaten | **Ja** | Defender, Entra, Intune, Purview, Sentinel, Partner | Security / IT | Incident Response, Threat Hunting, Security Operations |
| **Security Copilot Agents** | Spezialisierte Security-Aufgaben | hoch | **sehr hoch** | **sehr hoch** | Security-Daten | **hoch** | Security-Portfolios + Partner | Security Operations | Wiederholbare Security-Workflows automatisieren |
| **GitHub Copilot Chat** | Softwareentwicklung | Ja | mittel bis hoch | begrenzt | Repository / Code / Kontext | Ja | GitHub, IDEs | Entwickler | Fragen, Erklaerungen, Codeunterstuetzung |
| **GitHub Copilot Agent Mode** | Softwareentwicklung | Ja | **hoch** | **hoch** | Lokales Projekt / Repository | **hoch** | IDE, Tools, MCP | Entwickler | Mehrstufige Entwicklung im lokalen Workspace |
| **GitHub Copilot Cloud Agent** | Softwareentwicklung | Ja | **sehr hoch** | **sehr hoch** | Repository, Issues, PR-Kontext | **sehr hoch** | GitHub, Actions, MCP, Skills | Entwickler / Teams | Recherche, Planung, Implementierung, Tests, PR-Erstellung |
| **GitHub Copilot Code Review** | Codequalitaet / Security | Ja | **hoch** | mittel | PR-Diff + Repository-Kontext | Vorschlaege / Review | GitHub, Skills, MCP | Entwickler / Reviewer | PR-Review, Qualitaet, Security-Hinweise |
| **GitHub Copilot CLI** | Softwareentwicklung / Betrieb | Ja | hoch | **hoch** | lokaler Workspace | **hoch** | Shell, Git, MCP | Entwickler / Admins | Kommandozeilenbasierte Entwicklungs- und Automatisierungsaufgaben |
| **GitHub Copilot Skills** | Spezialaufgaben | abhaengig | abhaengig | abhaengig | Anweisungen, Skripte, Ressourcen | abhaengig | Cloud Agent, Code Review, CLI, IDE | Entwickler / Teams | Wiederholbare Spezialaufgaben standardisieren |
| **Eigener Microsoft-365-Agent** | DWD-Fachgebiet | abhaengig | abhaengig | abhaengig | definierte DWD-Wissensquellen | abhaengig | M365 / Connectoren / APIs | definierte Benutzergruppen | DWD-spezifische Fach- und Wissensaufgaben |
| **Eigener Copilot-Studio-Agent** | DWD-Prozess | hoch | hoch | **hoch** | SharePoint, Dataverse, APIs usw. | **hoch** | Connectoren, REST, MCP, Workflows | definierte Rollen / Organisation | Prozessautomatisierung und operative Arbeit |

## Feature-Matrix

Legende:

- **++** = Kernfunktion / besonders stark
- **+** = gut unterstuetzt
- **o** = eingeschraenkt oder abhaengig vom Szenario
- **-** = nicht der typische Einsatzzweck

| Feature | M365 Copilot | Researcher | Analyst | Agent Builder | Copilot Studio | Finance | Security Copilot | GitHub Cloud Agent | GitHub Code Review |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Natuerliche Sprache | ++ | ++ | ++ | ++ | ++ | ++ | ++ | ++ | ++ |
| Web-Recherche | + | ++ | + | o | o | ++ | + | o | - |
| Arbeitsinhalte / M365-Kontext | ++ | ++ | ++ | ++ | + | + | o | - | - |
| Strukturierte Tiefenanalyse | + | ++ | ++ | + | ++ | ++ | ++ | ++ | + |
| Mehrstufiges Reasoning | + | ++ | ++ | + | ++ | ++ | ++ | ++ | ++ |
| Eigene Wissensquellen | o | o | o | ++ | ++ | ++ | ++ | ++ | ++ |
| SharePoint | ++ | ++ | ++ | ++ | ++ | o | o | - | - |
| Connectoren / APIs | + | o | + | + | ++ | ++ | ++ | ++ | ++ |
| Workflows / Aktionen | o | o | o | o | ++ | ++ | ++ | ++ | + |
| MCP | + | o | o | o | ++ | ++ | ++ | ++ | ++ |
| Code erzeugen | + | - | - | o | + | - | - | ++ | + |
| Code aendern | o | - | - | o | + | - | - | ++ | + |
| Pull Requests | - | - | - | - | o | - | - | ++ | ++ |
| Code Review | - | - | - | - | o | - | - | + | ++ |
| Security-Analyse | o | o | o | o | + | o | ++ | ++ | ++ |
| ERP-Integration | - | - | - | - | ++ | ++ | - | - | - |
| Entra / Identity | + | - | - | o | + | - | ++ | + | + |
| Defender / Sentinel | - | - | - | o | + | - | ++ | + | + |
| Automatisierte Hintergrundaufgaben | o | + | + | - | ++ | ++ | ++ | ++ | + |
| Multi-Channel-Bereitstellung | + | + | + | + | ++ | + | ++ | ++ | ++ |
| Unternehmensweite Governance | ++ | ++ | ++ | + | ++ | ++ | ++ | ++ | ++ |

## Einordnung der wichtigsten Varianten

### 1. Microsoft 365 Copilot

Der allgemeine Einstieg fuer die Arbeit mit Microsoft 365. Er verbindet Copilot-Funktionen mit dem Microsoft-365-Arbeitskontext und Microsoft Graph.

### 2. Researcher und Analyst

Diese Agents sind **Aufgaben-Spezialisten**:

- Researcher = recherchieren, Quellen auswerten und einen strukturierten Bericht erzeugen.
- Analyst = Daten untersuchen, Muster erkennen und Analysen erstellen.

Sie sind deshalb nicht mit einer Entwicklungsplattform wie Copilot Studio gleichzusetzen.

### 3. Agent Builder

Agent Builder ist der schnelle Weg zu einem fokussierten Agenten innerhalb der Microsoft-365-Copilot-Erfahrung. Er eignet sich insbesondere fuer kleinere, klar abgegrenzte Wissensszenarien.

### 4. Copilot Studio

Copilot Studio ist die **Agenten- und Automatisierungsplattform** fuer komplexere Szenarien. Hier kommen Wissensquellen, Connectoren, REST-APIs, MCP, Workflows und andere Agents zusammen.

### 5. Finance Agent

Der Finance Agent ist ein **Fachagent**. Er kombiniert Finanzrecherche, Business Briefs und die Interaktion mit ERP-Daten. Die aktuelle Dokumentation nennt insbesondere Accounts Receivable und Accounts Payable sowie damit verbundene Abfragen und Aktionen.

### 6. Security Copilot

Security Copilot ist eine eigene Security-Plattform und nicht lediglich ein allgemeiner Copilot mit einem anderen Prompt. Die Agents arbeiten im Microsoft-Sicherheitsökosystem, unter anderem mit Defender, Entra, Intune, Purview und Sentinel.

### 7. GitHub Copilot

GitHub Copilot muss als **agentische Entwicklungsplattform mit mehreren Erfahrungen** verstanden werden:

- Chat
- Agent Mode
- Cloud Agent
- Code Review
- CLI
- Skills
- MCP
- Custom Agents

Der Cloud Agent kann beispielsweise ein Repository untersuchen, einen Plan erstellen, Code auf einem Branch aendern und einen Pull Request vorbereiten. Code Review kann Repository-Kontext, Skills und MCP verwenden.

## DWD-Entscheidungslogik

| Frage | Bevorzugte Variante |
|---|---|
| Ich brauche allgemeine Unterstuetzung in M365 | Microsoft 365 Copilot |
| Ich brauche eine tiefe Recherche | Researcher |
| Ich muss Daten untersuchen | Analyst |
| Ich brauche einen kleinen Wissensagenten | Agent Builder |
| Ich muss einen echten Geschaeftsprozess automatisieren | Copilot Studio |
| Ich arbeite mit Finanz-/ERP-Daten | Finance Agent |
| Ich bearbeite Security- und Incident-Themen | Security Copilot / Security Agents |
| Ich entwickle Software | GitHub Copilot |
| Copilot soll selbststaendig an einem Issue arbeiten | GitHub Copilot Cloud Agent |
| Ein Pull Request soll automatisiert geprueft werden | GitHub Copilot Code Review |
| Eine wiederholbare Spezialaufgabe soll standardisiert werden | Agent Skills / eigener Agent |
| Es gibt einen spezifischen DWD-Prozess | Eigener DWD-Agent, bevorzugt ueber Copilot Studio bei komplexen Aktionen |

## Governance-Hinweis

Die Matrix bewertet technische Faehigkeiten, ersetzt aber keine Sicherheits- oder Freigabepruefung. Insbesondere bei Agents mit Schreib-, Aktions-, Connector-, MCP- oder Workflow-Funktionen muessen Identitaet, Berechtigungen, Datenzugriff, Protokollierung, Freigabe und Lebenszyklus separat bewertet werden.

## Primaerquellen

- Microsoft Learn: [Agents fuer Microsoft 365 Copilot](https://learn.microsoft.com/de-de/microsoft-365/copilot/extensibility/agents-overview)
- Microsoft Learn: [Auswahl zwischen Agent Builder und Copilot Studio](https://learn.microsoft.com/de-de/microsoft-365/copilot/extensibility/copilot-studio-experience)
- Microsoft Learn: [Researcher Agent](https://learn.microsoft.com/de-de/microsoft-365/copilot/researcher-agent)
- Microsoft Learn: [Finance Agent](https://learn.microsoft.com/de-de/copilot/finance/agent-in-copilot-chat/agent-chat-overview)
- Microsoft Learn: [Microsoft Security Copilot](https://learn.microsoft.com/de-de/copilot/security/microsoft-security-copilot)
- Microsoft Learn: [Security Copilot Agents](https://learn.microsoft.com/de-de/copilot/security/agents-overview)
- Microsoft Learn: [Copilot Studio Agents](https://learn.microsoft.com/de-de/microsoft-copilot-studio/agents-overview)
- GitHub Docs: [Copilot Cloud Agent](https://docs.github.com/de/copilot/concepts/agents/cloud-agent/about-cloud-agent)
- GitHub Docs: [Copilot Code Review](https://docs.github.com/en/copilot/concepts/agents/code-review)
- GitHub Docs: [Agent Skills](https://docs.github.com/de/copilot/concepts/agents/about-agent-skills)
