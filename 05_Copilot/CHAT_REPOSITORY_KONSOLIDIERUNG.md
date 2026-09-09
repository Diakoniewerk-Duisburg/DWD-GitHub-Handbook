# Copilot – Chat-/Repository-Konsolidierung

## Zweck

Dieses Dokument ist der verbindliche Abgleich zwischen dem bisherigen fachlichen Copilot-Arbeitsstand aus den Chats und dem aktuellen Wissensstand im Repository.

Es ersetzt die Aussage, dass eine blosse Strukturuebernahme bereits eine vollstaendige Konsolidierung darstellt. Ziel ist die nachvollziehbare Sicherung der relevanten Erkenntnisse, Begriffe, Aufzaehlungen und Entscheidungen.

**Stand:** 09.09.2026  
**Status:** KONSOLIDIERT – fachlicher Chatbestand und Repositorybestand zusammengefuehrt

---

## 1. Konsolidiertes Gesamtmodell

Der Copilot-Arbeitsstand wird als zusammenhaengendes System verstanden:

**Benutzer -> Copilot-Erfahrung -> Agent -> Harness/Laufzeit -> Wissen -> Tool/Connector/MCP -> Aktion -> Prozess -> Governance/Betrieb**

Nicht jede Loesung benoetigt jede Ebene. Die Kette ist ein Pruefmodell und verhindert, dass Produkt, Agent, Laufzeit, Wissen, Integration und Governance miteinander vermischt werden.

---

## 2. Copilot-Produkte und Erfahrungen

### Microsoft 365 Copilot

- allgemeine Copilot-Erfahrung fuer Microsoft-365-Arbeit
- Arbeitskontext aus Microsoft 365 und Microsoft Graph
- Nutzung vorhandener Zugriffsgrenzen
- eigener Agent nur bei zusaetzlichem abgegrenztem Wissen, Verhalten oder Aktionen

### GitHub Copilot

- eigene Produktfamilie fuer Softwareentwicklung
- Chat
- Agent Mode
- Cloud Agent
- Code Review
- CLI
- Agent Skills
- agentische Workflows
- MCP-Integrationen

### Security Copilot

- eigene Security-/IT-orientierte Copilot-Plattform
- spezialisierte Security Agents
- Analyse, Untersuchung, Priorisierung und wiederholbare Sicherheitsaufgaben
- enge Kopplung an Defender, Entra, Intune, Purview, Sentinel und weitere Sicherheitsquellen

### Finance Agent

- spezialisierter Fachagent fuer Finanz- und ERP-Szenarien
- Recherche und Business Intelligence
- ERP-Daten und definierte Aktionen
- insbesondere AP/AR-Szenarien im bisher betrachteten Funktionsumfang

**Repository-Ablage:** `05_Copilot/Microsoft_365_Copilot`, `05_Copilot/Agents/Finance_Agent.md`, `05_Copilot/Agents/Security_Agents.md`, `05_Copilot/Agents/GitHub_Agents.md` und `05_Copilot/Agents/Agenten_Matrix.md`.

---

## 3. Agenten-Typen und spezialisierte Agents

Die bisher im Chat behandelten Beispiele werden getrennt von den Plattformen gefuehrt:

- Researcher – mehrstufige Recherche und strukturierte Ergebnisse
- Analyst – Datenanalyse, Muster und Auffaelligkeiten
- Finance Agent – Finanz-/ERP-Fachaufgaben
- Security Analyst Agent – Sicherheitsanalyse
- Threat Intelligence / Security Agents – Sicherheits- und Bedrohungsaufgaben
- Agents in Entra, Defender, Intune, Purview und Sentinel
- eigene DWD-Fachagenten

Grundsatz: Ein vorhandener spezialisierter Agent ist vor der Entwicklung eines eigenen Agents zu pruefen.

---

## 4. Agent Builder und Copilot Studio

### Agent Builder

Geeignet fuer:

- schnelle Erstellung
- fokussierte Wissensszenarien
- vergleichsweise einfache individuelle oder kleine Team-Szenarien
- vorhandene Organisationsinhalte als Wissen

### Copilot Studio

Geeignet fuer:

- komplexere Agents
- mehrstufige Prozesse
- Aktionen
- Integrationen
- Connectoren, APIs und MCP
- erweiterte Governance und ALM
- breitere Bereitstellung

### Entscheidungsregel

Nicht die Technologie ist der Ausgangspunkt. Zuerst werden Problem, Zielgruppe, Daten, Wissen, benötigte Aktionen, Autonomie und Governance bestimmt.

---

## 5. Harness-Konzept

Der Chatbestand hat den Harness als eigenstaendige Laufzeitebene herausgearbeitet.

