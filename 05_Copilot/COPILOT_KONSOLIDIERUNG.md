# Copilot-Konsolidierung

## Zweck

Dieses Dokument ist der fachliche Konsolidierungsnachweis fuer den bisherigen Arbeitsstand zu Copilot und Agents.

Ziel ist, dass wesentliche Erkenntnisse aus der bisherigen Bearbeitung nicht nur im Chat existieren, sondern als dauerhaftes Wissen in der Knowledgebase vorliegen.

Die Pruefung bezieht sich auf den Bereich `05_Copilot` und auf die im bisherigen Arbeitsstand behandelten Themen Microsoft 365 Copilot, Agents, Copilot Studio, Harnesses, Wissensquellen, Prompts, Governance, Agent 365, Security Copilot, Finance Agent und GitHub Copilot Agents.

## 1. Ergebnis der Konsolidierung

**Status: KONSOLIDIERT**

Der bisherige fachliche Arbeitsstand ist in `05_Copilot` als dauerhaftes Wissen abgebildet. Die vorhandenen Detaildokumente bleiben thematisch getrennt; dieses Dokument bildet den Audit- und Abschlussnachweis.

Die Knowledgebase behandelt Copilot nicht als einzelnen Chatbot, sondern als Zusammenspiel aus:

**Copilot-Erfahrung -> Agent -> Harness/Laufzeit -> Wissen -> Tools/Connectoren/MCP -> Aktionen/Prozesse -> Governance/Betrieb**

Diese Kette ist die zentrale fachliche Leitlinie fuer die weitere DWD-Architektur.

## 2. Konsolidierte Kernerkenntnisse

### 2.1 Copilot ist keine einheitliche technische Klasse

Im bisherigen Arbeitsstand wurde bewusst zwischen folgenden Ebenen unterschieden:

1. **Copilot-Erfahrung / Produkt** – z. B. Microsoft 365 Copilot, GitHub Copilot oder Security Copilot.
2. **Spezialisierter Agent** – z. B. Researcher, Analyst, Finance Agent oder Security Analyst Agent.
3. **Agentenplattform** – insbesondere Copilot Studio.
4. **Agent Builder** – einfacher Erstellungsweg fuer fokussierte Wissensagenten.
5. **Harness / Laufzeit** – bestimmt die Ausfuehrungs- und Orchestrierungslogik eines Agents.
6. **Erweiterungen** – Skills, MCP, Connectoren, REST-APIs, Workflows und Plugins.
7. **Eigener Agent** – organisations- oder prozessspezifische Loesung.
8. **Agent-Verwaltung / Governance** – insbesondere Identitaet, Berechtigungen, Registrierung, Telemetrie, Freigabe und Lifecycle.

Eine Gleichsetzung dieser Ebenen ist zu vermeiden.

### 2.2 Microsoft 365 Copilot

Microsoft 365 Copilot ist die allgemeine Copilot-Erfahrung fuer die Arbeit mit Microsoft-365-Inhalten und -Anwendungen.

Wesentliche Erkenntnisse:

- Der Arbeitskontext wird durch Microsoft 365 und Microsoft Graph bestimmt.
- Der Agent bzw. Copilot darf die vorhandenen Zugriffsgrenzen nicht als Abkuerzung fuer Berechtigungen umgehen.
- M365 Copilot, Agent Builder und Copilot Studio sind unterschiedliche Wege fuer unterschiedliche Komplexitaet.
- Ein einfacher Informationsbedarf erfordert nicht automatisch einen eigenen Agenten.
- Eigene Agenten werden erst relevant, wenn ein klar abgegrenztes Wissen, Verhalten oder eine Aktion benoetigt wird.

Dokumentiert in:

- `Microsoft_365_Copilot/Grundlagen.md`
- `Microsoft_365_Copilot/Varianten_und_Funktionen.md`

### 2.3 Researcher und Analyst

Der bisherige Arbeitsstand unterscheidet die spezialisierten M365-Agenten klar:

- **Researcher**: komplexe, mehrstufige Recherche mit Arbeitsinhalten und – sofern zulaessig – Webinformationen; strukturierte, quellenbezogene Ergebnisse.
- **Analyst**: Datenanalyse, Tabellen, Muster, Auffaelligkeiten und Ableitung von Erkenntnissen.

Diese Agenten sind keine Grundlage dafuer, jeden DWD-Prozess als eigenen Agenten zu bauen. Zuerst ist zu pruefen, ob der vorhandene Fachagent den Bedarf bereits abdeckt.

