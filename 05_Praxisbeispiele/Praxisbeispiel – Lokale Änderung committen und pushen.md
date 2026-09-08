# Praxisbeispiel 03 – Lokale Änderung committen und pushen

## Situation

Im lokalen Repository wurde eine oder mehrere Dateien geändert.

Die Änderungen sollen nachvollziehbar gespeichert und anschließend zu GitHub übertragen werden.

Beispiel:

```text id="q6g3px"
D:\GitHub\Mein-Projekt
        │
        └── README.md geändert
```

---

# 1. Repository öffnen

```powershell id="c6z4pw"
cd "D:\GitHub\Mein-Projekt"
```

---

# 2. Vorhandene Änderungen prüfen

```powershell id="zq3c4e"
git status
```

Beispiel:

```text id="qcz8jm"
modified: README.md
```

Jetzt ist bekannt, dass eine Datei geändert wurde.

---

# 3. Änderung ansehen

```powershell id="1m2xqn"
git diff
```

Hier wird geprüft:

- Was wurde geändert?
- Ist die Änderung beabsichtigt?
- Sind nur die erwarteten Dateien betroffen?
- Wurde versehentlich etwas anderes verändert?

---

# 4. Änderung für den Commit vormerken

Eine einzelne Datei:

```powershell id="h7k2x4"
git add README.md
```

Oder mehrere bewusst ausgewählte Dateien:

```powershell id="zq1g7e"
git add Datei1.md Datei2.md
```

Bei einem größeren, bewusst geprüften Änderungsumfang kann auch:

```powershell id="f8s1za"
git add .
```

verwendet werden.

---

# 5. Staging prüfen

Nach `git add`:

```powershell id="8v4jbx"
git status
```

Zusätzlich:

```powershell id="3e4r9d"
git diff --staged
```

Das ist eine wichtige Prüfung.

`git diff` zeigt Änderungen, die noch nicht im Staging liegen.

`git diff --staged` zeigt dagegen die Änderungen, die tatsächlich in den nächsten Commit aufgenommen werden.

---

# 6. Commit erstellen

Wenn alles korrekt ist:

```powershell id="w2h7cn"
git commit -m "Update project documentation"
```

Eine Commit-Nachricht sollte beschreiben, **was geändert wurde**.

Beispiele:

```text id="y9f3cx"
Update project documentation
Add repository setup guide
Correct Git workflow documentation
Update troubleshooting guide
```

---

# 7. Commit kontrollieren

```powershell id="l2r5qp"
git log --oneline -3
```

Der neue Commit sollte jetzt sichtbar sein.

Zusätzlich:

```powershell id="0z7w8e"
git status
```

Wenn keine weiteren Änderungen vorhanden sind:

```text id="a6d3pq"
nothing to commit, working tree clean
```

---

# 8. Push durchführen

Jetzt wird der lokale Commit nach GitHub übertragen:

```powershell id="2t8k5s"
git push
```

Falls für den Branch noch kein Upstream eingerichtet wurde:

```powershell id="z9c1vf"
git push -u origin main
```

---

# 9. Push kontrollieren

Nach erfolgreichem Push:

```powershell id="g6w1xm"
git status
```

Anschließend das Repository auf GitHub öffnen.

Prüfen:

- Dateiänderung vorhanden?
- Commit vorhanden?
- richtiger Branch?
- erwarteter Inhalt?

---

# Gesamtablauf

```powershell id="6b9y3x"
cd "D:\GitHub\Mein-Projekt"

git status
git diff

git add .
git status
git diff --staged

git commit -m "Update project documentation"

git log --oneline -3
git status

git push

git status
```

---

# Was passiert dabei?

```text id="f4p6bc"
Datei ändern
    ↓
Working Tree
    ↓
git add
    ↓
Staging
    ↓
git commit
    ↓
lokale Git-Historie
    ↓
git push
    ↓
GitHub
```

## Merksatz

> **Commit speichert lokal. Push überträgt zu GitHub.**

Ein erfolgreicher Commit bedeutet deshalb noch nicht, dass die Änderung bereits auf GitHub vorhanden ist.