Ein Harness vermittelt zwischen Agent und Modell und beeinflusst insbesondere Orchestrierung, Toolaufrufe, Fehlerbehandlung und weitere Laufzeitfunktionen.

Aktuell dokumentierte Copilot-Studio-Harnesses:

1. **GitHub Copilot Harness** – reasoning-intensive, mehrstufige Aufgaben.
2. **Standard Harness** – regelbasierte und strukturierte Szenarien.
3. **Copilot Chat Harness** – Erweiterung von M365 Copilot Chat mit Organisationswissen.

Wichtige Abgrenzung:

**GitHub Copilot Harness != GitHub Copilot Produktfamilie**

---

## 6. Wissen und Wissensquellen


Ein Agent darf nicht nur technisch auf eine Quelle zugreifen koennen; die Quelle muss fachlich geeignet sein.

Konsolidierte Grundsaetze:

- fachlich freigegebene Quellen
- klare Verantwortlichkeit
- Aktualitaet
- Quellenqualitaet
- Berechtigungsgrenzen
- Quellenprioritaet bei Widerspruechen
- Umgang mit fehlendem Wissen
- SharePoint als moegliche, aber nicht automatisch geeignete Wissensquelle
- Trennung von Wissen, Datenmodell und Prozess

**Primaerquelle fuer diese Ebene:** `05_Copilot/Wissensquellen/`.

---

## 7. Prompts

Prompts sind ein Steuerungsmittel, aber kein Ersatz fuer Architektur oder Governance.

Konsolidierte Prinzipien:

- eindeutiger Zweck
- klarer Kontext
- definierte Aufgabe
- erwartetes Ausgabeformat
- Begrenzung von Annahmen
- Testbarkeit
- Wiederholbarkeit
- fachliche Pruefung der Ergebnisse

**Primaerquelle:** `05_Copilot/Prompts/`.

---

## 8. Agentische Erweiterungen und Integrationen

Die Chat-Aufzaehlungen wurden als technische Erweiterungsebene konsolidiert:

- **Skills** – wiederverwendbare Anweisungen, Skripte und Ressourcen
- **MCP** – standardisierter Integrationsweg fuer Tools und Kontext
- **Connectoren** – Verbindungen zu Diensten und Datenquellen
- **REST APIs** – direkte Systemintegration
- **Workflows** – definierte Prozessaktionen
- **Plugins** – zusaetzliche Werkzeuge/Faehigkeiten spezialisierter Plattformen

Diese Mechanismen sind **keine eigenen Agentenklassen**.

Grundsatz:

**Technische Erreichbarkeit != fachliche Berechtigung**

**Primaerquellen:** `05_Copilot/Agents/MCP_und_Tools.md` und `05_Copilot/Agents/Connectoren_und_Aktionen.md`.

---

## 9. GitHub als gleichberechtigte Wissensdomain

GitHub wurde im Chat bewusst nicht als blosse Copilot-Erweiterung eingeordnet.

### `06_GitHub`

Dokumentiert GitHub als:

- Entwicklungsplattform
- Repository-Plattform
- Arbeitsweise
- Branch-/Commit-/PR-Modell
- GitHub Actions
- Sicherheit
- Authentifizierung
- Troubleshooting
- HowTos
- Checklisten

### `05_Copilot/Agents/GitHub_Agents.md`

Dokumentiert die agentische Seite von GitHub Copilot:

- Chat
- Agent Mode
- Cloud Agent
- Code Review
- CLI
- Skills
- MCP
- agentische Workflows

Damit bleiben **GitHub als Plattform** und **GitHub Copilot als agentische Produktfamilie** fachlich getrennt.

---

## 10. Agenten-Spezifikation

Jeder eigene DWD-Agent wird nach einem einheitlichen Schema beschrieben:

1. Stammdaten
2. fachliche Definition
3. Wissen und Daten
4. Tools und Aktionen
5. Identitaet und Berechtigungen
6. Autonomie
7. Human-in-the-Loop
8. Grenzen und Fehlverhalten
9. Test und Qualitaet
10. Governance und Betrieb
11. Freigabekriterium

Damit wird die Chat-Erkenntnis „Agent nicht nur als Prompt betrachten“ dauerhaft abgebildet.

---

## 11. Autonomie

Konsolidierte Autonomiestufen:

- **A0 – Informativ:** Antworten und Informationen
- **A1 – Assistiv:** Vorschlaege, Entwuerfe, vorbereitete Ergebnisse
- **A2 – Kontrolliert:** Aktionen nach menschlicher Bestaetigung
- **A3 – Autonom:** definierte Aktionen ohne Einzelbestaetigung

Grundsaetze:

