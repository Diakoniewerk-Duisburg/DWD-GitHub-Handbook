# Agenten – Uebersicht und Einordnung

## Zweck

Dieser Artikel ordnet die unterschiedlichen Agenten im Microsoft-Copilot-Umfeld ein. Wichtig ist die Unterscheidung zwischen **Agent**, **Agent-Harness/Plattform**, **vorgefertigtem Fachagenten** und **benutzerdefiniertem Agenten**.

Nicht alles, was Microsoft oder GitHub als „Agent“ bezeichnet, ist technisch dasselbe.

## 1. Die vier Agent-Kategorien

| Kategorie | Beispiel | Hauptzweck | Einordnung im DWD-Wissensmodell |
|---|---|---|---|
| Microsoft-1P-Agent | Researcher, Analyst | Vorgefertigte Aufgaben | `05_Copilot/Agents` |
| Fach-/Produkt-Agent | Finance Agent, Security Analyst | Spezialisierte Fachdomäne | `05_Copilot/Agents` + Fachdomäne |
| Agent-Harness / Plattform | GitHub Copilot Harness | Ausfuehrungs- und Entwicklungsumgebung fuer agentische Aufgaben | `05_Copilot/Agents` + `06_GitHub` |
| Eigener Agent | DWD-Beschaffungs-Agent | Organisationsspezifische Aufgabe | `05_Copilot/Agents` + betroffener Prozess |

## 2. Microsoft 365 Copilot – vorgefertigte Agents

Microsoft stellt Agents bereit, die bestimmte Arbeitsaufgaben bereits spezialisiert abdecken.

### Researcher

Der Researcher-Agent ist auf komplexe, mehrstufige Recherche ausgelegt. Er kann Arbeitsinhalte und – sofern zugelassen – Webinformationen zusammenführen und liefert strukturierte, quellenbezogene Ergebnisse.

**Stärken:**
- Multi-Source-Recherche
- Quellenangaben
- strukturierte Berichte
- Analyse von Arbeitsinhalten und Webinformationen
- geeignet fuer Entscheidungsgrundlagen

**Typische DWD-Nutzung:**
- Markt- und Anbieterrecherche
- Vergleich von Loesungsansaetzen
- Recherche zu Microsoft-365-Themen
- Vorbereitung von Entscheidungsunterlagen

→ Detail: `Microsoft_Agents.md`

### Analyst

Der Analyst-Agent ist auf Datenanalyse ausgerichtet. Er eignet sich insbesondere fuer Zahlen, Tabellen und die Ermittlung von Auffaelligkeiten oder Mustern.

**Stärken:**
- Datenbereinigung und -aufbereitung
- Zusammenfassung von Zahlen
- Analyse von Tabellen
- Erkennen von Mustern und Auffaelligkeiten
- Ableitung von Erkenntnissen

**Typische DWD-Nutzung:**
- Auswertung von Projekt- und Betriebsdaten
- Analyse von Excel-Daten
- Qualitaetspruefungen
- Vorbereitung von Kennzahlen

## 3. Fachagenten

Fachagenten sind auf eine bestimmte Geschaeftsfunktion oder technische Domäne zugeschnitten.

### Finance Agent

Der Finance Agent ist ein Beispiel fuer einen spezialisierten Fachagenten. Er verbindet finanzbezogene Recherche und Business Intelligence mit ERP-Daten. Die aktuellen Funktionen umfassen unter anderem Fragen und Analysen zu Accounts Payable und Accounts Receivable sowie bestimmte Aktionen im ERP.

**Stärken:**
- Finanzrecherche
- Business Briefs
- Vergleich von Unternehmen
- Verbindung oeffentlicher und interner Daten
- Abfragen von Kreditoren-/Debitorendaten
- bestimmte ERP-Aktionen

**Einordnung:**

`05_Copilot/Agents` beschreibt den Agenten selbst. Finanzfachliche Prozesse und Datenmodelle gehoeren dagegen in die jeweils fachlich zustaendigen Wissensbereiche, z. B. `07_Daten`, `08_Prozesse` oder spaeter einen eigenen Finanzbereich.

→ Detail: `Finance_Agent.md`

### Security Analyst Agent

Der Security Analyst Agent gehoert zum Microsoft-Security-Copilot-Umfeld. Er analysiert Sicherheitsdaten, kann Risiken priorisieren und arbeitet unter anderem mit Microsoft Defender und Microsoft Sentinel.

**Stärken:**
- Muster- und Trendanalyse
- Anomalieerkennung
- Risikobewertung
- Priorisierung
- Analyse grosser Datenmengen
- Beweispfade und Begruendungen

**Einordnung:**

