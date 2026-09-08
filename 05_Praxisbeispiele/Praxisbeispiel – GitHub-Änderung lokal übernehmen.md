# Praxisbeispiel 02 – GitHub-Änderung lokal übernehmen

## Situation

Eine Änderung wurde direkt auf GitHub durchgeführt.

Beispielsweise wurde:

- eine Markdown-Datei geändert,
- eine neue Datei angelegt,
- eine Dokumentation ergänzt,
- eine Datei verschoben.

Anschließend soll lokal mit dem aktuellen Stand weitergearbeitet werden.

---

## 1. In das lokale Repository wechseln

```powershell
cd "D:\GitHub\Mein-Projekt"
```

---

## 2. Lokalen Zustand prüfen

```powershell
git status
```

Wenn lokal noch eigene ungesicherte Änderungen vorhanden sind, sollte zunächst geklärt werden, wie damit umzugehen ist.

Nicht einfach blind `git pull` ausführen.

---

## 3. Änderungen von GitHub holen

Wenn der lokale Arbeitsstand sauber ist:

```powershell
git pull
```

Git lädt die neuen Änderungen vom Remote und integriert sie in den lokalen Branch.

---

## 4. Ergebnis kontrollieren

```powershell
git status
```

Zusätzlich kann geprüft werden:

```powershell
git log --oneline -5
```

Die auf GitHub durchgeführte Änderung sollte jetzt auch lokal vorhanden sein.

---

## 5. Weiterarbeiten

Jetzt kann lokal weitergearbeitet werden.

Beispiel:

```text
GitHub
  │
  │ git pull
  ▼
lokales Repository
  │
  ▼
lokale Änderung
  │
  ▼
git add
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

# Typischer Fehler

Wenn lokale Änderungen vorhanden sind und gleichzeitig Änderungen auf GitHub existieren, kann `git pull` zu Konflikten oder Problemen führen.

Dann zunächst:

```powershell
git status
```

und die Situation analysieren.

Siehe:

[Merge Conflict](../08_Troubleshooting/Merge_Conflict.md)

---

# Merksatz

> **Online geändert bedeutet: Vor der nächsten lokalen Arbeit zuerst synchronisieren.**

Der wichtigste Befehl dafür ist:

```powershell
git pull
```