- niedrigste ausreichende Autonomie
- Autonomie und Berechtigung getrennt bewerten
- schreibende Aktionen mindestens kontrolliert behandeln
- A3 nur bei klarer Begrenzung, Fehlerbehandlung, Monitoring und Fallback

---

## 12. Human-in-the-Loop

Das im Chat herausgearbeitete Muster ist:

**Agent analysiert -> Vorschlag -> menschliche Pruefung -> Freigabe/Ablehnung -> Aktion -> Protokollierung**

Besonders relevant fuer:

- Genehmigungen
- Beschaffung
- Berechtigungsänderungen
- Provisionierung
- Datenänderungen
- finanzielle oder sonstige folgenreiche Entscheidungen

**Primaerquelle:** `05_Copilot/Patterns/Human_in_the_Loop.md`.

---

## 13. Agenten-Orchestrierung

Bei mehreren Agents gilt:

- Verantwortlichkeiten trennen
- nur erforderliche Daten weitergeben
- nur erforderliche Aktionen erlauben
- keine implizite Rechteerweiterung
- Ergebnisse nachvollziehbar machen
- Human-in-the-Loop an kritischen Stellen vorsehen

**Primaerquelle:** `05_Copilot/Patterns/Agenten_Orchestrierung.md`.

---

## 14. Lifecycle und ALM

Konsolidierter Lifecycle:

**Idee -> Anwendungsfall -> Spezifikation -> Bewertung -> Prototyp -> Test -> fachliche Freigabe -> technische Freigabe -> Produktivbetrieb -> Monitoring/Review -> Aenderung/Abschaltung -> Archivierung**

Grundsatz:

**Kein direkter Sprung vom Prototyp in den Produktivbetrieb.**

ALM erfordert getrennte Entwicklungs-, Test- und Produktivbereiche sowie nachvollziehbare Aenderungen und Rueckfallmoeglichkeiten.

---

## 15. Testing und Debugging

Konsolidierte Testebenen:

- Konfiguration
- Funktion
- Negativszenarien
- Berechtigungen
- Wissen und Quellen
- Aktionen
- Fehler und Abbruch
- Regression

Fehleranalyse entlang der Kette:

**Eingabe -> Agentenanweisung -> Wissensquelle -> Orchestrierung -> Tool/Connector -> Zielsystem -> Ergebnis**

---

## 16. Governance

Die Governance wurde als eigene Ebene konsolidiert:

- Risiko-/Schutzklasse
- fachliche Verantwortung
- technische Verantwortung
- Berechtigungen
- Datenschutz
- Informationssicherheit
- Freigabe
- Audit
- Monitoring
- Kosten/Lizenzierung
- Lifecycle
- Abschaltung

### DWD-Schutzklassen

Das Repository fuehrt fuer die weitere DWD-Bewertung:

- R0 – Informativ
- R1 – Assistiv
- R2 – Prozessbezogen
- R3 – Kritisch
- R4 – Hochkritisch

**Hinweis:** R0–R4 sind ein DWD-Governance-Modell und keine Microsoft-Produktklassifikation.

---

## 17. Berechtigungsmodell

Berechtigungen werden auf mehreren Ebenen betrachtet:

1. Benutzerberechtigung
2. Agentenberechtigung
3. Toolberechtigung
4. Aktionsberechtigung
5. Freigabeberechtigung

Grundsatz:

**Least Privilege und keine implizite Rechteeskalation.**

---

## 18. Datenschutz und Sicherheit

Konsolidierte Pruefpunkte:

- Zweck und Rechtsgrundlage
- Sensibilitaet der Daten
- Personenbezug
- Datenminimierung
- Zugriffs- und Empfaengerkreis
- Wissensquellen
- externe Dienste
- Speicherung/Aufbewahrung
- Protokollierung
- Loeschung
- Datenweitergabe
- Prompt Injection / manipulierte Inhalte
- ungewollte Tool-Aufrufe

Sicherheitsfachwissen bleibt primaer in `12_Sicherheit_und_Compliance`; `05_Copilot` beschreibt die agentische Faehigkeit und Governance.

---

## 19. Audit und Monitoring

Produktive Agents muessen hinsichtlich mindestens folgender Aspekte beobachtbar sein:

- Betriebsstatus
- relevante Aenderungen
- Tool-/Aktionsaufrufe, soweit zulaessig
- Fehler und Abbrueche
- sicherheitsrelevante Ereignisse
- Berechtigungsänderungen
- Eskalationen
- auffaelliges Verhalten

Bei schwerwiegendem Fehlverhalten muss eine kontrollierte Abschaltung moeglich sein.

---

## 20. Lizenzierung und Kosten

Die Chat-Erkenntnis zur Wirtschaftlichkeit wurde als eigener Governance-Punkt gesichert:

