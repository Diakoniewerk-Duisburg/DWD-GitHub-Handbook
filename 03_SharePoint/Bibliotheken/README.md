# SharePoint Bibliotheken

## Rolle

Dokumentbibliotheken sind die zentrale Ablage fuer Dokumente und Dateien innerhalb der SharePoint-Informationsarchitektur. Sie werden von strukturierten Listen und anderen Datenobjekten unterschieden.

## Architekturbezug

Das Referenzprojekt beschreibt SharePoint Online als Plattform fuer Sites, Hub-Struktur und Dokumentablage. Dokumentbibliotheken gehoeren damit zur fachlichen Informationsarchitektur einer Site und muessen mit Site-, Berechtigungs-, Metadaten- und Lifecycle-Konzept abgestimmt werden.

## Grundsaetze

- Dokumente werden nach fachlicher Funktion und nicht nur nach Dateiendung strukturiert.
- Metadaten sind gegenueber rein hierarchischer Ordnerablage zu bevorzugen, wenn Informationen ueber mehrere Kontexte hinweg gesucht und klassifiziert werden.
- Berechtigungen folgen der fachlichen Verantwortlichkeit und nicht einzelnen Dateien als Standardfall.
- Aufbewahrung, Versionierung, Freigabe und Loeschung sind Bestandteil des Lifecycle.
- Bibliotheken fuer unterschiedliche Schutz- oder Berechtigungsbereiche werden getrennt modelliert, wenn eine gemeinsame Berechtigungsstruktur nicht sinnvoll ist.

## Bezug zum DWD-Modell

Sites werden im Core-Modell als konkrete Informationsraeume gefuehrt. Die Bibliotheksstruktur ist daraus fachlich abzuleiten und darf nicht unabhaengig von Informationsarchitektur und Berechtigungskonzept entstehen.

## Quelle

`DWD-SharePoint-M365/05_Documentation/02_Architektur/SharePoint-Informationsarchitektur.md` und die zugehoerige Dokumentation zu Anforderungen, Berechtigungen und Betrieb.
