# Agentenspezifikation – DWD Beschaffungsagent v1.0

**Version:** 1.0  
**Status:** Entwurf – technische Umsetzung noch nicht freigegeben  
**Autonomiestufe:** A2 – Kontrolliert  
**Ziel-Risikoklasse:** R2+  
**Primärer Anwendungsfall:** Beschaffung  

> Diese Spezifikation definiert den fachlichen und technischen Zielzustand für einen ersten DWD-Beschaffungsagenten. Sie ist keine Produktivfreigabe.

## 1. Stammdaten

| Feld | Festlegung |
|---|---|
| Agentname | DWD Beschaffungsagent |
| Zweck | Unterstützung bei Aufnahme, Prüfung, Vorbereitung und kontrollierter Prozesssteuerung von Beschaffungsvorgängen |
| Fachlicher Owner | Noch festzulegen |
| Technischer Owner | Noch festzulegen |
| Zielgruppe | Berechtigte DWD-Mitarbeitende und definierte Rollen im Beschaffungsprozess |
| Status | Entwurf |
| Version | 1.0 |
| Autonomie | A2 – Kontrolliert |
| Risikoklasse | R2+ als vorläufige Zielbewertung |

## 2. Fachliche Definition

### 2.1 Ausgangssituation

Beschaffungsbedarfe entstehen häufig als Freitext und müssen anschließend hinsichtlich Vollständigkeit, Zuständigkeit, Regeln, Kosten und Genehmigung aufbereitet werden. Der Agent soll diese Vorarbeiten standardisieren und den Prozess nachvollziehbarer machen.

### 2.2 Ziel

Der Agent soll aus einem natürlich formulierten Bedarf einen strukturierten und prüfbaren Beschaffungsvorgang erzeugen und diesen kontrolliert bis zur menschlichen Genehmigung begleiten.

### 2.3 Nutzen

- weniger Rückfragen
- höhere Vollständigkeit der Anträge
- einheitliche Anwendung freigegebener Beschaffungsregeln
- schnellere Zuordnung von Zuständigkeiten
- transparenter Vorgangsstatus
- nachvollziehbare Prozess- und Agentenaktionen

### 2.4 Eingaben

- freier Bedarfstext
- Antragsteller
- Organisationseinheit
- Kostenstelle
- Produkt oder Leistung
- Menge
- Begründung
- gewünschter Termin
- geschätzte Kosten
- Lieferanten-/Angebotsinformationen, soweit vorhanden

Der Agent darf fehlende Pflichtinformationen nicht erfinden.

### 2.5 Ergebnisse

- strukturierter Beschaffungsvorgang
- Liste fehlender Angaben
- Prüfergebnis
- angewendete relevante Regeln
- ermittelte Genehmigungsstufe
- vorbereiteter Genehmigungsvorgang
- Status und nächste erforderliche Aktion

## 3. Fachliche Regeln

1. Der Agent verwendet ausschließlich freigegebene Beschaffungsregeln.
2. Bei fehlenden Pflichtangaben fragt der Agent nach.
3. Bei widersprüchlichen Daten stoppt der Agent und fordert Klärung an.
4. Genehmigungsgrenzen dürfen nicht umgangen werden.
5. Der Antragsteller darf seinen eigenen Vorgang nicht selbst genehmigen.
6. Der Agent darf eine menschliche Genehmigung nicht simulieren.
7. Finanzielle oder sonstige verbindliche Entscheidungen bleiben bei der dafür autorisierten Stelle.
8. Nicht eindeutig bewertbare Vorgänge werden eskaliert.

## 4. Wissen und Daten

### 4.1 Primäre Wissensquellen

Für den Produktivbetrieb sind verbindliche fachliche Primärquellen festzulegen. Vorgesehen sind:

- Beschaffungsrichtlinie
- Genehmigungs- und Vollmachtsregelungen
- freigegebene Prozessbeschreibung
- Zuständigkeits- und Stellvertretungsregelungen
- freigegebene Formulare und Vorlagen

### 4.2 Weitere Wissensquellen

- Lieferantenstamm
- Vertrags- und Rahmenvertragsinformationen
- Kostenstelleninformationen
- freigegebene Produkt-/Leistungskataloge
- relevante DWD-Prozessdokumentation

### 4.3 Datenmodell

Der Vorgang muss mindestens folgende Daten führen:

```text
RequestId
Status
CreatedAt
CreatedBy
Applicant
OrganizationUnit
CostCenter
Category
Description
Quantity
Priority
Justification
RequestedDate
EstimatedCost
BudgetReference
Supplier
OfferReference
ApprovalLevel
Approver
ApprovalStatus
ApprovalDate
OrderStatus
OrderReference
LastAction
LastActionAt
AuditReference
```

### 4.4 Quellenpriorität

Bei Widersprüchen gilt die fachlich verbindliche Primärquelle. Der Agent darf widersprüchliche Aussagen nicht eigenständig harmonisieren, wenn dadurch eine fachliche Entscheidung entstehen würde.

## 5. Tools und Aktionen