**Entwicklung + Test + Lizenzen/Verbrauch + Betrieb + Monitoring + Support + Weiterentwicklung**

Lizenz- und Preisangaben sind zeitabhaengig und muessen vor einer konkreten Beschaffungsentscheidung gegen aktuelle Herstellerinformationen geprueft werden.

---

## 21. DWD-Anwendungsfaelle

Die sieben im Chat entwickelten Kandidaten sind dauerhaft als eigene Steckbriefe dokumentiert:

1. Wissensagent
2. Beschaffungsagent
3. Genehmigungsagent
4. Ticketagent
5. Provisioningagent
6. Datenmigrationsagent
7. Adressbuchagent

Sie sind Kandidaten und keine Produktivfreigaben.

Die fachliche Prozessdokumentation bleibt in `08_Prozesse`; die technische Agentenbeschreibung bleibt in `05_Copilot`.

---

## 22. Entscheidungslogik fuer eigene Agents

Vor dem Bau eines eigenen Agents gilt:

1. Reicht Microsoft 365 Copilot?
2. Gibt es einen passenden spezialisierten Agenten?
3. Reicht Agent Builder?
4. Werden Aktionen oder Integrationen benoetigt?
5. Ist Copilot Studio erforderlich?
6. Welche Wissensquellen werden benoetigt?
7. Welche Identitaet und Berechtigungen sind erforderlich?
8. Welche Tools, Connectoren, APIs, MCP oder Workflows werden benoetigt?
9. Welche menschliche Kontrolle ist erforderlich?
10. Wie wird getestet, freigegeben, betrieben, ueberwacht und abgeschaltet?

---

## 23. Was wurde gegenueber dem bisherigen Chat korrigiert?

Die fruehere Konsolidierung war inhaltlich bereits weitgehend richtig, aber der Nachweis war zu pauschal. Mit diesem Dokument werden insbesondere die bisher nur zusammengefassten Aufzaehlungen explizit als dauerhafte Repository-Inhalte festgehalten.

Damit gilt nicht mehr nur:

> „Das Thema ist im Repository vorhanden.“

Sondern:

> **„Die relevante Chat-Erkenntnis ist identifiziert, fachlich eingeordnet und einer konkreten Repository-Ablage zugeordnet.“**

---

## 24. Konsolidierungsstatus

| Bereich | Chatbestand | Repository | Status |
|---|---|---|---|
| Copilot-Produkte | vorhanden | dokumentiert | konsolidiert |
| Agenten-Typen | vorhanden | dokumentiert | konsolidiert |
| Agent Builder / Copilot Studio | vorhanden | dokumentiert | konsolidiert |
| Harnesses | vorhanden | dokumentiert | konsolidiert |
| Wissen / Wissensquellen | vorhanden | dokumentiert | konsolidiert |
| Prompts | vorhanden | dokumentiert | konsolidiert |
| Connectoren / APIs / MCP | vorhanden | dokumentiert | konsolidiert |
| Skills / Plugins / Workflows | vorhanden | dokumentiert | konsolidiert |
| GitHub Copilot Agents | vorhanden | dokumentiert | konsolidiert |
| Security Copilot | vorhanden | dokumentiert | konsolidiert |
| Finance Agent | vorhanden | dokumentiert | konsolidiert |
| Agent 365 | vorhanden | dokumentiert | konsolidiert |
| Agenten-Spezifikation | vorhanden | dokumentiert | konsolidiert |
| Lifecycle / ALM | vorhanden | dokumentiert | konsolidiert |
| Autonomie | vorhanden | dokumentiert | konsolidiert |
| Human-in-the-Loop | vorhanden | dokumentiert | konsolidiert |
| Testing / Debugging | vorhanden | dokumentiert | konsolidiert |
| Governance | vorhanden | dokumentiert | konsolidiert |
| DWD-Anwendungsfaelle | vorhanden | dokumentiert | konsolidiert |
| Entscheidungslogik | vorhanden | dokumentiert | konsolidiert |

## 25. Abgrenzung: Konsolidierung vs. weitere Entwicklung

Konsolidiert ist der bisherige fachliche Arbeitsstand. Nicht automatisch abgeschlossen sind:

- technische Implementierung einzelner Agents
- produktive Freigaben
- konkrete Connector-/MCP-Konfigurationen
- konkrete Daten- und Berechtigungsmodelle
- konkrete ALM-/Deployment-Pipelines
- belastbare Lizenz-/Kostenentscheidungen fuer konkrete Produkte
- produktive Testnachweise

Diese Punkte sind Folgearbeiten und werden nicht rueckwirkend als bereits entschieden dargestellt.