Dokumentiert in `Agents/Agenten_Uebersicht.md` und `Agents/Microsoft_Agents.md`.

### 2.4 Agent Builder versus Copilot Studio

Die zentrale Entscheidungsregel lautet:

- **Agent Builder** fuer schnelle, fokussierte und vergleichsweise einfache Wissensszenarien.
- **Copilot Studio** fuer komplexere Agents, mehrstufige Prozesse, Aktionen, Integrationen und erweiterte Governance-/ALM-Anforderungen.

Fuer DWD ist damit nicht die Technologie der Ausgangspunkt, sondern das fachliche Problem, die benoetigten Daten und die benoetigte Handlungstiefe.

Dokumentiert in `Copilot_Studio/Grundlagen.md` und `Agents/Agenten_Matrix.md`.

### 2.5 Harness-Konzept

Ein wichtiger Bestandteil des bisherigen Arbeitsstands ist die Abgrenzung des Harness-Begriffs.

Ein Harness ist die Laufzeit zwischen Agent und Modell. Es beeinflusst unter anderem Orchestrierung, Toolaufrufe, Fehlerbehandlung, Dateien, Skills und Memory.

Aktuell betrachtete Copilot-Studio-Harnesses:

- **GitHub Copilot Harness** – fuer reasoning-intensive, mehrstufige Aufgaben.
- **Standard Harness** – fuer regelbasierte und strukturierte Szenarien.
- **Copilot Chat Harness** – fuer die Erweiterung von M365 Copilot Chat mit Organisationswissen.

**Wichtig:** Das GitHub Copilot Harness in Copilot Studio ist nicht identisch mit der GitHub-Copilot-Produktfamilie.

Dokumentiert in `Copilot_Studio/Harnesses_und_Agententypen.md` und `Agents/Agenten_Matrix.md`.

### 2.6 Wissen und Wissensquellen

Ein Agent ist nur so belastbar wie sein fachlich freigegebenes Wissen.

Daher wurden folgende Grundsaetze als Knowledgebase-Wissen festgelegt:

- Wissensquellen muessen fachlich geeignet und freigegeben sein.
- Berechtigungen der Quelle sind Teil des Sicherheitsmodells.
- Quellenqualitaet, Aktualitaet und Verantwortlichkeit muessen nachvollziehbar sein.
- SharePoint ist eine wichtige Wissensquelle, aber nicht automatisch eine fachlich gute Wissensquelle.
- Die Quelle muss zum Zweck des Agents passen.
- Wissen, Datenmodell und Prozess bleiben fachlich getrennte Wissensbereiche.

Dokumentiert in `Wissensquellen/Grundlagen.md`.

### 2.7 Prompts

Prompts sind kein Ersatz fuer Architektur, Governance oder ein belastbares Datenmodell.

Als dauerhaftes Wissen wurden folgende Prinzipien festgehalten:

- eindeutiger Zweck
- klarer Kontext
- definierte Aufgabe
- erwartetes Ausgabeformat
- Begrenzung von Annahmen
- Testbarkeit und Wiederholbarkeit
- fachliche Pruefung der Ergebnisse

Dokumentiert in `Prompts/Grundlagen.md`.

### 2.8 Security Copilot und Security Agents

Security Copilot wurde bewusst als eigener agentischer Sicherheitsbereich eingeordnet.

Wesentliche Erkenntnisse:

- Security Copilot ist mehr als ein Chatbot; er umfasst Agents, Prompts, Promptbooks, Plugins, Connectoren und Integrationen in Sicherheitsprodukte.
- Security Agents koennen Analyse, Priorisierung, Untersuchung und wiederholbare Sicherheitsaufgaben unterstuetzen.
- Beispiele reichen ueber Security Analyst, Threat Intelligence sowie Agents in Entra, Intune, Purview, Sentinel und Defender.
- Bei autonomen Sicherheitsaktionen sind Identitaet, Berechtigungen, Trigger, Tools, Aktionen, Protokollierung und menschliche Kontrolle besonders relevant.
- Sicherheitsfachwissen bleibt primaer in `12_Sicherheit_und_Compliance`; `05_Copilot` dokumentiert die agentische Faehigkeit und deren Einordnung.

Dokumentiert in `Agents/Security_Agents.md`.

### 2.9 Finance Agent

Der Finance Agent wurde als Beispiel eines spezialisierten Fachagents eingeordnet.

Wesentliche Erkenntnisse:

