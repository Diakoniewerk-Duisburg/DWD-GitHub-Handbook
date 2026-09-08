# Praxisbeispiel 05 – Push abgelehnt

## Situation

Eine lokale Änderung wurde committed und anschließend soll sie nach GitHub übertragen werden.

Der Push wird jedoch abgelehnt.

Beispielsweise:

```powershell
git push
```

führt zu einer Meldung, dass der Remote-Branch Änderungen enthält, die lokal noch nicht vorhanden sind.

---

# 1. Was bedeutet das?

Vereinfacht:

```text id="g9x2cd"
Lokal                         GitHub
  │                              │
  │ Commit A                     │
  │ Commit B                     │
  │ Commit C                     │
  │                              │ Commit X
  │                              │
  └────────── push ─────────────►│
                 ✕
```

Git verhindert den Push, weil dadurch Änderungen auf GitHub überschrieben werden könnten.

Das ist zunächst **ein Schutzmechanismus und kein Fehler von Git**.

---

# 2. Nicht sofort Force Push verwenden

Nicht einfach:

```powershell
git push --force
```

verwenden.

Ein Force Push kann die Historie des Remote-Repositorys verändern und unter Umständen Commits anderer Personen überschreiben.

Zuerst muss geklärt werden, warum die Stände voneinander abweichen.

---

# 3. Lokalen Zustand prüfen

```powershell
git status
```

Danach:

```powershell
git branch --show-current
git remote -v
```

Damit wird geprüft:

- welcher Branch aktiv ist
- welches Repository als Remote verwendet wird
- ob lokale Änderungen vorhanden sind

---

# 4. Ursache feststellen

Ein häufiger Grund ist eine Änderung direkt auf GitHub.

Beispielsweise:

```text id="6m8xk2"
GitHub:
README geändert
        ↓
Commit auf GitHub
```

Während lokal:

```text id="0j2x7q"
README ebenfalls geändert
        ↓
lokaler Commit
```

Jetzt existieren unterschiedliche Änderungen.

---

# 5. Remote-Änderungen holen

Wenn das lokale Arbeitsverzeichnis sauber ist, zunächst:

```powershell
git pull
```

Git versucht nun, die Änderungen von GitHub mit dem lokalen Branch zusammenzuführen.

---

# 6. Fall A – Git kann automatisch zusammenführen

Wenn die Änderungen nicht miteinander kollidieren, kann Git die Historien automatisch zusammenführen.

Danach:

```powershell
git status
```

prüfen.

Wenn alles korrekt ist:

```powershell
git push
```

---

# 7. Fall B – Merge Conflict

Wenn Git die Änderungen nicht automatisch zusammenführen kann, entsteht ein Merge-Konflikt.

Beispielsweise:

```text id="6v5c4j"
<<<<<<< HEAD
Lokale Version
=======
GitHub Version
>>>>>>> origin/main
```

Jetzt muss entschieden werden, welcher Inhalt erhalten bleiben soll.

Nicht einfach die Konfliktmarkierungen stehen lassen.

Nach der manuellen Bearbeitung:

```powershell
git add <Datei>
```

Danach den Merge abschließen beziehungsweise den von Git vorgegebenen nächsten Schritt durchführen.

Anschließend:

```powershell
git status
```

und nach erfolgreicher Konfliktauflösung:

```powershell
git push
```

Siehe auch:

[Merge Conflict](../08_Troubleshooting/Merge_Conflict.md)

---

# 8. Fall C – GitHub enthält eine Änderung, die bewusst übernommen werden soll

Beispielsweise wurde online eine Dokumentation ergänzt.

Dann ist der gewünschte Ablauf:

```text id="7a3v5p"
GitHub
  │
  │ git pull
  ▼
lokal
  │
  ├── bestehende Änderungen
  │
  └── GitHub-Änderung
         │
         ▼
      zusammenführen
         │
         ▼
       commit
         │
         ▼
       push
         │
         ▼
      GitHub
```

---

# 9. Fall D – GitHub-Änderung soll bewusst nicht übernommen werden

Hier darf nicht einfach mit einem beliebigen Befehl die Remote-Historie überschrieben werden.

Zunächst muss geklärt werden:

- Warum wurde die Änderung erstellt?
- Wer hat sie erstellt?
- Soll sie erhalten bleiben?
- Ist das Remote tatsächlich das richtige Repository?
- Ist der lokale Stand möglicherweise veraltet?

Erst danach darf über die weitere Vorgehensweise entschieden werden.

---

# 10. Sonderfall: GitHub wurde nur versehentlich initialisiert

Ein häufiger Fall beim Erstellen eines neuen Repositorys:

Lokal existiert bereits eine vollständige Git-Historie.

Auf GitHub wurde zusätzlich eine README erzeugt.

Dadurch entstehen zwei unabhängige Historien:

```text id="z4f7s2"
Lokal:

A ── B ── C


GitHub:

X
```

Für einen sauberen Transfer wäre es besser gewesen, das GitHub-Repository leer zu erstellen.

In diesem Fall kann es sinnvoller sein, die Situation zu bereinigen und das Ziel-Repository entsprechend neu aufzusetzen, anstatt eine unnötige Historienverknüpfung zu erzeugen.

---

# 11. Kontrolle nach der Lösung

Nach erfolgreicher Synchronisierung:

```powershell
git status
```

Danach:

```powershell
git log --oneline -5
```

und:

```powershell
git remote -v
```

Schließlich das GitHub-Repository kontrollieren.

---

# Entscheidungslogik

```text id="2y9r8x"
Push abgelehnt
      ↓
git status
      ↓
git remote -v
      ↓
Ursache?
      │
      ├── Remote enthält neue Änderungen
      │          ↓
      │       git pull
      │          ↓
      │    ┌─────┴─────┐
      │    ↓           ↓
      │ automatisch   Konflikt
      │    ↓           ↓
      │  prüfen     Konflikt lösen
      │    └─────┬─────┘
      │          ↓
      │       git push
      │
      └── falsches Remote
               ↓
           erst korrigieren
```

# Merksatz

> **Ein abgelehnter Push ist zunächst eine Aufforderung zur Prüfung – nicht zur Verwendung von `--force`.**