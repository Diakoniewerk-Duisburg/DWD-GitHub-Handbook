# Testing und Debugging

## Grundsatz

Agenten werden wie technische Systeme getestet, aber nicht ausschliesslich technisch. Neben Funktion und Schnittstellen muessen Wissen, Berechtigungen, Verhalten bei Unsicherheit und Nebenwirkungen geprueft werden.

## Testebenen

1. **Konfigurationstest** – Agent, Wissen, Tools und Einstellungen sind korrekt.
2. **Funktionstest** – erwartete Aufgaben werden korrekt ausgefuehrt.
3. **Negativtest** – unzulaessige oder nicht unterstuetzte Anfragen werden sicher behandelt.
4. **Berechtigungstest** – der Agent kann nur auf freigegebene Daten und Aktionen zugreifen.
5. **Wissenstest** – Antworten sind anhand der vorgesehenen Quellen nachvollziehbar.
6. **Aktions-Test** – schreibende Aktionen werden mit kontrollierten Testdaten ausgefuehrt.
7. **Fehler- und Abbruchtest** – Timeouts, unvollstaendige Daten und Toolfehler fuehren zu einem sicheren Zustand.
8. **Regressionstest** – Aenderungen duerfen bereits freigegebene Funktionen nicht unbemerkt verschlechtern.

## Testfaelle

Jeder produktive Agent sollte mindestens folgende Faelle besitzen:

| Fall | Erwartung |
|---|---|
| Normalfall | Aufgabe wird korrekt geloest. |
| Fehlende Information | Agent fragt nach oder verweigert sicher. |
| Unzulaessige Anfrage | Keine unberechtigte Aktion. |
| Fehlendes Recht | Zugriff wird sauber abgelehnt. |
| Toolfehler | Kein unkontrollierter Folgeprozess. |
| Unsichere Antwort | Unsicherheit wird kenntlich gemacht. |
| Schreibaktion | Nur nach definierter Freigabe und mit Protokollierung. |

## Debugging

Bei Fehlverhalten zuerst die Kette pruefen:

**Eingabe -> Agentenanweisung -> Wissensquelle -> Orchestrierung -> Tool/Connector -> Zielsystem -> Ergebnis**

Dabei ist zu unterscheiden, ob die Ursache fachlich, datenbezogen, konfigurationsbedingt, berechtigungsbezogen oder technisch ist.

## Freigabe

Ein Agent gilt erst als produktionsreif, wenn die definierten Testfaelle bestanden, offene Risiken bewertet und die erforderlichen fachlichen und technischen Freigaben dokumentiert sind.

## Verwandte Dokumente

- [Agenten-Spezifikation](Agenten_Spezifikation.md)
- [Agenten-Lifecycle](Agenten_Lifecycle.md)
- [Connectoren und Aktionen](Connectoren_und_Aktionen.md)
- [Umgebungen und ALM](Umgebungen_und_ALM.md)
