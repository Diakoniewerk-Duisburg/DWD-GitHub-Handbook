# Security Agents

## Einordnung

Security Agents bilden einen eigenen fachlichen Bereich innerhalb des Microsoft-Security-Copilot-Oekosystems. Sie sind nicht einfach eine weitere Variante eines allgemeinen Microsoft-365-Copiloten.

Microsoft Security Copilot verbindet generative KI mit Sicherheitsdaten, Microsoft-Sicherheitsprodukten und konfigurierten Aktionen. Agents koennen wiederholbare Sicherheitsaufgaben automatisieren und dabei innerhalb administrativ festgelegter Identitaeten, Berechtigungen und Ausfuehrungsgrenzen arbeiten.

## Wichtige Agent-Kategorien

| Bereich | Beispiele | Schwerpunkt |
|---|---|---|
| Security Operations | Security Analyst Agent | Sicherheitsdaten analysieren, Risiken erkennen und priorisieren |
| Threat Intelligence | Threat Intelligence Briefing Agent | Bedrohungsinformationen sammeln, korrelieren und Berichte erstellen |
| Identity & Access | Agents in Microsoft Entra | Identitaeten, Zugriffe und sicherheitsrelevante Signale analysieren |
| Endpoint Security | Agents in Microsoft Intune | Endpunkte und sicherheitsrelevante Verwaltungsaufgaben |
| Data Security | Agents in Microsoft Purview | DLP, Insider Risk und Datensicherheitsereignisse analysieren |
| SIEM / Detection | Agents in Microsoft Sentinel | Vorfaelle analysieren und Hunting-/KQL-Aufgaben unterstuetzen |
| Defender | Agents in Microsoft Defender | Incident Response, Threat Hunting und Sicherheitsanalyse |

Die konkrete Agent-Landschaft entwickelt sich weiter. Deshalb wird in der Knowledgebase zwischen dem fachlichen Bereich und einzelnen aktuell verfuegbaren Agents unterschieden.

## Zentrale Funktionen

Security Agents koennen insbesondere:

- Sicherheitsereignisse analysieren
- Risiken priorisieren
- Untersuchungen strukturieren
- Threat Intelligence zusammenfuehren
- Vorfaelle untersuchen
- Hunting-Abfragen unterstuetzen
- wiederholbare Sicherheitsworkflows automatisieren
- Ergebnisse und Empfehlungen erzeugen
- je nach Konfiguration auch definierte Aktionen ausfuehren

## Autonomie und Kontrolle

Ein Security Agent kann je nach Typ und Konfiguration assistiv oder autonom arbeiten. Entscheidend sind dabei:

- Agent-Identitaet
- Rollen und Berechtigungen
- Datenzugriff
- Trigger
- erlaubte Tools und Aktionen
- menschliche Kontrolle
- Protokollierung und Nachvollziehbarkeit

Ein Agent darf deshalb nicht nur nach seiner KI-Leistung bewertet werden. Fuer den produktiven Einsatz ist mindestens ebenso wichtig, **was der Agent mit welchen Rechten selbststaendig tun darf**.

## Security Copilot als Plattform

Security Copilot stellt neben Agents weitere Bausteine bereit:

- Prompts
- Promptbooks
- Plugins
- Connectoren
- Security Store
- eigene Custom Agents
- Integrationen in Defender, Entra, Intune, Purview und Sentinel

Damit ist Security Copilot eher als **agentische Sicherheitsplattform** zu verstehen und nicht lediglich als Chatbot.

## DWD-Einordnung

Fuer die DWD-Knowledgebase ist Security Copilot besonders relevant fuer die Bereiche:

- Identitaet und Zugriff
- Informationssicherheit
- Datenschutz und Datensicherheit
- Endpoint Security
- Security Operations
- Audit und Untersuchung
- Sicherheitsautomatisierung

Die fachliche Dokumentation der Sicherheitsprozesse bleibt jedoch unter `12_Sicherheit_und_Compliance`. Unter `05_Copilot/Agents` wird dokumentiert, **welche Copilot-/Agent-Funktion diese Prozesse unterstuetzen kann**.

## Entscheidungsregel

Ein Security Agent sollte nur eingesetzt werden, wenn sein Datenzugriff, seine Identitaet, seine Berechtigungen, seine Trigger und seine moeglichen Aktionen eindeutig bekannt und verantwortet sind.

Besonders bei autonomen Aktionen gilt das Prinzip:

> So wenig Berechtigung und Autonomie wie moeglich, so viel wie fuer den konkreten Sicherheitsprozess erforderlich.

## Primaerquellen

- Microsoft Learn: [Microsoft Security Copilot](https://learn.microsoft.com/de-de/copilot/security/microsoft-security-copilot)
- Microsoft Learn: [Security Copilot Agents](https://learn.microsoft.com/en-us/copilot/security/agents-security-copilot)
- Microsoft Learn: [Security Copilot Agents – Uebersicht](https://learn.microsoft.com/en-us/copilot/security/agents-overview)
- Microsoft Learn: [Security Copilot in Workflows](https://learn.microsoft.com/en-us/copilot/security/workflows-overview)