- Finanzrecherche und Business Intelligence.
- Nutzung von Finanz-/ERP-Daten.
- Aktuelle Szenarien umfassen insbesondere Accounts Payable und Accounts Receivable sowie bestimmte ERP-Aktionen.
- Der Agent selbst gehoert in `05_Copilot`; fachliche Finanzprozesse und Datenmodelle gehoeren in die jeweiligen Fachdomänen.

Dokumentiert in `Agents/Finance_Agent.md`.

### 2.10 GitHub Copilot als eigene agentische Produktfamilie

GitHub bleibt ein gleichberechtigter Wissensbereich der Knowledgebase. Gleichzeitig ist GitHub Copilot ein Bestandteil der Agentenlandschaft.

Im bisherigen Arbeitsstand wurden insbesondere unterschieden:

- GitHub Copilot Chat
- Agent Mode
- Cloud Agent
- Code Review
- CLI
- Agent Skills
- agentische Workflows
- MCP-Integrationen

Der Cloud Agent kann Repository-Kontext untersuchen, planen, Aenderungen umsetzen, Tests ausfuehren und Pull Requests vorbereiten. Code Review dient der agentischen Pruefung von Pull Requests.

**Abgrenzung:**

- `05_Copilot/Agents/GitHub_Agents.md` dokumentiert die agentische Funktion.
- `06_GitHub` dokumentiert GitHub als Arbeits-, Entwicklungs- und Governance-Plattform.

### 2.11 Skills, MCP, Connectoren und APIs

Diese Begriffe wurden als Integrations- bzw. Erweiterungsmechanismen und nicht als eigene Agentenklassen eingeordnet.

- **Skills** liefern wiederverwendbare Anweisungen, Skripte und Ressourcen fuer definierte Aufgaben.
- **MCP** stellt einen standardisierten Integrationsweg fuer externe Werkzeuge und Kontext dar.
- **Connectoren** verbinden Agents mit Diensten und Datenquellen.
- **REST APIs** ermoeglichen direkte Systemintegration.
- **Workflows** koennen definierte Prozessaktionen ausfuehren.
- **Plugins** stellen in spezialisierten Plattformen zusaetzliche Werkzeuge und Faehigkeiten bereit.

Damit gilt: Der Agent entscheidet nicht allein ueber seine Faehigkeiten; seine reale Wirkung entsteht aus Wissen, Tools, Identitaet und erlaubten Aktionen.

### 2.12 Agent 365 und zentrale Verwaltung

Der bisherige Arbeitsstand hat die Verwaltungsebene ausdruecklich von der Agent-Funktion getrennt.

Fuer eine wachsende Agentenlandschaft werden insbesondere relevant:

- eindeutige Identitaet
- Registrierung / Inventarisierung
- Rollen und Berechtigungen
- Telemetrie und Beobachtung
- Governance-Richtlinien
- Lifecycle
- Kostenkontrolle
- Abschaltung

Agent 365 ist deshalb als Verwaltungs- und Governance-Ebene zu betrachten, nicht als neue fachliche Agentenklasse.

Dokumentiert in `Governance/Agent_365_und_Governance.md`.

## 3. DWD-Architekturprinzip

Fuer DWD gilt als konsolidiertes Architekturmodell:

**Benutzer -> Copilot -> Agent -> Harness/Laufzeit -> Wissen -> Tool/Connector/MCP -> Aktion -> Prozess -> Governance/Betrieb**

Nicht jede Loesung benoetigt alle Elemente in gleicher Auspraegung. Die Kette dient als Pruefmodell, um keine wichtige technische oder organisatorische Ebene zu uebersehen.

## 4. DWD-Entscheidungslogik

Vor der Entwicklung eines eigenen Agents ist in dieser Reihenfolge zu pruefen:

1. Reicht Microsoft 365 Copilot aus?
2. Gibt es einen passenden spezialisierten Microsoft-Agenten?
3. Reicht Agent Builder fuer das Szenario?
4. Werden Aktionen, Integrationen oder mehrstufige Prozesse benoetigt?
5. Ist Copilot Studio die passende Plattform?
6. Welche Wissensquellen sind erforderlich?
7. Welche Identitaet und Berechtigungen sind erforderlich?
8. Welche Tools, Connectoren, APIs, MCP-Server oder Workflows werden benoetigt?
9. Welche menschliche Kontrolle ist erforderlich?
10. Wie wird getestet, freigegeben, betrieben, ueberwacht und abgeschaltet?

## 5. Governance-Mindeststandard

Ein produktiver DWD-Agent darf nicht allein aufgrund einer funktionierenden Demo freigegeben werden.