Der Agent wird unter `05_Copilot/Agents` dokumentiert; Sicherheitsfachwissen bleibt primaer in `12_Sicherheit_und_Compliance`.

## 4. GitHub Copilot – besondere Einordnung

GitHub Copilot ist nicht einfach ein einzelner Fachagent wie Finance Agent. GitHub stellt mehrere agentische Erfahrungen bereit.

Dazu gehoeren insbesondere:

- Copilot Cloud Agent
- Agent Mode in der IDE
- Copilot CLI
- Copilot Code Review
- Custom Agents
- Agent Skills
- Agentic Workflows in GitHub Actions
- MCP-Integrationen

Der **GitHub Copilot Harness** in Copilot Studio ist wiederum eine Ausfuehrungsgrundlage fuer reasoning-intensive, mehrstufige Agenten. Er ist daher als Plattform-/Harness-Konzept von einzelnen GitHub-Copilot-Produkten zu unterscheiden.

→ Detail: `GitHub_Agents.md`

## 5. Eigene DWD-Agents

Eigene Agents werden nicht danach gebaut, welche Technologie gerade verfuegbar ist, sondern nach einem konkreten fachlichen Problem.

Ein eigener DWD-Agent sollte mindestens folgende Eigenschaften besitzen:

1. klar definierter Zweck
2. definierte Zielgruppe
3. definierte Wissensquellen
4. definierte Berechtigungen
5. definierte Tools und Aktionen
6. definierte Grenzen
7. Testfaelle
8. fachlicher Owner
9. technischer Owner
10. Freigabe- und Lifecycle-Regel

Beispiele fuer spaetere DWD-Pruefungen koennten sein:

- Wissens-Agent fuer SharePoint/M365
- Beschaffungs-/Genehmigungs-Agent
- Ticket-Agent
- Provisioning-Agent
- Datenmigrations-Agent
- Adressbuch-Agent

Diese Beispiele sind **Kandidaten**, keine bereits freigegebenen Produktivloesungen.

## 6. Funktionsmatrix

| Agent/Typ | Recherche | Datenanalyse | Fachwissen | Aktionen | Dateien | Multi-Step | Integration |
|---|---:|---:|---:|---:|---:|---:|---:|
| Standard Copilot | ✓ | ✓ | allgemein | begrenzt | ✓ | begrenzt | M365 |
| Researcher | ✓✓ | ✓ | ✓ | begrenzt | ✓ | ✓✓ | Web + M365 |
| Analyst | ✓ | ✓✓ | ✓ | begrenzt | ✓ | ✓ | M365/Daten |
| Finance Agent | ✓ | ✓✓ | Finanzen | ✓ | ✓ | ✓ | ERP/MCP |
| Security Analyst | ✓ | ✓✓ | Sicherheit | ✓/Analyse | ✓ | ✓✓ | Defender/Sentinel |
| GitHub Cloud Agent | ✓ | ✓ | Softwareentwicklung | ✓✓ | ✓✓ | ✓✓ | GitHub/GitHub Actions |
| Eigener Agent | nach Design | nach Design | nach Design | nach Design | nach Design | nach Design | nach Design |

Die Matrix ist bewusst qualitativ. Verfuegbarkeit, Lizenzierung und Funktionsumfang koennen sich je Produkt und Release aendern.

## 7. Entscheidungslogik fuer DWD

**Frage 1: Brauchen wir nur eine Antwort?**
→ Microsoft 365 Copilot / Standard Chat pruefen.

**Frage 2: Brauchen wir tiefgehende Recherche?**
→ Researcher pruefen.

**Frage 3: Muessen Daten analysiert werden?**
→ Analyst pruefen.

**Frage 4: Geht es um eine spezielle Fachdomäne mit eigener Datenwelt?**
→ passenden Fachagenten pruefen, z. B. Finance oder Security Analyst.

**Frage 5: Muss ein Agent Systeme bedienen oder Prozesse ausfuehren?**
→ Agent Builder oder Copilot Studio pruefen.

**Frage 6: Geht es um Softwareentwicklung und GitHub-Arbeit?**
→ GitHub Copilot Agenten verwenden und im GitHub-Wissensbereich dokumentieren.

**Frage 7: Gibt es keinen passenden vorgefertigten Agenten?**
→ eigenen DWD-Agenten spezifizieren.

## Primaerquellen

- Microsoft Learn: Agents fuer Microsoft 365 Copilot
- Microsoft Learn: Agents in Copilot Studio
- Microsoft Learn: Researcher Agent
- Microsoft Learn: Finance Agent
- Microsoft Learn: Security Analyst Agent
- GitHub Docs: GitHub Copilot Agents
