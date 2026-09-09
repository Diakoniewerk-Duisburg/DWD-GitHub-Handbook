# Autonomiestufen – DWD-Standard

## Zweck

Die Autonomiestufe beschreibt, wie selbststaendig ein Agent handeln darf. Sie ist ein Governance-Merkmal und keine Aussage ueber die technische Leistungsfaehigkeit eines Modells.

| Stufe | Bezeichnung | Verhalten | DWD-Einsatz |
|---|---|---|---|
| A0 | Informativ | Antworten und Informationen | Standard fuer Wissens- und Auskunftsszenarien |
| A1 | Assistiv | Vorschlaege, Entwuerfe, vorbereitete Ergebnisse | bevorzugt fuer fachliche Vorbereitung |
| A2 | Kontrolliert | Aktion nach expliziter menschlicher Bestaetigung | geeignet fuer folgenreiche Aktionen |
| A3 | Autonom | definierte Aktion ohne Einzelbestaetigung | nur bei klar begrenztem, risikoarmem Verhalten |

## Entscheidungsregeln

- Die niedrigste ausreichende Autonomiestufe ist zu verwenden.
- Schreibende Aktionen sind mindestens A2 zu bewerten, sofern keine begruendete A3-Freigabe besteht.
- Berechtigungen und Autonomie werden getrennt bewertet.
- A3 setzt definierte Grenzen, Fehlerbehandlung, Monitoring und Rueckfallmechanismen voraus.
- Eine hohe Modellleistung ist kein Grund fuer eine hoehere Autonomiestufe.

## Typische Beispiele

### A0

Agent beantwortet eine Frage auf Basis freigegebener SharePoint-Inhalte.

### A1

Agent erstellt einen Entwurf fuer einen Beschaffungsantrag, der von einem Mitarbeiter geprueft wird.

### A2

Agent bereitet eine Aktion vor und fuehrt sie erst nach Bestaetigung durch den berechtigten Benutzer aus.

### A3

Agent verarbeitet einen eindeutig definierten, risikoarmen Routinevorgang selbststaendig und protokolliert das Ergebnis.

## Freigabe

Die Autonomiestufe muss Bestandteil der Agenten-Spezifikation sein. Eine Erhoehung von A0/A1 nach A2/A3 ist als wesentliche Aenderung zu behandeln und erfordert eine erneute Bewertung.
