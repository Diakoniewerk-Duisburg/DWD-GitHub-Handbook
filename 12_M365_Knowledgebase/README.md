# DWD M365 Knowledgebase

## Zweck

Die DWD M365 Knowledgebase bündelt fachliches, technisches, organisatorisches und projektbezogenes Wissen rund um die digitale Arbeitsumgebung.

Microsoft 365, SharePoint, Power Platform, Copilot und GitHub sind **gleichberechtigte Wissensdomänen**. GitHub ist damit kein nachgelagerter Quellenspeicher, sondern ein eigener Bestandteil der Gesamtwissensarchitektur.

## Zielarchitektur

```text
DWD M365 Knowledgebase
│
├── 00_Governance
├── 01_Organisation
├── 02_Microsoft_365
├── 03_SharePoint
├── 04_Power_Platform
├── 05_Copilot
├── 06_GitHub
├── 07_Daten
├── 08_Prozesse
├── 09_Architektur
├── 10_Entwicklung
├── 11_Betrieb
├── 12_Sicherheit_und_Compliance
├── 13_Projektwissen
├── 14_Wissensobjekte
└── 90_Quellen
```

## Grundprinzipien

1. Jede Domäne besitzt eine eigene fachliche und technische Verantwortung.
2. GitHub ist eine gleichberechtigte Wissensdomäne und wird nicht auf seine Rolle als Quelle reduziert.
3. Die primäre Quelle eines Wissensobjekts wird eindeutig festgelegt.
4. Inhalte werden nicht unnötig mehrfach gepflegt.
5. Fachliches, technisches, organisatorisches und projektbezogenes Wissen bleibt unterscheidbar.
6. Copilot ist keine Primärquelle, sondern nutzt freigegebene Wissensquellen.
7. Verbindliche Entscheidungen werden von Empfehlungen und Entwürfen getrennt.
8. Veraltete Inhalte werden kenntlich gemacht und nicht als aktuelle Wahrheit verwendet.
9. Dateinamen und Ordner bleiben ohne Umlaute.
10. Dokumentation wird grundsätzlich auf Deutsch geführt; technische Bezeichner bleiben in der etablierten Schreibweise.

## Verhältnis zu bestehenden Repositories

Die Knowledgebase ist ein Wissensmodell und keine Aufforderung zur physischen Zusammenkopierung aller Inhalte.

Bestehende Repositories bleiben dort, wo sie fachlich und technisch hingehören. Für GitHub ist insbesondere das bestehende `DWD-GitHub-Handbook` die operative Primärquelle für Git- und GitHub-Arbeitsweisen. Die Domäne `06_GitHub` bildet diese Inhalte konzeptionell innerhalb der Knowledgebase ab, ohne das Handbook zu zerstören oder dessen bestehende Struktur umzubauen.

Die Zuordnung wird in `00_Governance/KONSOLIDIERUNGSMATRIX.md` dokumentiert.

## Quellen

`90_Quellen` beschreibt Herkunft und Provenienz von Wissen. Eine Quelle ist nicht automatisch eine eigene Wissensdomäne. Die Domänenstruktur bestimmt, wo Wissen fachlich eingeordnet wird; das Quellenmodell bestimmt, woher die Aussage stammt.

## Status

**Zielmodell beschlossen – Domänenstruktur und Konsolidierung werden schrittweise aufgebaut.**
