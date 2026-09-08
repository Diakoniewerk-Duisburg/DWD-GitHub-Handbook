# Praxisbeispiel 08 – Online und lokal arbeiten

## Situation

Ein GitHub-Repository wird sowohl direkt über die GitHub-Weboberfläche als auch lokal mit Git bearbeitet.

Beispiel:

```text id="k2v5z8"
GitHub Weboberfläche
        │
        │ Änderung
        ▼
GitHub Repository
        ▲
        │
        │ git push
        │
Lokales Repository
        │
        │ lokale Änderung
        ▼
      Arbeit
```

Diese Arbeitsweise ist möglich, erfordert aber Aufmerksamkeit.

---

# 1. Online wurde eine Änderung durchgeführt

Beispielsweise wurde auf GitHub:

```text id="q6w3n9"
README.md
```

bearbeitet und committed.

Damit enthält GitHub jetzt einen neuen Commit.

---

# 2. Lokales Repository kennt diesen Commit noch nicht

Lokal kann der Stand beispielsweise noch so aussehen:

```text id="r8p4m1"
A ── B ── C
```

GitHub:

```text id="s5x2k7"
A ── B ── C ── D
```

Der lokale Stand ist damit hinter dem Remote-Stand.

---

# 3. Vor lokaler Weiterarbeit synchronisieren

Wenn lokal keine offenen Änderungen vorhanden sind:

```powershell id="c3n7v2"
git status
```

anschließend:

```powershell id="b8m4q5"
git pull
```

Danach enthält das lokale Repository ebenfalls Commit `D`.

---

# 4. Lokal weiterarbeiten

Jetzt kann beispielsweise eine weitere Datei geändert werden:

```text id="m7q2z9"
README.md
```

oder:

```text id="v4c8p3"
04_HowTos/Neue_Anleitung.md
```

Danach:

```powershell id="j6r1x5"
git status
git diff
```

---

# 5. Lokalen Commit erstellen

```powershell id="s9k4w2"
git add .
git diff --staged
git commit -m "Add new GitHub workflow guide"
```

---

# 6. Nach GitHub übertragen

```powershell id="n3f7c1"
git push
```

Jetzt enthält GitHub beide Änderungen.

```text id="g4m8x6"
A ── B ── C ── D ── E
                  ▲
                  │
             lokaler Commit
```

---

# 7. Problemfall: Online und lokal wurden gleichzeitig geändert

Jetzt wird es interessant.

GitHub:

```text id="2p8s5v"
A ── B ── C ── D
```

Lokal:

```text id="7k3q1m"
A ── B ── C ── E
```

Beide Seiten haben nach Commit `C` unabhängig weitergearbeitet.

Ein Push kann abgelehnt werden.

```text id="a6r9t2"
       D
      /
A─B─C
      \
       E
```

---

# 8. Richtige Reaktion

Nicht:

```powershell id="q8m2v5"
git push --force
```

Sondern zunächst:

```powershell id="x4c7n9"
git status
git remote -v
git branch --show-current
```

Danach:

```powershell id="f3k6p1"
git pull
```

Git versucht, beide Entwicklungszweige zusammenzuführen.

---

# 9. Konflikt möglich

Wenn dieselbe Stelle in einer Datei unterschiedlich geändert wurde, kann ein Merge Conflict entstehen.

Dann:

```powershell id="v5n8q2"
git status
```

und die betroffenen Dateien prüfen.

Siehe:

[Merge Conflict](../08_Troubleshooting/Merge_Conflict.md)

---

# 10. Grundregel für gemischte Arbeitsweise

Wenn ein Repository hauptsächlich lokal bearbeitet wird:

> **Vor Beginn der lokalen Arbeit `git pull`.**

Wenn zwischendurch direkt auf GitHub gearbeitet wurde:

> **Vor der nächsten lokalen Arbeit erneut synchronisieren.**

Wenn lokal gearbeitet wurde:

> **Vor dem Push Änderungen prüfen und anschließend `git push`.**

---

# Empfohlener Ablauf

```text id="z7c2m8"
        GitHub
           │
           │ Änderung online?
           ▼
       git pull
           │
           ▼
      lokal arbeiten
           │
           ▼
       git status
           │
           ▼
        git diff
           │
           ▼
        git add
           │
           ▼
   git diff --staged
           │
           ▼
       git commit
           │
           ▼
        git push
           │
           ▼
        GitHub
```

---

# Merksatz

> **Online und lokal kann man parallel arbeiten – aber man muss wissen, dass dadurch unterschiedliche Stände entstehen können.**

Die sicherste Gewohnheit ist:

> **Vor lokaler Arbeit synchronisieren, vor dem Push prüfen.**