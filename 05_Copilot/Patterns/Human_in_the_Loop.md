# Pattern: Human-in-the-Loop

## Zweck

Der Agent bereitet eine Handlung vor, eine berechtigte Person entscheidet und erst danach wird eine folgenreiche Aktion ausgefuehrt.

```text
Agent analysiert
      -> Vorschlag / Ergebnis
      -> menschliche Pruefung
      -> Freigabe oder Ablehnung
      -> Aktion
      -> Protokoll
```

## Geeignete Einsatzfaelle

- Genehmigungen
- Beschaffung
- Berechtigungsänderungen
- Provisioning
- Datenveraenderungen
- fachliche Entscheidungen mit Auswirkungen auf Personen oder Organisation

## Mindestanforderungen

1. eindeutiger Entscheidungspunkt
2. berechtigte entscheidende Person oder Rolle
3. nachvollziehbare Entscheidungsgrundlage
4. Anzeige relevanter Daten und Quellen
5. eindeutige Freigabe / Ablehnung
6. Protokollierung
7. definiertes Verhalten bei Ablehnung, Timeout oder Fehler

## DWD-Grundsatz

Bei Unsicherheit oder nicht eindeutig automatisierbaren Entscheidungen wird die Kontrolle an einen Menschen uebergeben. Human-in-the-Loop ist kein Ersatz fuer ein sauberes Berechtigungs- und Governance-Modell.
