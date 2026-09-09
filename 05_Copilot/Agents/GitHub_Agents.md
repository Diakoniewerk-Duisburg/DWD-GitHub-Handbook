# GitHub Copilot – Agenten und agentische Funktionen

## Einordnung

GitHub Copilot ist kein einzelner Agent. GitHub stellt mehrere agentische Erfahrungen bereit, die unterschiedliche Teile des Softwareentwicklungsprozesses abdecken.

Dazu gehoeren insbesondere:

- Copilot Cloud Agent
- Agent Mode in der IDE
- Copilot CLI
- Copilot Code Review
- Custom Agents
- Agent Skills
- Agentic Workflows in GitHub Actions
- MCP-Integrationen
- Agent Apps und weitere Coding Agents

## Copilot Cloud Agent

Der Cloud Agent arbeitet asynchron in einer von GitHub bereitgestellten Entwicklungsumgebung.

### Kernfunktionen

- Repository recherchieren
- Implementierungsplan erstellen
- Code aendern
- Fehler beheben
- neue Features implementieren
- Testabdeckung verbessern
- Dokumentation aktualisieren
- technische Schulden reduzieren
- Merge-Konflikte bearbeiten
- Branch erstellen
- optional Pull Request erstellen

### Besonderheit

Der Agent arbeitet nicht nur als Codegenerator. Er kann einen Auftrag recherchieren, planen, implementieren, testen und die Ergebnisse fuer einen Pull Request vorbereiten.

## Agent Mode in der IDE

Agent Mode arbeitet innerhalb der Entwicklungsumgebung und kann Aufgaben in der lokalen Arbeitsumgebung ausfuehren.

Er ist damit vom Cloud Agent zu unterscheiden:

| Merkmal | Cloud Agent | Agent Mode |
|---|---|---|
| Ausfuehrung | GitHub-basierte Umgebung | lokale IDE-Umgebung |
| Arbeitsweise | asynchron | interaktiv |
| Repository | GitHub | lokaler Workspace/Repository |
| PR-Erstellung | Bestandteil des Workflows | je nach IDE/Workflow manuell bzw. nachgelagert |
| Schwerpunkt | delegierte Entwicklungsaufgabe | Entwickler-Agent im laufenden Entwicklungsprozess |

## Copilot Code Review

Copilot kann Pull Requests pruefen, Probleme identifizieren und Verbesserungsvorschlaege liefern.

Das ist ein Agenten-Szenario fuer **Qualitaetssicherung**, nicht fuer die eigentliche Implementierung.

## Custom Agents

Custom Agents erlauben eine Spezialisierung auf wiederkehrende Aufgaben.

Beispiele:

- Test-Agent
- Dokumentations-Agent
- Refactoring-Agent
- PowerShell-Agent
- Security-Review-Agent
- Architektur-Review-Agent

Fuer den DWD ist besonders interessant, dass die Spezialisierung mit eigenen Anweisungen und Werkzeugen kombiniert werden kann.

## Agent Skills

Skills kapseln wiederverwendbare Faehigkeiten fuer spezialisierte Aufgaben. Dadurch kann ein Agent standardisierte Arbeitsweisen fuer bestimmte Problemklassen verwenden.

## Agentic Workflows

GitHub Actions kann agentische Arbeitsweisen fuer wiederkehrende Repository-Aufgaben einsetzen. Damit entsteht die Verbindung zwischen:

**Agent → GitHub → GitHub Actions → Repository-Prozess**

Das ist fuer automatisierte Dokumentationspruefungen, Triage, Tests und andere wiederkehrende Entwicklungsaufgaben interessant.

## MCP

MCP kann Agenten kontrollierten Zugriff auf weitere Werkzeuge und Datenquellen ermoeglichen.

Fuer den DWD ist dabei besonders wichtig, dass MCP nicht nur als technische Integration, sondern auch unter Sicherheits- und Berechtigungsaspekten bewertet wird.

## Einordnung in die DWD-Knowledgebase

| Thema | Primaerer Bereich |
|---|---|
| GitHub Copilot allgemein | `06_GitHub` |
| Agentische Konzepte | `05_Copilot/Agents` |
| GitHub Cloud Agent | `05_Copilot/Agents` + `06_GitHub` |
| GitHub Actions | `06_GitHub/GitHub_Actions` |
| MCP | `05_Copilot` + `10_Entwicklung` |
| Code Review | `06_GitHub/Pull_Requests` |
| Custom Agents | `05_Copilot/Agents` |
| Agent Skills | `05_Copilot/Agents` |
| DWD-spezifische Coding Agents | `05_Copilot/Agents` + jeweiliger Entwicklungsbereich |

## DWD-Grundsatz

GitHub bleibt ein gleichwertiger Wissensbereich. Die Copilot-Knowledgebase beschreibt die **agentischen Konzepte und deren Rolle im Copilot-Oekosystem**. Die konkreten GitHub-Arbeitsweisen, Repository-Regeln und GitHub-Actions-Regeln bleiben primaer im Bereich `06_GitHub`.

## Primaerquellen

- GitHub Docs: Konzepte fuer GitHub Copilot Agents – https://docs.github.com/de/copilot/concepts/agents
- GitHub Docs: Copilot Cloud Agent – https://docs.github.com/de/copilot/concepts/agents/cloud-agent/about-cloud-agent
- GitHub Docs: Verantwortungsvolle Nutzung von Agents – https://docs.github.com/de/copilot/responsible-use/agents
