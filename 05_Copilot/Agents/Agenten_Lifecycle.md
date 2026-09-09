# Agenten-Lifecycle – DWD-Standard

## Ziel

Eigene Agents werden als technische Anwendungen mit einem kontrollierten Lebenszyklus behandelt.

```text
Idee
  -> Anwendungsfall
  -> Spezifikation
  -> Bewertung
  -> Prototyp
  -> Test
  -> fachliche Freigabe
  -> technische Freigabe
  -> Produktivbetrieb
  -> Monitoring / Review
  -> Aenderung oder Abschaltung
  -> Archivierung
```

## Phasen

### 1. Idee

Ein konkretes fachliches Problem wird beschrieben. Technologieentscheidungen werden noch nicht vorweggenommen.

### 2. Anwendungsfall

Nutzen, Zielgruppe, Prozess, Daten und erwartetes Ergebnis werden abgegrenzt.

### 3. Spezifikation

Der Agent wird nach `Agenten_Spezifikation.md` beschrieben.

### 4. Bewertung

Risiken, Berechtigungen, Daten, Autonomie, Datenschutz, Informationssicherheit, Kosten und technische Machbarkeit werden bewertet.

### 5. Prototyp

Der Agent wird kontrolliert und bevorzugt mit Testdaten erprobt. Ein funktionierender Prototyp ist noch keine Produktionsfreigabe.

### 6. Test

Normal-, Grenz- und Negativfaelle werden nachvollziehbar getestet. Kritische Aktionen und Berechtigungen erhalten eigene Tests.

### 7. Freigabe

Fachliche und technische Verantwortung muessen vor Produktivsetzung geklaert sein. Die Freigabe wird dokumentiert.

### 8. Produktivbetrieb

Der Agent wird unter definierten Berechtigungen, Protokollierung und Monitoring betrieben.

### 9. Review

Agent, Wissensquellen, Berechtigungen, Aktionen und Kosten werden regelmaessig auf Aktualitaet und Notwendigkeit geprueft.

### 10. Aenderung

Wesentliche Aenderungen an Wissen, Tools, Berechtigungen, Autonomie oder Prozessverhalten koennen eine erneute Test- oder Freigabephase ausloesen.

### 11. Abschaltung

Bei Wegfall des Zwecks, unvertretbarem Risiko oder Ersatz durch eine andere Loesung wird der Agent kontrolliert deaktiviert.

### 12. Archivierung

Nachweise, Spezifikation, Freigaben und relevante Betriebsinformationen werden entsprechend den DWD-Aufbewahrungsregeln behandelt.

## DWD-Grundsatz

**Kein direkter Sprung vom Prototyp in den Produktivbetrieb.**

Der Lifecycle muss nachvollziehbar bleiben, insbesondere bei Agents mit schreibenden oder autonomen Aktionen.
