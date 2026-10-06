# Feiditor – Hinweise für die Entwicklung

- **Eine Engine für dreizehn Feiditoren:** Das große Skript („EINE Engine für alle Feiditoren“) ist byte-identisch
  im normalen Feiditor (janrickmer/feiditor), im Lerntagebuch-Feiditor (janrickmer/lerntagebuch-feiditor) und in
  den in die elf Escape-Rooms eingebetteten Feiditoren (janrickmer/escape-room-* sowie janrickmer/BSO-JG11 und
  janrickmer/Q3-PoWi-Konfliktanalyse-im-H-rtetest). Änderungen als exakte Ersetzungen in alle dreizehn Dateien
  einspielen und prüfen. Unterschiede nur über `window.FEIDITOR_CONFIG` (vor
  der Engine) oder eigene Skripte danach.
- **Auswertung für Lehrkräfte:** ausschließlich „Check des Feind(t)es“ (check.janrickmer.de, Repository
  janrickmer/check-des-feind-t-es mit ausführlicher `CLAUDE.md`). Im Feiditor gibt es keinen Lehrkraft-Zugang.
- **Nutzdaten** (`%TRACKDATA`, AES-GCM): `t`, `m`, `f`, `k`, `v: 2` (Längen in UTF-16-Einheiten), `z` (1 =
  Zwischenstand, 0 = fertige Abgabe); im Escape-Modus `e = {esc, red, ctx}` – `ctx` ist der Steckbrief des
  Escape-Rooms (Jahrgangsstufe, Inhalte) aus `window.__ESCAPE_DATA__.ctx` bzw. `%ESCAPEDATA` (Feld `c`).
- **Eine Datei für Moodle:** Die fertige Abgabe im Escape-Modus heißt „Abgeschlossener Escape-Room von Vorname
  Nachname.pdf“ (`makePdfName()`) und enthält vorne Aufgaben und Antworten, hinten die Überblicksseiten des
  Escape-Rooms. Der eingebettete Feiditor erzeugt sie aus `window.__ESCAPE_DATA__.overview` (`buildOverviewPages`);
  der eigenständige Feiditor übernimmt sie aus der hochgeladenen Überblick-PDF bzw. Zwischenstand-PDF
  (`overviewStreamsFrom()`: alle Seiten der Überblick-PDF, in Feiditor-PDFs die mit `%ESCAPE-OVERVIEW` markierten
  Content-Streams) und hängt sie unverändert an (`buildPdf`, `opts.overviewStreams`).
- **Live für Schüler:innen** (Branch `main`): vor jedem Push mit echten Dateien im Check testen.
