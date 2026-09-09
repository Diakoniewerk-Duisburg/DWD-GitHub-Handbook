# Copilot Studio – Grundlagen

## Zweck

Microsoft Copilot Studio ist die Plattform fuer die Erstellung und Erweiterung anspruchsvollerer Agents. Sie verbindet Anweisungen und Wissen mit Tools, Connectoren, Datenquellen und – je nach Szenario – automatisierten Aktionen.

## Wann Copilot Studio einsetzen?

Copilot Studio ist insbesondere sinnvoll, wenn ein Agent:

- auf mehrere Unternehmenssysteme zugreifen muss,
- externe Datenquellen oder APIs benoetigt,
- Aktionen oder Workflows ausfuehren soll,
- ueber Teams, Websites oder andere Kanaele bereitgestellt werden soll,
- einen kontrollierten Entwicklungs-, Test- und Produktionslebenszyklus benoetigt,
- erweiterte Governance- und Sicherheitsanforderungen besitzt.

## Zentrale Bausteine

### Wissen

Wissensquellen liefern den fachlichen Kontext fuer Antworten. Dazu koennen unter anderem Microsoft-365-Inhalte, SharePoint-Inhalte, Connectoren und weitere Unternehmensdatenquellen gehoeren.

### Tools

Tools ermoeglichen Interaktionen mit anderen Systemen. Connectoren koennen beispielsweise Unternehmensdaten abrufen oder Aktionen in angebundenen Diensten ausloesen.

### Themen und Anweisungen

Sie steuern das Verhalten und die fachliche Ausrichtung des Agents.

### Umgebungen

Fuer Unternehmensloesungen ist eine Trennung von Entwicklung, Test und Produktion ein wichtiger Bestandteil des Lebenszyklus.

## ALM-Grundsatz

Ein produktiver Agent soll nicht direkt und unkontrolliert in der Produktionsumgebung entwickelt werden. Aenderungen muessen nachvollziehbar getestet und anschliessend gezielt veroeffentlicht werden.

## Connector-Governance

Connectoren sind eine wesentliche Sicherheitsgrenze. Vor ihrer Verwendung muss geklaert werden:

- welche Daten gelesen werden,
- welche Aktionen ausgefuehrt werden,
- welche Identitaet verwendet wird,
- welche Benutzer den Agent verwenden duerfen,
- welche DLP- und Umgebungsrichtlinien gelten.

## Primaerquelle

Microsoft Learn: [Funktionen des Agents erweitern](https://learn.microsoft.com/de-de/microsoft-copilot-studio/extend-agent-capabilities)
