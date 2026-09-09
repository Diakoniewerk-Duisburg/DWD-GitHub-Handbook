# Copilot Studio – Harnesses und Agententypen

## Zweck

Copilot Studio verwendet aktuell drei unterschiedliche Harnesses. Das Harness ist die Laufzeitumgebung eines Agents und beeinflusst Orchestrierung, Autonomie, Werkzeuge, Dateien, Skills, Gedächtnis, Bereitstellung und Abrechnung.

## Die drei Harnesses

| Harness | Schwerpunkt | Geeignet fuer | Wesentliche Merkmale |
|---|---|---|---|
| **GitHub Copilot Harness** | komplexe, mehrstufige Arbeit | anspruchsvolle Geschaeftsprozesse | zielorientiertes Reasoning, mehrstufige Orchestrierung, Tools, Connectoren, MCP, Skills, Memory, Dateioperationen |
| **Standard Harness** | vorhersehbare Agenten und Workflows | regelbasierte Prozesse und strukturierte Dialoge | definierte Themen, Regeln, Verzweigungen und Agent-Flows |
| **Copilot Chat Harness** | Erweiterung von Microsoft 365 Copilot Chat | Unternehmenswissen direkt in M365 Copilot | deklarative bzw. benutzerdefinierte Agents, Wissen und Tools innerhalb der M365-Copilot-Erfahrung |

## GitHub Copilot Harness

Das GitHub Copilot Harness ist nicht mit GitHub Copilot fuer Softwareentwicklung gleichzusetzen. Innerhalb von Copilot Studio ist es eine Agenten-Laufzeit fuer komplexe, mehrstufige Geschaeftsaufgaben.

Typische Eigenschaften:

- nimmt ein Ziel entgegen und zerlegt es in Arbeitsschritte,
- kann mehrere Werkzeuge und Wissensquellen orchestrieren,
- kann bei Fehlern alternative Pfade versuchen,
- kann Word-, Excel-, PowerPoint- und PDF-Dateien erstellen und bearbeiten,
- unterstuetzt Skills,
- kann dauerhaften Kontext bzw. Memory verwenden,
- kann verbundene Agents einbinden,
- kann MCP verwenden,
- wird in einer kontrollierten Laufzeitumgebung ausgefuehrt.

### Abgrenzung zu GitHub Copilot

**GitHub Copilot** ist eine eigene Produktfamilie fuer Softwareentwicklung.

Das **GitHub Copilot Harness in Copilot Studio** ist dagegen eine Agenten-Laufzeit fuer Geschaeftsprozesse. Die Namensaehnlichkeit darf nicht zu einer fachlichen Gleichsetzung fuehren.

## Standard Harness

Das Standard Harness eignet sich fuer vorhersehbare, regelbasierte Agenten und strukturierte Prozesse.

Typische Einsatzfaelle:

- definierte Gespraechsablaeufe,
- feste Regeln und Verzweigungen,
- bekannte Prozessschritte,
- kontrollierte Workflows,
- Agents, bei denen vorhersehbares Verhalten wichtiger ist als maximale Autonomie.

## Copilot Chat Harness

Das Copilot Chat Harness dient dazu, Microsoft 365 Copilot Chat mit organisationsspezifischem Wissen und spezialisierten Agents zu erweitern.

Es eignet sich insbesondere fuer:

- fachlich abgegrenzte Wissensbereiche,
- SharePoint- und andere Unternehmensinformationen,
- deklarative Agents,
- spezialisierte Assistenten innerhalb der gewohnten M365-Copilot-Oberflaeche.

## Entscheidungsregel fuer DWD

| Anforderung | Empfohlene Wahl |
|---|---|
| Komplexer Prozess mit mehreren selbststaendigen Schritten | GitHub Copilot Harness |
| Agent soll Probleme erkennen und alternative Wege versuchen | GitHub Copilot Harness |
| Agent muss Dateien erzeugen oder bearbeiten | GitHub Copilot Harness |
| Regelbasierter und nachvollziehbarer Prozess | Standard Harness |
| Fester Dialog mit klaren Verzweigungen | Standard Harness |
| M365 Copilot um DWD-Wissen erweitern | Copilot Chat Harness |
| Fachwissen aus SharePoint direkt in Copilot Chat bereitstellen | Copilot Chat Harness |
| Softwareentwicklung | GitHub Copilot Produktfamilie, nicht automatisch Copilot-Studio-Harness |

## Governance

Die Wahl des Harness ist Teil der Architekturentscheidung. Vor einer produktiven Nutzung sind mindestens Datenquellen, Identitaet, Berechtigungen, Tools, Connectoren, MCP, Aktionen, Kosten, Teststrategie, Freigabe und Lebenszyklus zu bewerten.

## Primaerquellen

- Microsoft Learn: [Uebersicht ueber Agents](https://learn.microsoft.com/de-de/microsoft-copilot-studio/agents-overview)
- Microsoft Learn: [Harness auswaehlen](https://learn.microsoft.com/de-de/microsoft-copilot-studio/harnesses-overview)
- Microsoft Learn: [Copilot Chat Harness](https://learn.microsoft.com/de-de/microsoft-copilot-studio/microsoft-365-copilot-extend-with-agents)