### 5.1 Lesende Aktionen

- `GetProcurementRules`
- `GetCostCenter`
- `GetBudgetInformation`
- `GetApprovalMatrix`
- `GetSupplierInformation`
- `GetRequestStatus`

### 5.2 Vorbereitende Aktionen

- `CreateProcurementRequest`
- `ValidateProcurementRequest`
- `PrepareApproval`
- `PrepareComparison`

### 5.3 Prozessaktionen

- `StartApproval`
- `SendNotification`
- `UpdateRequestStatus`
- `CreateOrderRequest` – erst nach separater Freigabe für die jeweilige Prozessstufe

### 5.4 Nicht erlaubte Aktionen

- Genehmigung selbst erteilen
- Genehmigungsgrenzen ändern
- Berechtigungen ändern
- Budgetwerte verändern
- Lieferantenregeln umgehen
- eigene Genehmigung auslösen
- irreversible Bestellung ohne freigegebenen Prozess durchführen
- Daten außerhalb des erlaubten Zwecks abrufen

## 6. Technische Zielarchitektur

```text
Microsoft 365 Copilot / geeignete Copilot-Oberfläche
                    ↓
             DWD Beschaffungsagent
          ┌─────────┼──────────┐
          ↓         ↓          ↓
       Wissen     Vorgang    Aktionen
          ↓         ↓          ↓
     SharePoint   List/       Power
     / freige-    Dataverse   Automate
     gebene       Daten       Workflows
     Quellen
                    ↓
            menschliche Freigabe
                    ↓
              Folgeprozess
```

Für den MVP wird eine möglichst einfache und kontrollierbare Architektur bevorzugt. Erweiterungen um ERP, externe APIs, MCP oder weitere Systeme erfolgen erst nach separater Prüfung.

## 7. Identität und Berechtigungen

Es gelten folgende Ebenen:

1. Benutzerberechtigung
2. Agentenberechtigung
3. Toolberechtigung
4. Aktionsberechtigung
5. Genehmigungsberechtigung

Der Agent erhält nur die für den Anwendungsfall erforderlichen Rechte. Lesen und Schreiben werden soweit technisch möglich getrennt. Eine technische Möglichkeit zum Aufruf einer Aktion stellt keine fachliche Freigabe dieser Aktion dar.

## 8. Autonomie

Der Agent wird mit **A2 – Kontrolliert** betrieben.

Das bedeutet:

- Informationen und Vorschläge können selbstständig erzeugt werden.
- definierte nichtkritische Prozessaktionen können kontrolliert ausgeführt werden.
- folgenreiche Aktionen benötigen eine definierte menschliche Bestätigung oder eine bereits freigegebene Prozessregel.
- Genehmigungsentscheidungen bleiben menschlich.

A3 ist für Version 1.0 nicht vorgesehen.

## 9. Human-in-the-Loop

Der Agent stoppt mindestens vor:

- verbindlicher finanzieller Entscheidung
- Genehmigung eines eigenen Vorgangs
- Überschreitung definierter Wert- oder Berechtigungsgrenzen
- nicht eindeutig bewertbaren Vorgängen
- irreversiblen oder wirtschaftlich wesentlichen Aktionen

Der Genehmiger erhält mindestens:

- Antragsteller
- Bedarf
- Begründung
- Kosten
- Kostenstelle
- relevante Regel-/Prüfergebnisse
- Lieferanten-/Angebotsinformationen, soweit relevant
- Risiken und offene Punkte
- Entscheidungsmöglichkeiten

Entscheidungen werden mit Zeitpunkt, Rolle und Ergebnis protokolliert.

## 10. Dialog- und Verhaltensregeln

Der Agent soll:

- kurz und sachlich kommunizieren
- fehlende Informationen gezielt erfragen
- Annahmen ausdrücklich kennzeichnen
- Quellen bzw. Regelgrundlagen nachvollziehbar nennen, soweit verfügbar
- Unsicherheit offenlegen
- keine Entscheidung als bereits erfolgt darstellen, wenn sie nur vorbereitet wurde
- vor folgenreichen Aktionen den aktuellen Zustand bestätigen

Beispiel:

> Der Beschaffungsantrag ist vollständig vorbereitet. Eine Genehmigung steht noch aus. Es wurde noch keine Bestellung ausgelöst.

## 11. Fehler- und Ausnahmebehandlung

### Fehlende Daten

Status `RUECKFRAGE`; keine Folgeaktion mit fachlicher Wirkung.

### Widersprüchliche Daten

Status `PAUSIERT`; Eskalation an definierte fachliche Stelle.

### Fehlende Berechtigung

Aktion abbrechen und Berechtigungsproblem melden. Kein Versuch einer Rechteausweitung.

### Tool-/Connectorfehler

Aktion abbrechen, Fehler protokollieren und Vorgang in einen kontrollierten Fehlerzustand setzen.

### Unsichere Agentenantwort

Keine verbindliche Aktion. Rückfrage oder Eskalation.

### Manipulierte Inhalte / Prompt Injection

