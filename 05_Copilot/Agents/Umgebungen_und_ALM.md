# Umgebungen und ALM

## Ziel

Agents und agentische Loesungen werden nicht direkt aus dem Experimentierzustand in den Produktivbetrieb uebernommen. Entwicklung, Test und Produktion sind nachvollziehbar zu trennen.

## Grundmodell

**Entwicklung -> Test/Validierung -> Freigabe -> Produktion -> Monitoring -> Aenderung oder Abschaltung**

Die konkrete technische Umsetzung richtet sich nach der verwendeten Plattform, insbesondere Copilot Studio, Power Platform oder GitHub.

## DWD-Mindestanforderungen

- klare Umgebung fuer Entwicklung und Erprobung
- kontrollierter Testbereich
- getrennte Produktivumgebung
- definierter Freigabeprozess
- nachvollziehbare Konfiguration
- dokumentierte Abhaengigkeiten zu Connectoren, Tools, Wissensquellen und Identitaeten
- reproduzierbare Aenderungen, soweit technisch moeglich
- Rueckfall- oder Abschaltmoeglichkeit

## Aenderungsmanagement

Aenderungen an Agenten koennen Verhalten, Datenzugriff und Aktionen veraendern. Deshalb sind insbesondere folgende Aenderungen neu zu bewerten:

- neue Wissensquellen
- neue Tools oder Connectoren
- neue Schreibaktionen
- andere Identitaeten oder Berechtigungen
- hoehere Autonomiestufe
- neue Zielgruppen
- neue fachliche Einsatzgebiete

## Bezug zum Lifecycle

Die Umgebungs- und ALM-Struktur unterstuetzt den [Agenten-Lifecycle](Agenten_Lifecycle.md). Ein Prototyp ist kein Produktionssystem.

## Verwandte Dokumente

- [Agenten-Lifecycle](Agenten_Lifecycle.md)
- [Agenten-Spezifikation](Agenten_Spezifikation.md)
- [Autonomiestufen](Autonomiestufen.md)
- [Governance](../Governance/Grundlagen.md)
