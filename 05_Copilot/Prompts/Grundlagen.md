# Prompts – Grundlagen

## Zweck

Ein Prompt beschreibt die Aufgabe oder Frage, die an Copilot oder einen Agent gestellt wird. Bei Agents kommen zusaetzlich dauerhafte Anweisungen hinzu, die Verhalten, Rolle, Grenzen und Ziel des Agents definieren.

## Gute Prompts

Ein guter Prompt beschreibt mindestens:

- **Aufgabe:** Was soll getan werden?
- **Kontext:** Welche Informationen sind relevant?
- **Zielgruppe:** Fuer wen ist das Ergebnis bestimmt?
- **Ausgabe:** In welchem Format soll geantwortet werden?
- **Grenzen:** Was soll nicht angenommen oder getan werden?

## Beispiel

Schlecht:

> Erklaere den Beschaffungsprozess.

Besser:

> Erstelle fuer neue Mitarbeitende eine kurze Schritt-fuer-Schritt-Erklaerung des freigegebenen Beschaffungsprozesses. Verwende nur die bereitgestellten Organisationsdokumente. Nenne je Schritt Verantwortlichen, erforderliche Eingabe und erwartetes Ergebnis. Wenn eine Information fehlt, kennzeichne dies ausdruecklich.

## Prompt und Wissensquelle unterscheiden

Ein Prompt ersetzt keine Wissensquelle.

- Der **Prompt** beschreibt, was der Agent tun soll.
- Die **Wissensquelle** liefert den fachlichen Inhalt.
- Ein **Tool** ermoeglicht eine Interaktion mit einem System.

## Prompt-Standard fuer DWD

Prompts fuer produktive Agents sollen nachvollziehbar und wiederverwendbar sein. Fachliche Regeln gehoeren nicht ausschliesslich in einen schwer wartbaren Einzelprompt, sondern moeglichst in freigegebene Dokumentation und Wissensquellen.

## Qualitaetspruefung

Vor produktiver Nutzung sollte ein Prompt mindestens mit folgenden Fragen geprueft werden:

1. Ist die Aufgabe eindeutig?
2. Ist die Zielgruppe bekannt?
3. Sind relevante Quellen definiert?
4. Sind Grenzen und Ausschluesse beschrieben?
5. Ist das gewuenschte Ausgabeformat klar?
6. Wurde das Verhalten mit realistischen und negativen Testfaellen geprueft?

## Hinweis

Prompt Engineering ist nur ein Teil der Agentenqualitaet. Schlechte oder unklare Wissensquellen, unpassende Berechtigungen oder falsch konfigurierte Tools koennen durch einen guten Prompt nicht kompensiert werden.
