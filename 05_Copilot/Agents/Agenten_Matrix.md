# Copilot- und Agenten-Matrix

## Zweck

Diese Matrix ordnet Copilot-Produkte, spezialisierte Agents, Agentenplattformen, Harnesses und agentische Erweiterungen getrennt voneinander ein.

Die Trennung ist wichtig: Ein **Produkt** ist nicht automatisch ein Agent, ein **Agent** ist nicht automatisch eine **Laufzeit**, und eine **Erweiterung** wie Skills ist keine eigene Agentenklasse.

Produktnamen, Funktionsumfang, Lizenzierung und Verfügbarkeit koennen sich aendern. Preview-/Frontier-Funktionen sind entsprechend zu kennzeichnen und nicht als produktiver Standard zu behandeln.

## 1. Produkt- und Agentenmatrix

| Variante / Funktion | Kategorie | Fachgebiet | Recherche | Analyse | Eigenstaendige Aufgaben | Wissen / Daten | Aktionen / Schreiben | Integrationen | Typische Zielgruppe |
|---|---|---|---:|---:|---:|---|---:|---|---|
| **Microsoft 365 Copilot** | Copilot-Erfahrung | Produktivitaet | ++ | + | o | Microsoft Graph / Arbeitsinhalte | + | M365-Apps | Information Worker |
| **Researcher** | spezialisierter Agent | Recherche | ++ | ++ | + | Web + Arbeitsinhalte | o | Microsoft 365 | Fachanwender |
| **Analyst** | spezialisierter Agent | Datenanalyse | + | ++ | + | Daten / Dateien | o | Microsoft 365 / Datenquellen | Fachanwender / Analysten |
| **Agent Builder** | Agent-Erstellung | Fachwissen | + | + | o | Organisationswissen, z. B. SharePoint | o | Microsoft 365 | Information Worker / Teams |
| **Copilot Studio** | Agentenplattform | Prozesse / Automatisierung | + | ++ | ++ | Unternehmensdaten / Wissensquellen | ++ | Connectoren, APIs, MCP, Workflows, Agents | Maker / Entwickler |
| **Finance Agent** | Fachagent | Finanzen | ++ | ++ | + | Finanz- / ERP-Daten | + | ERP, u. a. AR/AP | Finance |
| **Security Copilot** | Security-Plattform | IT-Sicherheit | ++ | ++ | ++ | Security-Signale / Microsoft Security / Partnerdaten | ++ | Defender, Entra, Intune, Purview, Sentinel | Security / IT |
| **Security Copilot Agents** | spezialisierte Security-Agents | Security | + | ++ | ++ | Security-Daten | ++ | Security-Portfolios / Partner | Security Operations |
| **GitHub Copilot Chat** | Copilot-Erfahrung | Softwareentwicklung | + | + | o | Repository / Code / Kontext | + | GitHub / IDEs | Entwickler |
| **GitHub Copilot Agent Mode** | Agent-Modus | Softwareentwicklung | + | ++ | ++ | lokaler Workspace / Repository | ++ | IDE / Tools / MCP | Entwickler |
| **GitHub Copilot Cloud Agent** | autonomer Entwicklungsagent | Softwareentwicklung | + | ++ | ++ | Repository / Issues / PR-Kontext | ++ | GitHub / Actions / MCP / Skills | Entwickler / Teams |
| **GitHub Copilot Code Review** | agentische Review-Funktion | Codequalitaet / Security | o | ++ | + | PR-Diff / Repository-Kontext | + | GitHub / Skills / MCP | Entwickler / Reviewer |
| **GitHub Copilot CLI** | agentische CLI-Erfahrung | Entwicklung / Betrieb | + | + | ++ | lokaler Workspace | ++ | Shell / Git / MCP | Entwickler / Admins |
| **Agent Skills** | Erweiterung | Spezialaufgaben | abhaengig | abhaengig | abhaengig | Anweisungen / Skripte / Ressourcen | abhaengig | Cloud Agent, Code Review, CLI, IDE Agent Mode | Entwickler / Teams |
| **Eigener M365-Agent** | eigener Agent | DWD-Fachgebiet | abhaengig | abhaengig | abhaengig | definierte DWD-Wissensquellen | abhaengig | M365 / Connectoren / APIs | definierte Benutzergruppen |
| **Eigener Copilot-Studio-Agent** | eigener Agent | DWD-Prozess | + | ++ | ++ | SharePoint / Dataverse / APIs | ++ | Connectoren / REST / MCP / Workflows | definierte Rollen / Organisation |

Legende: **++** = Kernfunktion / besonders stark, **+** = gut unterstuetzt, **o** = eingeschraenkt oder szenarioabhaengig, **-** = nicht typischer Einsatzzweck.

## 2. Copilot Studio – Harness-Matrix

| Harness | Kategorie | Bestes Einsatzgebiet | Orchestrierung | Autonomie | Dateien | Skills / Memory | Tools / MCP | Bereitstellung |
|---|---|---|---|---|---|---|---|---|
| **GitHub Copilot Harness** | Laufzeit | komplexe, mehrstufige Geschaeftsprozesse | ++ zielorientiert | ++ | ++ Word / Excel / PowerPoint / PDF | ++ | ++ | intern und extern |
| **Standard Harness** | Laufzeit | regelbasierte Agents und strukturierte Workflows | + definiert | o | o | o | + | intern und extern |
| **Copilot Chat Harness** | Laufzeit | Erweiterung von M365 Copilot Chat mit Organisationswissen | + | o | o | o | + | M365 / Teams |

