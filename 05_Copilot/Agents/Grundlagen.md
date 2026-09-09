# Agents – Grundlagen

## Was ist ein Agent?

Ein Agent ist ein spezialisierter KI-Assistent, der mit Anweisungen, Wissen und – je nach Ausbaustufe – Werkzeugen und Aktionen fuer eine definierte Aufgabe ausgestattet wird.

Ein Agent soll nicht einfach nur allgemeines Wissen liefern. Er soll einen klar abgegrenzten Zweck, definierte Wissensquellen und nachvollziehbare Grenzen besitzen.

## Bausteine eines Agents

| Baustein | Zweck |
|---|---|
| Anweisungen | Verhalten, Aufgabe, Rolle und Grenzen definieren |
| Wissen | Fachliche oder organisatorische Informationen bereitstellen |
| Tools | Andere Systeme oder Dienste aufrufen |
| Aktionen | Konkrete Arbeitsschritte ausfuehren |
| Ausgabekanal | Festlegen, wo der Agent bereitgestellt wird |
| Governance | Zugriff, Freigabe, Betrieb und Kontrolle regeln |

## Agent Builder und Copilot Studio

Fuer einfache, persoenliche oder kleine Team-Szenarien kann Agent Builder in Microsoft 365 Copilot geeignet sein. Wenn Integrationen, externe Datenquellen, komplexere Aktionen oder ein kontrollierter Unternehmenslebenszyklus erforderlich sind, ist Copilot Studio die geeignete Ausbaustufe.

Microsoft beschreibt insbesondere folgende Entscheidungskriterien:

- Zielgruppe
- geplanter Bereitstellungsbereich
- erforderliche Funktionalitaet
- Governance- und Lebenszyklusanforderungen

## DWD-Grundsatz

Vor der Erstellung eines Agents sind mindestens folgende Fragen zu beantworten:

1. Welches konkrete Problem loest der Agent?
2. Wer darf ihn verwenden?
3. Welche Daten benoetigt er?
4. Welche Daten darf er nicht verwenden?
5. Muss er nur antworten oder auch Aktionen ausfuehren?
6. Welche Systeme und Connectoren benoetigt er?
7. Wie wird der Agent getestet und freigegeben?
8. Wie wird er spaeter geaendert oder abgeschaltet?

## Sicherheitsprinzip

Ein Agent darf niemals als Umgehung bestehender Berechtigungen betrachtet werden. Die Berechtigungen der zugrunde liegenden Microsoft-365-Datenquellen bleiben eine zentrale Sicherheitsgrenze.

## Primaerquellen

- Microsoft Learn: [Auswahl zwischen Agent Builder und Copilot Studio](https://learn.microsoft.com/de-de/microsoft-365/copilot/extensibility/copilot-studio-experience)
- Microsoft Learn: [Agents in Copilot Studio](https://learn.microsoft.com/de-de/microsoft-copilot-studio/agents-overview)
