# Agenten-Spezifikation – DWD-Standard

## Zweck

Jeder eigene DWD-Agent wird vor einer technischen Umsetzung fachlich und technisch nach einem einheitlichen Schema beschrieben. Die Spezifikation ist die verbindliche Grundlage fuer Bewertung, Prototyp, Test, Freigabe und Betrieb.

## 1. Stammdaten

| Feld | Inhalt |
|---|---|
| Agentname | Eindeutiger Name |
| Zweck | Welches konkrete Problem loest der Agent? |
| Fachlicher Owner | Verantwortliche Fachstelle |
| Technischer Owner | Verantwortliche IT / Entwicklung |
| Zielgruppe | Berechtigte Benutzergruppen |
| Status | Idee / Entwurf / Test / Freigegeben / Produktiv / Ausser Betrieb |
|

## 2. Fachliche Definition

- Ausgangssituation
- Ziel und erwarteter Nutzen
- Nicht-Ziele und Grenzen
- Eingaben
- erwartete Ergebnisse
- relevante Prozesse
- fachliche Regeln
- Eskalationsfaelle

## 3. Wissen und Daten

- primaere Wissensquellen
- weitere Wissensquellen
- Datenmodell / Stammdaten
- Aktualisierungsanforderungen
- Quellenprioritaet bei Widerspruechen
- Berechtigungsgrenzen
- Umgang mit nicht verfuegbarem Wissen

## 4. Tools und Aktionen

- Connectoren
- APIs / REST
- MCP
- Workflows
- erlaubte Aktionen
- schreibende Aktionen
- externe Systeme
- technische Fehlerbehandlung

Jede schreibende oder folgenreiche Aktion muss explizit beschrieben und freigegeben werden.

## 5. Identitaet und Berechtigungen

- Benutzeridentitaet / Agentidentitaet
- benoetigte Rollen
- benoetigte Datenberechtigungen
- Least-Privilege-Prinzip
- Trennung von Lesen und Schreiben
- privilegierte Aktionen

Ein Agent darf keine Berechtigungsgrenzen des zugrunde liegenden Systems umgehen.

## 6. Autonomie

Der Agent wird einer Autonomiestufe zugeordnet:

- **A0 – Informativ:** nur Antworten und Informationen
- **A1 – Assistiv:** Vorschlaege, Entwuerfe und vorbereitete Ergebnisse
- **A2 – Kontrolliert:** Aktionen nach menschlicher Bestaetigung
- **A3 – Autonom:** definierte Aktionen ohne Einzelbestaetigung

A3 ist nur fuer klar abgegrenzte, risikoarme und technisch kontrollierbare Aktionen zulaessig.

## 7. Human-in-the-Loop

Falls eine menschliche Entscheidung erforderlich ist, wird definiert:

1. wann der Agent stoppt
2. welche Information der Mensch erhaelt
3. welche Entscheidung getroffen werden muss
4. wer entscheiden darf
5. wie die Entscheidung protokolliert wird
6. was bei Ablehnung oder Timeout geschieht

## 8. Grenzen und Fehlverhalten

Zu dokumentieren sind mindestens:

- nicht beantwortbare Fragen
- fehlende oder widerspruechliche Daten
- unberechtigte Anfragen
- fehlerhafte Tools / Connectoren
- unerlaubte Aktionen
- Prompt-Injection / manipulierte Inhalte
- Eskalationsweg

## 9. Test und Qualitaet

Vor Freigabe muessen Testfaelle fuer Normal-, Grenz- und Negativszenarien vorliegen. Mindestens zu pruefen sind Fachlichkeit, Quellen, Berechtigungen, Aktionen, Fehlerverhalten, Datenschutz und Sicherheit.

## 10. Governance und Betrieb

- Datenschutzbewertung
- Sicherheitsbewertung
- Freigabeinstanzen
- Protokollierung
- Monitoring
- Kosten / Verbrauch
- Review-Intervall
- Aenderungsprozess
- Backup / Wiederherstellung, soweit relevant
- Abschaltverfahren

## 11. Freigabekriterium

Ein Agent gilt erst als produktionsbereit, wenn Zweck, Owner, Zielgruppe, Wissen, Daten, Identitaet, Berechtigungen, Tools, Aktionen, Autonomie, Tests, Governance und Abschaltung dokumentiert und freigegeben sind.

## Verwandte Dokumente

- `Agenten_Lifecycle.md`
- `Autonomiestufen.md`
- `Human_in_the_Loop.md`
- `../Governance/Grundlagen.md`
- `Agenten_Matrix.md`
