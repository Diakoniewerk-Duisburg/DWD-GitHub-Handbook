# Konzept – DWD Beschaffungsagent

## 1. Zweck

Der DWD Beschaffungsagent unterstützt Mitarbeitende bei der Vorbereitung, Prüfung und kontrollierten Durchführung von Beschaffungsvorgängen. Er verbindet fachliches Beschaffungswissen, strukturierte Vorgangsdaten und definierte Prozessaktionen.

Der Agent ersetzt keine menschliche Genehmigungs- oder Finanzentscheidung.

## 2. Zielbild

```text
Mitarbeiter
    ↓
Beschaffungsagent
    ├─ Bedarf verstehen
    ├─ Rückfragen stellen
    ├─ Vollständigkeit prüfen
    ├─ Regeln anwenden
    ├─ Antrag vorbereiten
    ├─ Genehmiger ermitteln
    └─ Status erklären
    ↓
SharePoint / Dataverse / Lists
    ↓
Power Automate
    ↓
Menschliche Genehmigung
    ↓
Bestellung / Folgeprozess
    ↓
Abschluss und Audit
```

## 3. Fachlicher Umfang

### Im Umfang

- Aufnahme eines Beschaffungsbedarfs in natürlicher Sprache
- Ermittlung fehlender Angaben
- Strukturierung des Beschaffungsvorgangs
- Prüfung gegen freigegebene Beschaffungsregeln
- Plausibilitäts- und Vollständigkeitsprüfung
- Ermittlung der erforderlichen Genehmigungsstufe
- Vorbereitung eines Genehmigungsvorgangs
- Start definierter Workflows
- Statusauskunft zum Vorgang
- nachvollziehbare Protokollierung von Agentenaktionen

### Nicht im Umfang

- eigenständige Genehmigung
- Umgehung von Wertgrenzen oder Zuständigkeiten
- eigenständige Budgetentscheidung
- eigenständige Änderung von Berechtigungen
- freie Auswahl oder Bevorzugung von Lieferanten
- verbindliche Bestellung ohne ausdrücklich freigegebenen Prozess
- autonome irreversible Aktionen

## 4. Zielarchitektur

Der MVP wird als kontrollierter Agent mit klar getrennten Wissens-, Daten- und Aktionsschichten konzipiert.

### Wissensschicht

- Beschaffungsrichtlinien
- Genehmigungsregeln
- Zuständigkeiten und Stellvertretungen
- freigegebene Formulare und Prozessbeschreibungen
- Lieferanten- und Vertragsinformationen, soweit fachlich erforderlich

### Datenebene

Der Beschaffungsvorgang wird strukturiert gespeichert. Mindestfelder:

- RequestId
- Status
- Antragsteller
- Organisationseinheit
- Kostenstelle
- Kategorie
- Beschreibung
- Menge
- Begründung
- gewünschter Termin
- geschätzte Kosten
- Lieferant / Angebot, soweit vorhanden
- Genehmigungsstufe
- Genehmiger
- Genehmigungsstatus
- Bestellstatus
- Auditinformationen

### Aktionsschicht

Read-Aktionen und Write-Aktionen werden getrennt betrachtet.

**Lesen:**

- Beschaffungsregeln abrufen
- Kostenstelle prüfen
- Budgetinformationen lesen, soweit zulässig
- Zuständigkeit und Genehmigungsmatrix ermitteln
- Vorgangsstatus lesen

**Vorbereiten:**

- Beschaffungsantrag erstellen
- Antrag validieren
- Genehmigung vorbereiten
- Vergleichsübersicht vorbereiten

**Prozessaktionen:**

- Genehmigungsworkflow starten
- Benachrichtigung auslösen
- Vorgangsstatus ändern
- nach Freigabe einen definierten Folgeprozess anstoßen

Jede schreibende oder folgenreiche Aktion benötigt eine explizite fachliche und technische Freigabe.

## 5. Prozessmodell

