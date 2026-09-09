# LF/CRLF-Warnung

## 1. Typische Meldung

Unter Windows kann Git beispielsweise folgende Warnung anzeigen:

```text
warning: in the working copy of 'README.md',
LF will be replaced by CRLF the next time Git touches it
```

## 2. Bedeutung

Die Meldung betrifft unterschiedliche Zeilenenden.

- `LF` = Line Feed
- `CRLF` = Carriage Return + Line Feed

Unix- und Linux-Systeme verwenden typischerweise `LF`.

Windows verwendet häufig `CRLF`.

## 3. Ist das ein Fehler?

Normalerweise nicht.

Die Meldung ist eine **Warnung zur Zeilenendekonvertierung**.

Sie bedeutet nicht automatisch, dass die Datei beschädigt ist.

## 4. Warum tritt die Meldung auf?

Git kann abhängig von der Konfiguration Zeilenenden zwischen Working Tree und Repository unterschiedlich behandeln.

Das ist insbesondere bei gemischten Entwicklungsumgebungen relevant.

## 5. Was sollte man tun?

Nicht automatisch versuchen, jede einzelne Datei wegen dieser Meldung zu verändern.

Zunächst prüfen:

```powershell
git status
```

und die tatsächlichen Änderungen kontrollieren:

```powershell
git diff
```

## 6. Einheitliche Regeln

Bei größeren Projekten sollte die Behandlung von Zeilenenden bewusst über eine `.gitattributes`-Datei geregelt werden.

Beispiel:

```text
* text=auto
```

Eine solche Regel sollte jedoch projektspezifisch festgelegt werden.

## 7. Dokumentation

Bei einem reinen Markdown-Dokumentationsrepository sollte eine einheitliche Zeilenendebehandlung bevorzugt werden.

Die konkrete Einstellung sollte im Repository festgelegt und dokumentiert werden.

## 8. Merksatz

> Eine LF/CRLF-Warnung ist normalerweise kein Git-Fehler, sondern ein Hinweis auf unterschiedliche Zeilenenden.