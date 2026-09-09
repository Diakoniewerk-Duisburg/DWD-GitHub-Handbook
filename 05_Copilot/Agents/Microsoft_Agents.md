# Microsoft 365 Copilot – vorgefertigte Agents

## Zweck

Microsoft stellt neben dem allgemeinen Copilot-Erlebnis spezialisierte Agents bereit. Diese Agents sind auf bestimmte Arbeitsmuster optimiert und muessen deshalb nicht wie ein eigener DWD-Agent von Grund auf gebaut werden.

## Researcher Agent

Der Researcher-Agent ist fuer komplexe, mehrstufige Rechercheaufgaben ausgelegt.

### Kernfunktionen

- Recherche ueber mehrere Quellen
- Einbeziehung von Arbeitsinhalten, auf die der Benutzer Zugriff hat
- optional Webrecherche
- strukturierte Berichte
- Quellenangaben
- Nachfragen zur Praezisierung der Recherche
- mehrstufiges Schlussfolgern

### Wann einsetzen?

Wenn eine Aufgabe deutlich mehr als eine schnelle Zusammenfassung oder eine einfache Frage-Antwort-Interaktion erfordert.

### Beispiel

> Vergleiche drei technische Loesungsansaetze fuer einen M365-Prozess. Beruecksichtige unsere vorhandenen Projektunterlagen und aktuelle Microsoft-Dokumentation. Fuehre Vor- und Nachteile sowie offene Entscheidungen auf.

### Grenzen

Researcher ersetzt keine fachliche Freigabe. Ergebnisse muessen bei Entscheidungen mit Auswirkungen auf Sicherheit, Datenschutz, Architektur oder Finanzen geprueft werden.

## Analyst Agent

Der Analyst-Agent ist auf Daten und analytische Aufgaben ausgerichtet.

### Kernfunktionen

- Daten analysieren
- Tabellen und Zahlen auswerten
- Daten bereinigen und zusammenfassen
- Muster und Auffaelligkeiten erkennen
- Erkenntnisse aus Daten ableiten

### Beispiel

> Analysiere die letzten drei Monatsauswertungen und markiere Positionen, deren Werte deutlich vom bisherigen Verlauf abweichen.

### Einordnung

Der Analyst ist fuer Datenanalyse geeignet. Er ist nicht automatisch ein Fachagent fuer Controlling oder Finanzbuchhaltung.

## Weitere Microsoft-Agents

Das Microsoft-365-Copilot-Umfeld entwickelt sich laufend weiter. Je nach Lizenz, Rollout und Produktstand koennen weitere vorgefertigte Agents oder Agent-Erfahrungen bereitgestellt werden, beispielsweise fuer:

- Moderation und Besprechungen
- Projektarbeit
- Self-Service fuer Mitarbeiter
- kreative Ideenentwicklung
- Uebersetzung und Kommunikation

Diese Agents werden in der Wissensbasis einzeln dokumentiert, sobald sie fuer den DWD relevant und im verwendeten Tenant verfuegbar sind.

## Administrationssicht

Vorgefertigte Microsoft-Agents sind nicht automatisch fuer jeden Benutzer uneingeschraenkt verfuegbar. Verfuegbarkeit, Lizenzierung, Rollout und Administrationsoptionen muessen getrennt betrachtet werden.

Fuer den DWD sind deshalb mindestens zu dokumentieren:

| Merkmal | Dokumentation |
|---|---|
| Agent | Produktname und konkrete Variante |
| Zweck | Welche Aufgabe wird geloest? |
| Zielgruppe | Welche Benutzer duerfen ihn verwenden? |
| Daten | Welche Datenquellen werden verwendet? |
| Webzugriff | Ja/Nein bzw. Administrationsvorgabe |
| Berechtigungen | Welche bestehenden Berechtigungen gelten? |
| Lizenz | Welche Voraussetzung besteht? |
| Status | Verfuegbar / Preview / nicht freigegeben |
| Governance | Welche DWD-Regeln gelten? |

## Primaerquellen

- Microsoft Learn: Researcher Agent – https://learn.microsoft.com/de-de/microsoft-365/copilot/researcher-agent
- Microsoft Learn: Researcher FAQ – https://learn.microsoft.com/de-de/copilot/microsoft-365/faq-researcher
- Microsoft Learn: Microsoft 365 Copilot Agents – https://learn.microsoft.com/de-de/microsoft-365/copilot/extensibility/agents-overview