Das Harness ist die Laufzeit zwischen Agent-Definition und Modell. Es bestimmt unter anderem, wie Ziele zerlegt werden, wie Werkzeuge aufgerufen werden, wie mit Fehlern umgegangen wird und welche Funktionen wie Dateien, Skills oder Memory zur Verfuegung stehen.

**Wichtig:** Das GitHub Copilot Harness in Copilot Studio ist nicht dasselbe wie die GitHub Copilot Produktfamilie. Die Namensaehnlichkeit darf nicht zu einer fachlichen Gleichsetzung fuehren.

## 3. Feature-Matrix

| Feature | M365 Copilot | Researcher | Analyst | Agent Builder | Copilot Studio | Finance | Security | GitHub Cloud Agent | Code Review |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Natuerliche Sprache | ++ | ++ | ++ | ++ | ++ | ++ | ++ | ++ | ++ |
| Web-Recherche | + | ++ | + | o | o | ++ | + | o | - |
| M365-Arbeitskontext | ++ | ++ | ++ | ++ | + | + | o | - | - |
| Tiefenanalyse | + | ++ | ++ | + | ++ | ++ | ++ | ++ | + |
| Mehrstufiges Reasoning | + | ++ | ++ | + | ++ | ++ | ++ | ++ | ++ |
| Eigene Wissensquellen | o | + | + | ++ | ++ | ++ | ++ | ++ | ++ |
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
| Hintergrundaufgaben | o | + | + | - | ++ | ++ | ++ | ++ | + |
| Multi-Channel | + | + | + | + | ++ | + | ++ | ++ | ++ |
| Unternehmensweite Governance | ++ | ++ | ++ | + | ++ | ++ | ++ | ++ | ++ |

## 4. Begriffsabgrenzung

### Copilot-Erfahrung

Eine Benutzeroberflaeche bzw. Produktfamilie, z. B. Microsoft 365 Copilot oder GitHub Copilot.

### Agent

Ein spezialisierter KI-Assistent mit definiertem Zweck, Wissen und gegebenenfalls Tools und Aktionen.

### Agentenplattform

Eine Entwicklungs- und Bereitstellungsumgebung fuer Agents, insbesondere Copilot Studio.

### Harness

Die Laufzeit eines Agents. In Copilot Studio gibt es aktuell Standard Harness, Copilot Chat Harness und GitHub Copilot Harness.

### Skill

Eine wiederverwendbare Sammlung aus Anweisungen, Skripten und Ressourcen fuer eine Spezialaufgabe. Skills sind **keine eigene Agentenklasse**.

### MCP

Ein standardisierter Weg, ueber den Agents auf externe Werkzeuge und Kontext zugreifen koennen. MCP ist eine Integrationsmoeglichkeit und kein eigener Agent.

## 5. DWD-Entscheidungslogik

| Anforderung | Primaere Bewertung |
|---|---|
| Allgemeine Unterstuetzung in M365 | Microsoft 365 Copilot |
| Tiefe Recherche | Researcher |
| Daten untersuchen | Analyst |
| Kleiner fokussierter Wissensagent | Agent Builder / M365-Agent |
| M365 Copilot um DWD-Wissen erweitern | Copilot Chat Harness / M365-Agent |
| Regelbasierter Geschaeftsprozess | Standard Harness / Copilot Studio |
| Komplexer mehrstufiger Geschaeftsprozess | GitHub Copilot Harness / Copilot Studio |
| Finanz- und ERP-Aufgaben | Finance Agent |
| Security- und Incident-Themen | Security Copilot / Security Agents |
| Softwareentwicklung | GitHub Copilot |
| Selbststaendige Bearbeitung eines Issues | GitHub Copilot Cloud Agent |
| Pull Request pruefen | GitHub Copilot Code Review |
| Wiederholbare Entwicklungs-Spezialaufgabe | Agent Skills |
| DWD-spezifischer Prozess mit Aktionen | eigener Copilot-Studio-Agent |

## 6. Governance-Hinweis

Technische Faehigkeiten ersetzen keine Freigabe. Fuer produktive Agents muessen mindestens Zweck, Besitzer, Zielgruppe, Identitaet, Berechtigungen, Wissensquellen, Tools, Connectoren, MCP, Aktionen, Testnachweise, Protokollierung, Kosten, Freigabe, Lebenszyklus und Abschaltung dokumentiert werden.

## Primaerquellen

- Microsoft Learn: [Agents fuer Microsoft 365 Copilot](https://learn.microsoft.com/de-de/microsoft-365/copilot/extensibility/agents-overview)
- Microsoft Learn: [Harness auswaehlen](https://learn.microsoft.com/de-de/microsoft-copilot-studio/harnesses-overview)
- Microsoft Learn: [Copilot Studio Agents](https://learn.microsoft.com/de-de/microsoft-copilot-studio/agents-overview)
- Microsoft Learn: [Copilot Chat Harness](https://learn.microsoft.com/de-de/microsoft-copilot-studio/microsoft-365-copilot-extend-with-agents)
- Microsoft Learn: [Finance Agent](https://learn.microsoft.com/de-de/copilot/finance/agent-in-copilot-chat/agent-chat-overview)
- Microsoft Learn: [Security Copilot Agents](https://learn.microsoft.com/de-de/copilot/security/agents-overview)
- GitHub Docs: [Copilot Cloud Agent](https://docs.github.com/de/copilot/concepts/agents/cloud-agent/about-cloud-agent)
- GitHub Docs: [Copilot Code Review](https://docs.github.com/en/copilot/concepts/agents/code-review)
- GitHub Docs: [Agent Skills](https://docs.github.com/de/copilot/concepts/agents/about-agent-skills)
