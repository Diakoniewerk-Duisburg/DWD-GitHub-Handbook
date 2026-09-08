# Praxisbeispiel 07 – Mehrere Änderungen sauber committen

## Situation

Während einer Arbeitssitzung wurden mehrere Dateien geändert.

Beispielsweise:

```text id="h5q7n3"
README.md
02_GitHub_Online/README.md
04_HowTos/README.md
05_Praxisbeispiele/...
```

Jetzt stellt sich die Frage:

> Sollen alle Änderungen gemeinsam committed werden?

Die Antwort lautet:

> **Nicht automatisch.**

Entscheidend ist, ob die Änderungen logisch zusammengehören.

---

# 1. Änderungen vollständig erfassen

Zunächst:

```powershell id="2b8d4q"
git status
```

Beispiel:

```text id="y7f4m2"
modified: README.md
modified: 02_GitHub_Online/README.md
modified: 04_HowTos/README.md
```

---

# 2. Änderungen einzeln betrachten

```powershell id="0h3n8c"
git diff
```

Jetzt wird geprüft, welche inhaltlichen Änderungen tatsächlich vorgenommen wurden.

---

# 3. Logischen Zusammenhang feststellen

Beispiel:

```text id="x5q9w2"
README.md
04_HowTos/README.md
05_Praxisbeispiele/README.md
```

Alle Änderungen dienen demselben Zweck:

> Navigation des GitHub-Handbooks verbessern.

Dann kann ein gemeinsamer Commit sinnvoll sein.

Beispiel:

```powershell id="c2m7h5"
git add .
git commit -m "Improve handbook navigation"
```

---

# 4. Nicht zusammengehörende Änderungen trennen

Beispielsweise:

```text id="u3k8r6"
README.md                  → Dokumentation
PROJECT_TIME_TRACKING.md   → Zeiterfassung
TestScript.ps1             → technischer Test
```

Diese Änderungen gehören möglicherweise nicht zusammen.

Dann sollte nicht einfach alles mit:

```powershell id="x6s2n9"
git add .
```

committed werden.

Stattdessen können Dateien gezielt vorgemerkt werden:

```powershell id="n8q1cw"
git add README.md
```

Danach:

```powershell id="q4p6s8"
git diff --staged
```

und anschließend:

```powershell id="w9f2r5"
git commit -m "Update handbook documentation"
```

Danach kann die nächste logische Änderung separat committed werden.

---

# 5. Warum kleine logische Commits sinnvoll sind

Eine gute Commit-Historie sollte nachvollziehbar sein.

Beispiel:

```text id="6k3v9d"
Add GitHub online workflow
Add repository transfer guide
Improve handbook navigation
Add troubleshooting examples
Update security documentation
```

Weniger hilfreich wäre:

```text id="m8c1p4"
Update files
Changes
Fix stuff
Update
```

Die Commit-Historie ist später eine wichtige Informationsquelle.

---

# 6. `git add .` ist nicht automatisch falsch

Der Befehl:

```powershell id="3p5d7n"
git add .
```

ist praktisch und kann bei einem zusammenhängenden Änderungsumfang sinnvoll sein.

Er sollte aber nicht bedeuten:

> Alles ungeprüft committen.

Nach dem Staging:

```powershell id="8r4m2x"
git diff --staged
```

prüfen.

---

# 7. Beispiel für eine saubere Arbeitsweise

```powershell id="4w7z9c"
git status
git diff

git add README.md
git add 04_HowTos/README.md
git add 05_Praxisbeispiele/README.md

git status
git diff --staged

git commit -m "Improve handbook navigation"
```

Danach:

```powershell id="e6c2n5"
git status
```

---

# 8. Mehrere Commits statt eines großen Commits

Beispiel:

```text id="q7v3a1"
Änderungen
   │
   ├── Dokumentation
   │       ↓
   │    Commit 1
   │
   ├── Troubleshooting
   │       ↓
   │    Commit 2
   │
   └── Sicherheit
           ↓
        Commit 3
```

Das erleichtert später:

- Nachvollziehbarkeit
- Fehleranalyse
- Review
- Rückverfolgung
- gezielte Korrekturen

---

# Merksatz

> **Ein Commit sollte eine logisch zusammengehörende Änderung beschreiben – nicht einfach alle aktuell vorhandenen Änderungen.**