```text
BEDARF_ERFASST
      ↓
DATEN_ERGAENZEN
      ↓
VOLLSTAENDIGKEIT_PRUEFEN
      ↓
FACHLICH_PRUEFEN
      ↓
GENEHMIGUNGSSTUFE_ERMITTELN
      ↓
GENEHMIGUNG_AUSSTEHEND
      ↓
   ┌──┴───────┐
   ↓          ↓
ABGELEHNT   GENEHMIGT
              ↓
       FOLGEPROZESS
              ↓
          ABGESCHLOSSEN
```

Zusätzliche Zustände sind für `ENTWURF`, `RUECKFRAGE`, `FEHLER`, `PAUSIERT` und `STORNIERT` vorzusehen.

## 6. Human-in-the-Loop

Der Agent stoppt vor jeder Entscheidung, die eine verbindliche finanzielle, organisatorische oder rechtliche Wirkung erzeugt, sofern diese Entscheidung nicht ausdrücklich als kontrollierte Agentenaktion freigegeben wurde.

Der Mensch erhält:

- den vollständigen relevanten Sachverhalt
- erkannte fehlende oder widersprüchliche Angaben
- angewendete Regeln
- Kosten- und Budgetinformationen, soweit berechtigt
- vorgeschlagene nächste Aktion
- Risiken und Unsicherheiten

Ablehnung, Rückfrage und Timeout werden als Prozesszustand protokolliert.

## 7. Sicherheits- und Governance-Modell

Zielbewertung des MVP: **A2 – Kontrolliert / R2+ – Prozessbezogen bis erhöhtes Risiko**.

Die konkrete Risikoklasse wird je Vorgang bzw. Anwendungsfall abschließend bewertet.

Grundsätze:

- Least Privilege
- keine implizite Rechteausweitung
- Trennung von Lesen und Schreiben
- keine Selbstgenehmigung
- keine Umgehung von Genehmigungsgrenzen
- personenbezogene Daten nur im erforderlichen Umfang
- nachvollziehbare Agenten- und Prozessaktionen
- kontrolliertes Fehler- und Abbruchverhalten

## 8. MVP-Abgrenzung

Der erste Prototyp umfasst sechs Fähigkeiten:

1. Bedarf aufnehmen
2. fehlende Angaben ermitteln
3. Beschaffungsregeln prüfen
4. strukturierten Antrag erzeugen
5. Genehmigungsworkflow vorbereiten bzw. starten
6. Vorgangsstatus erklären

Eine verbindliche Bestellung ist **nicht Bestandteil des ersten MVP**.

## 9. Technische Ausbaustufen

### Stufe 1 – Prototyp

Agent Builder bzw. geeignete M365-Copilot-Erweiterung mit freigegebenem Beschaffungswissen. Schwerpunkt: Dialog, Wissen und Prüfung.

### Stufe 2 – Prozessagent

Copilot Studio mit strukturierten Aktionen und Power-Automate-Workflows.

### Stufe 3 – Systemintegration

Anbindung weiterer Systeme wie ERP oder Lieferanten-/Bestellsysteme nach separater Architektur-, Datenschutz- und Sicherheitsprüfung.

## 10. Erfolgsbedingungen

Der Agent gilt fachlich erst dann als belastbarer MVP, wenn:

- die Beschaffungsregeln eindeutig vorliegen
- Zuständigkeiten und Genehmigungsgrenzen geklärt sind
- die Datenstruktur freigegeben ist
- Wissensquellen eindeutig als fachliche Primärquellen definiert sind
- Aktionen und Berechtigungen getrennt beschrieben sind
- Negativ- und Berechtigungstests durchgeführt wurden
- Human-in-the-Loop umgesetzt ist
- Audit und Fehlerbehandlung nachgewiesen sind

## 11. Verwandte DWD-Dokumente

- `DWD_Anwendungsfaelle/02_Beschaffungsagent.md`
- `Agents/Agenten_Spezifikation.md`
- `Agents/Agenten_Lifecycle.md`
- `Agents/Autonomiestufen.md`
- `Agents/Connectoren_und_Aktionen.md`
- `Agents/Testing_und_Debugging.md`
- `Governance/Risiko_und_Schutzklassen.md`
- `Governance/Freigabeprozess.md`
- `Governance/Berechtigungsmodell.md`
- `Patterns/Human_in_the_Loop.md`
