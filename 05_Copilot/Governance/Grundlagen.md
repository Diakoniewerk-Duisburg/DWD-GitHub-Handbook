# Copilot Governance – Grundlagen

## Ziel

Copilot Governance stellt sicher, dass Copilot, Agents, Wissensquellen und Tools kontrolliert eingesetzt werden. Dabei muessen Nutzen, Datenschutz, Informationssicherheit, Berechtigungen und Betrieb gemeinsam betrachtet werden.

## Governance-Ebenen

| Ebene | Leitfrage |
|---|---|
| Identitaet | Wer darf den Agent verwenden? |
| Daten | Auf welche Informationen darf zugegriffen werden? |
| Wissen | Welche Quellen sind fachlich freigegeben? |
| Aktionen | Welche Systeme darf der Agent aufrufen oder veraendern? |
| Entwicklung | Wie wird der Agent erstellt und getestet? |
| Freigabe | Wer darf ihn produktiv veroeffentlichen? |
| Betrieb | Wie werden Nutzung, Fehler und Aenderungen ueberwacht? |
| Compliance | Welche Datenschutz- und Aufbewahrungsregeln gelten? |

## Berechtigungsprinzip

Agents sollen bestehende Microsoft-365-Berechtigungen nicht umgehen. Microsoft beschreibt fuer Microsoft-365-Copilot-Agents, dass bestehende Zugriffsgrenzen von Microsoft 365 und Microsoft Graph beruecksichtigt werden.

## Copilot Studio

Bei Copilot-Studio-Szenarien kommen weitere Governance-Ebenen hinzu, insbesondere:

- Umgebungen
- DLP-Richtlinien
- Connector-Governance
- Rollen und Berechtigungen
- ALM
- Freigabe und Veroeffentlichung
- Telemetrie und Nutzungsanalyse

## Minimaler Freigabeprozess

Vor der produktiven Bereitstellung eines DWD-Agents sollte mindestens dokumentiert sein:

1. Zweck und Zielgruppe
2. fachlicher Besitzer
3. technische Verantwortung
4. verwendete Wissensquellen
5. benoetigte Connectoren und Tools
6. Berechtigungsmodell
7. Testfaelle und Testergebnis
8. Datenschutz-/Compliance-Bewertung, soweit erforderlich
9. Freigabeentscheidung
10. Verfahren fuer Aenderung und Abschaltung

## Sicherheitsgrundsatz

Ein Agent ist eine Anwendung und muss entsprechend behandelt werden. Insbesondere duerfen sensible Daten, Connectoren und Aktionen nicht allein aufgrund eines funktionierenden Prototyps produktiv freigegeben werden.

## Primaerquelle

Microsoft Learn: [Datenschutz, Sicherheit und Governance bei Microsoft 365 Copilot](https://learn.microsoft.com/de-de/microsoft-365/copilot/extensibility/data-privacy-security)
