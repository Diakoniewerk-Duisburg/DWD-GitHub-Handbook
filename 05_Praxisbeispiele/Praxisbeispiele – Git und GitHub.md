# Praxisbeispiele

Dieser Bereich beschreibt typische Situationen aus der praktischen Arbeit mit Git und GitHub.

Während die Befehlsreferenz einzelne Befehle erklärt und die HowTos vollständige Aufgaben beschreiben, zeigen die Praxisbeispiele typische Alltagssituationen.

## Warum Praxisbeispiele?

Git wird wesentlich einfacher, wenn nicht nur einzelne Befehle bekannt sind, sondern der Zusammenhang verstanden wird.

Ein typischer Vorgang besteht beispielsweise aus:

```text
Repository auswählen
      ↓
Status prüfen
      ↓
Änderung durchführen
      ↓
Änderung prüfen
      ↓
Commit erstellen
      ↓
Push
      ↓
Kontrolle
```

Die folgenden Beispiele zeigen solche Situationen anhand konkreter Abläufe.

---

## Praxisbeispiele

### 01 – Lokales Repository nach GitHub übertragen

Ein vorhandenes lokales Repository soll erstmals in ein neues GitHub-Repository übertragen werden.

[Praxisbeispiel öffnen](01_Lokales_Repository_nach_GitHub.md)

---

### 02 – GitHub-Änderung lokal übernehmen

Eine Datei wurde direkt auf GitHub geändert und soll anschließend im lokalen Repository verfügbar sein.

[Praxisbeispiel öffnen](02_GitHub_Aenderung_lokal_uebernehmen.md)

---

### 03 – Lokale Änderung committen und pushen

Eine Änderung wurde lokal durchgeführt und soll sauber nach GitHub übertragen werden.

[Praxisbeispiel öffnen](03_Lokale_Aenderung_committen_und_pushen.md)

---

### 04 – Repository-Zustand prüfen

Ein Repository soll vor einer weiteren Aktion vollständig verstanden und kontrolliert werden.

[Praxisbeispiel öffnen](04_Repository_Stand_pruefen.md)

---

### 05 – Push abgelehnt

Ein Push wird von Git abgelehnt, weil das Remote-Repository Änderungen enthält, die lokal noch nicht vorhanden sind.

[Praxisbeispiel öffnen](05_Push_abgelehnt.md)

---

### 06 – Falsches Remote erkennen

Ein lokales Repository ist mit einem falschen GitHub-Repository verbunden.

[Praxisbeispiel öffnen](06_Falsches_Remote_erkennen.md)

---

### 07 – Mehrere Änderungen sauber committen

Mehrere Dateien wurden geändert und sollen sinnvoll und nachvollziehbar committed werden.

[Praxisbeispiel öffnen](07_Mehrere_Aenderungen_sauber_committen.md)

---

### 08 – Online und lokal parallel arbeiten

Eine Änderung wurde direkt auf GitHub durchgeführt, während lokal ebenfalls weitergearbeitet wurde.

[Praxisbeispiel öffnen](08_Online_und_lokal_arbeiten.md)

---

# Grundprinzip

Bei allen Praxisbeispielen gilt:

> **Nicht der Befehl steht im Mittelpunkt, sondern der Zustand des Repositorys.**

Deshalb beginnt ein Beispiel möglichst mit:

```powershell
git status
```

und endet mit einer Kontrolle.

---

# Beziehung zu den anderen Bereichen

| Bereich | Zweck |
|---|---|
| `01_Grundlagen` | Verständnis |
| `02_GitHub_Online` | Arbeiten im Webinterface |
| `03_Arbeitsweise` | Standardablauf lokal |
| `04_HowTos` | vollständige Aufgaben |
| `05_Praxisbeispiele` | typische Alltagssituationen |
| `07_Befehlsreferenz` | einzelne Befehle |
| `08_Troubleshooting` | Fehleranalyse |
| `09_Sicherheit` | Sicherheitsregeln |
| `11_Checklisten` | kurze operative Prüfung |

Die Bereiche ergänzen sich und sind nicht als Konkurrenz zueinander gedacht.