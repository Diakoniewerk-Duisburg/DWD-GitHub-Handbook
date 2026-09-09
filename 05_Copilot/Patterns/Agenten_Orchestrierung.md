# Pattern: Agenten-Orchestrierung

## Zweck

Mehrere spezialisierte Agents koennen gemeinsam einen fachlichen Vorgang bearbeiten. Jeder Agent bleibt fuer eine klar abgegrenzte Aufgabe verantwortlich.

```text
Benutzer / Copilot
        |
        v
   Orchestrierung
    /    |    \
   v     v     v
Wissen  Fach   Aktion
Agent   Agent  Agent
        |
        v
     Ergebnis
```

## Grundregeln

- Aufgaben werden nach fachlicher Verantwortung getrennt.
- Ein Agent soll nur die fuer seine Aufgabe erforderlichen Daten und Aktionen erhalten.
- Berechtigungen werden pro Agent und Tool bewertet.
- Der Orchestrator darf keine implizite Berechtigungserweiterung erzeugen.
- Ergebnisse spezialisierter Agents muessen fuer den naechsten Verarbeitungsschritt nachvollziehbar sein.
- Kritische Entscheidungen koennen an Human-in-the-Loop uebergeben werden.

## Beispiel DWD

Ein kuenftiger Beschaffungsvorgang koennte Recherche, fachliche Pruefung und Genehmigung durch getrennte Komponenten unterstuetzen. Welche Komponenten tatsaechlich als Agents umgesetzt werden, wird erst anhand des konkreten Prozesses entschieden.

## Anti-Pattern

Ein einzelner Agent mit uneingeschraenktem Zugriff auf alle DWD-Daten, Connectoren und Aktionen ist zu vermeiden.
