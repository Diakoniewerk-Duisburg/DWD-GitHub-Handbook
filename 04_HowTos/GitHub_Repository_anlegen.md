# GitHub Repository anlegen

## Ziel

Dieses HowTo beschreibt, wie ein neues Repository auf GitHub angelegt wird.

Es ist besonders relevant, wenn ein neues Projekt erstmals auf GitHub bereitgestellt werden soll.

## Voraussetzungen

- GitHub-Account
- Berechtigung zum Erstellen eines Repositorys im gewünschten Account oder in der Organisation
- gewünschter Repository-Name
- Entscheidung über die Sichtbarkeit: `public` oder `private`

## 1. GitHub öffnen

GitHub öffnen und anmelden.

Danach die Funktion zum Erstellen eines neuen Repositorys aufrufen.

## 2. Repository-Namen festlegen

Einen eindeutigen und verständlichen Namen vergeben.

Beispiel:

```text
DWD-GitHub-Handbook
```

Der Repository-Name sollte:

- eindeutig sein,
- zum Projekt passen,
- langfristig verständlich bleiben,
- keine unnötigen Sonderzeichen enthalten.

## 3. Besitzer auswählen

Das Repository kann je nach Berechtigung im persönlichen GitHub-Account oder in einer Organisation angelegt werden.

Für ein Organisationsprojekt ist darauf zu achten, dass die Organisation als Besitzer ausgewählt wird.

## 4. Sichtbarkeit festlegen

Entscheiden:

- **Public:** Das Repository und seine Inhalte sind öffentlich sichtbar.
- **Private:** Das Repository ist nur für berechtigte Personen sichtbar.

Die Wahl muss zum Inhalt des Repositorys passen.

## 5. Repository initialisieren oder leer anlegen?

Hier ist zwischen zwei typischen Situationen zu unterscheiden.

### Neues Projekt ohne lokales Repository

Das Repository kann beispielsweise mit einer README initialisiert werden.

Zusätzliche Dateien wie `.gitignore` oder eine Lizenz können bei Bedarf ebenfalls angelegt werden.

### Bereits vorhandenes lokales Git-Repository

Wenn lokal bereits eine vollständige Git-Historie existiert, sollte das GitHub-Repository für die erstmalige Übertragung möglichst leer angelegt werden.

Das bedeutet insbesondere:

- keine zusätzliche README,
- keine zusätzliche `.gitignore`,
- keine zusätzliche Lizenz,

sofern diese nicht bewusst benötigt werden.

Damit wird vermieden, dass lokale und entfernte Historien unnötig auseinanderlaufen.

## 6. Repository erstellen

Repository mit den gewählten Einstellungen erstellen.

Anschließend sollte die erzeugte Repository-URL geprüft werden.

Beispiel:

```text
https://github.com/Benutzername/Mein-Projekt
```

Für Git wird typischerweise die Clone-URL verwendet:

```text
https://github.com/Benutzername/Mein-Projekt.git
```

## 7. Kontrolle

Nach dem Erstellen prüfen:

- richtiger Besitzer
- richtiger Repository-Name
- richtige Sichtbarkeit
- richtige URL
- erwarteter Branch, normalerweise `main`
- Repository-Inhalt entsprechend der gewählten Initialisierung

## 8. Nächster Schritt

### Lokales Repository vorhanden

Weiter mit:

[Lokales Repository nach GitHub übertragen](Lokales_Repository_nach_GitHub_uebertragen.md)

### GitHub Repository soll lokal verwendet werden

Weiter mit:

[Repository klonen](../03_Arbeitsweise/Repository_klonen.md)

## Typische Fehler

### Repository versehentlich initialisiert

Wenn lokal bereits eine eigene Git-Historie vorhanden ist und GitHub zusätzlich mit einem Commit initialisiert wurde, können zwei unabhängige Historien entstehen.

In diesem Fall nicht blind mit `git push --force` arbeiten. Zuerst die beiden Zustände prüfen.

### Falscher Besitzer

Bei Organisationsprojekten prüfen, ob das Repository tatsächlich unter der vorgesehenen Organisation angelegt wurde.

### Falsche Sichtbarkeit

Vor der Veröffentlichung prüfen, ob das Repository vertrauliche Informationen enthält. Ein öffentliches Repository darf keine Passwörter, Tokens, privaten Schlüssel oder andere vertrauliche Daten enthalten.

## Erfolgreicher Endzustand

Das GitHub Repository existiert unter dem richtigen Besitzer, mit dem richtigen Namen und der gewünschten Sichtbarkeit.

Bei einem bestehenden lokalen Repository ist das Ziel ein leeres GitHub-Repository, das anschließend über das HowTo zur Repository-Übertragung mit der lokalen Historie verbunden wird.