Mindestens zu dokumentieren sind:

- Zweck
- Zielgruppe
- fachlicher Owner
- technischer Owner
- Identitaet
- Berechtigungen
- Wissensquellen
- Datenklassifizierung, soweit erforderlich
- Tools / Connectoren / MCP
- Aktionen
- Grenzen und Autonomiegrad
- Testfaelle und Testergebnisse
- Datenschutz-/Compliance-Pruefung, soweit erforderlich
- Freigabe
- Monitoring / Protokollierung
- Kosten
- Lifecycle
- Abschaltverfahren

Die bestehenden Governance-Dokumente unter `05_Copilot/Governance` bilden diesen Mindeststandard ab.

## 6. Status der wesentlichen Chat-Erkenntnisse

| Erkenntnis | Dauerhaft dokumentiert | Ablage |
|---|---|---|
| Copilot-/Agenten-Taxonomie | Ja | `Agents/Agenten_Matrix.md` |
| Microsoft 365 Copilot | Ja | `Microsoft_365_Copilot/*` |
| Researcher / Analyst | Ja | `Agents/Microsoft_Agents.md`, `Agents/Agenten_Uebersicht.md` |
| Agent Builder | Ja | `Microsoft_365_Copilot/*`, `Copilot_Studio/*` |
| Copilot Studio | Ja | `Copilot_Studio/*` |
| Harnesses | Ja | `Copilot_Studio/Harnesses_und_Agententypen.md` |
| Wissensquellen | Ja | `Wissensquellen/*` |
| Prompts | Ja | `Prompts/*` |
| Finance Agent | Ja | `Agents/Finance_Agent.md` |
| Security Copilot / Security Agents | Ja | `Agents/Security_Agents.md` |
| GitHub Copilot Agents | Ja | `Agents/GitHub_Agents.md` |
| Skills | Ja | `Agents/GitHub_Agents.md`, Matrix |
| MCP / Connectoren / APIs | Ja | Matrix, Copilot Studio, Governance |
| Agent 365 | Ja | `Governance/Agent_365_und_Governance.md` |
| Governance / Freigabe | Ja | `Governance/*` |
| DWD-Architekturmodell | Ja | dieses Dokument, Root-README, Matrix |
| DWD-Entscheidungslogik | Ja | Matrix, Agenten-Uebersicht, dieses Dokument |
| Abgrenzung GitHub-Wissensdomäne vs. GitHub-Copilot-Agentik | Ja | `Agents/GitHub_Agents.md`, dieses Dokument |

## 7. Bewusst noch offene Ausbaustufen

Die Konsolidierung bedeutet nicht, dass `05_Copilot` bereits vollstaendig ausgebaut ist. Folgende Themen sind **Ausbaustufen**, keine verlorenen Chat-Erkenntnisse:

- konkrete DWD-Agentenspezifikationen
- standardisierte Agent-Steckbriefe
- standardisierte Testfaelle
- Freigabeformular / Governance-Checkliste als Vorlage
- konkrete DWD-Wissensquellen je Agent
- Kosten- und Lizenzmodell je produktivem Szenario
- ALM- und Deployment-Standard fuer Copilot Studio
- konkrete DWD-Anwendungsfaelle und Patterns
- Verknuepfung der Agents mit den einzelnen DWD-Prozessen

Diese Punkte werden erst dann verbindlich, wenn die jeweiligen fachlichen Entscheidungen getroffen und dokumentiert wurden.

## 8. Quellenprinzip

Die Knowledgebase behandelt Microsoft- und GitHub-Dokumentation als primaere technische Quellen. Produktstatus, Funktionsumfang, Lizenzierung und Preview-/Frontier-Status sind zeitabhaengig und muessen bei kuenftigen Aktualisierungen erneut gegen die offiziellen Herstellerquellen geprueft werden.

Die fachliche Primaerquelle eines DWD-Prozesses oder Datenmodells bleibt dagegen in der jeweils zustaendigen Wissensdomäne.

## 9. Konsolidierungsregel fuer die Zukunft

Neue wesentliche Erkenntnisse aus Arbeitsgespraechen zu Copilot werden nicht dauerhaft nur im Chat belassen.

Bei einer fachlich relevanten Entscheidung gilt:

**Erkenntnis -> Einordnung -> Dokumentation im passenden Fachbereich -> Verlinkung in Matrix/Navigation -> ggf. Governance-/Projektentscheidung**

Damit bleibt der Chat ein Arbeitsmedium und `05_Copilot` der dauerhafte fachliche Wissensstand.