Nicht vertrauenswürdige Anweisungen aus Wissensquellen dürfen keine System- oder Sicherheitsregeln überschreiben. Verdächtige Inhalte werden nicht als autorisierte Handlungsanweisung behandelt.

## 12. Vorgangsstatus

```text
ENTWURF
  ↓
RUECKFRAGE
  ↓
PRUEFUNG
  ↓
GENEHMIGUNG_AUSSTEHEND
  ↓
GENEHMIGT / ABGELEHNT
  ↓
FOLGEPROZESS
  ↓
ABGESCHLOSSEN
```

Zusätzliche Zustände:

- `PAUSIERT`
- `FEHLER`
- `STORNIERT`

Der Status muss aus strukturierten Prozessdaten ableitbar sein und darf nicht ausschließlich aus dem Chatverlauf rekonstruiert werden.

## 13. Test und Qualität

Vor einer Produktivfreigabe sind mindestens folgende Testklassen erforderlich:

| Testklasse | Beispiel |
|---|---|
| Normalfall | vollständiger Standardbedarf |
| Unvollständig | fehlende Kostenstelle |
| Widerspruch | widersprüchliche Kostenangaben |
| Berechtigung | Benutzer ohne erforderliche Berechtigung |
| Genehmigung | korrekte Genehmigungsstufe |
| Selbstgenehmigung | Antragsteller ist Genehmiger |
| Grenzwert | Wert knapp unter/über Genehmigungsgrenze |
| Toolfehler | Workflow/Connector nicht erreichbar |
| Unsicherheit | Regel nicht eindeutig |
| Schreibaktion | nicht freigegebene Aktion wird angefordert |
| Prompt Injection | manipulierte Wissensquelle |
| Datenschutz | Zugriff auf nicht benötigte Personendaten |
| Regression | bestehende Szenarien nach Änderung |

## 14. Datenschutz und Sicherheit

Vor Produktivbetrieb erforderlich:

- Zweckbestimmung
- Prüfung personenbezogener Daten
- Datenminimierung
- Berechtigungsprüfung
- Prüfung der Wissensquellen
- Prüfung externer Dienste und Connectoren
- Aufbewahrung und Löschung
- Logging und Audit
- Bewertung von Prompt Injection und Datenabfluss
- Prüfung der Rollen und Verantwortlichkeiten

## 15. Governance und Betrieb

Erforderlich sind:

- fachlicher Owner
- technischer Owner
- dokumentierte Version
- dokumentierte Wissensquellen
- dokumentierte Tools/Aktionen
- dokumentierte Berechtigungen
- Testnachweis
- Freigaben
- Monitoring
- Änderungsprozess
- regelmäßiges Review
- kontrolliertes Abschaltverfahren

## 16. MVP-Freigabegrenze

Version 1.0 umfasst ausschließlich:

1. Bedarf aufnehmen
2. fehlende Angaben ermitteln
3. Beschaffungsregeln prüfen
4. Antrag strukturiert erzeugen
5. Genehmigungsworkflow vorbereiten bzw. starten
6. Status erklären

Eine verbindliche Bestellung ist **nicht Bestandteil des MVP**.

## 17. Freigabekriterien

Produktivfreigabe erst nach Nachweis von:

- fachlich freigegebenen Beschaffungsregeln
- geklärten Genehmigungsgrenzen
- definierten Verantwortlichkeiten
- freigegebenem Datenmodell
- geprüften Wissensquellen
- geprüften Berechtigungen
- dokumentierten Aktionen
- bestandenen Normal-, Grenz- und Negativtests
- Datenschutz- und Sicherheitsbewertung
- funktionierendem Human-in-the-Loop
- Auditierbarkeit
- Fehler- und Abschaltverfahren

## 18. Offene Entscheidungen für v1.1 / Implementierung

| Thema | Entscheidung |
|---|---|
| Fachlicher Owner | offen |
| Technischer Owner | offen |
| führendes Vorgangssystem | SharePoint List oder Dataverse zu entscheiden |
| führendes Beschaffungssystem/ERP | zu klären |
| konkrete Wertgrenzen | fachlich zu liefern |
| Genehmigungsmatrix | fachlich zu liefern |
| Kostenstellenquelle | technisch/fachlich zu klären |
| Lieferantenquelle | technisch/fachlich zu klären |
| konkrete Connectoren | Architekturentscheidung erforderlich |
| produktive Bestellaktion | außerhalb MVP, separate Freigabe |

## Verwandte Dokumente

- `02_Beschaffungsagent.md`
- `Beschaffungsagent_Konzept.md`
- `../Agents/Agenten_Spezifikation.md`
- `../Agents/Agenten_Lifecycle.md`
- `../Agents/Autonomiestufen.md`
- `../Agents/Connectoren_und_Aktionen.md`
- `../Agents/Testing_und_Debugging.md`
- `../Governance/Risiko_und_Schutzklassen.md`
- `../Governance/Freigabeprozess.md`
- `../Governance/Berechtigungsmodell.md`
- `../Patterns/Human_in_the_Loop.md`
