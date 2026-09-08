# Checklisten

Dieser Bereich enthält kurze Checklisten für wiederkehrende Git- und GitHub-Aufgaben.

Die Checklisten sind für die praktische Durchführung gedacht.

Sie ersetzen keine ausführlichen HowTos.

## Verfügbare Checklisten

### Repository anlegen

[Repository anlegen](Repository_anlegen.md)

Für die Erstellung eines neuen GitHub-Repositorys.

---

### Repository übertragen

[Repository übertragen](Repository_uebertragen.md)

Für die Übertragung eines bereits vorhandenen lokalen Repositorys nach GitHub.

---

### Repository synchronisieren

[Repository synchronisieren](Repository_synchronisieren.md)

Für den regelmäßigen Abgleich zwischen lokalem Repository und GitHub.

---

# Standardprüfung

Unabhängig von der konkreten Aufgabe sind folgende Prüfungen besonders wichtig:

```powershell id="2u4j8g"
git status
git branch --show-current
git remote -v
```

Damit wird festgestellt:

- Zustand des Repositorys
- aktueller Branch
- konfiguriertes Remote

## Vor einem Commit

```text id="c5o8i2"
[ ] Richtige Dateien geändert
[ ] Keine unnötigen Dateien enthalten
[ ] Keine Secrets enthalten
[ ] Keine vertraulichen Daten enthalten
[ ] git status geprüft
[ ] git diff geprüft
[ ] git diff --staged geprüft
[ ] Commit-Nachricht sinnvoll
```

## Vor einem Push

```text id="xq6v1b"
[ ] Richtiger Branch
[ ] Richtiges Remote
[ ] Commit geprüft
[ ] Keine Secrets enthalten
[ ] Keine unerwarteten Dateien enthalten
[ ] Push bewusst durchgeführt
```

## Nach einem Push

```text id="m2d8qk"
[ ] git status geprüft
[ ] GitHub Repository geöffnet
[ ] Dateien kontrolliert
[ ] Branch kontrolliert
[ ] Commit-Historie kontrolliert
```

## Merksatz

> **Prüfen → Ändern → Prüfen → Commit → Prüfen → Push → Kontrollieren**