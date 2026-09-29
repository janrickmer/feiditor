# Feiditor – Hinweise für die Entwicklung

- **Eine Engine für elf Feiditoren:** Das große Skript („EINE Engine für alle Feiditoren“) ist byte-identisch im
  normalen Feiditor (janrickmer/feiditor), im Lerntagebuch-Feiditor (janrickmer/lerntagebuch-feiditor) und in
  den in die neun Escape-Rooms eingebetteten Feiditoren (janrickmer/escape-room-*). Änderungen als exakte
  Ersetzungen in alle elf Dateien einspielen und prüfen. Unterschiede nur über `window.FEIDITOR_CONFIG` (vor
  der Engine) oder eigene Skripte danach.
- **Auswertung für Lehrkräfte:** ausschließlich „Check des Feind(t)es“ (check.janrickmer.de, Repository
  janrickmer/check-des-feind-t-es mit ausführlicher `CLAUDE.md`). Im Feiditor gibt es keinen Lehrkraft-Zugang.
- **Nutzdaten** (`%TRACKDATA`, AES-GCM): `t`, `m`, `f`, `k`, `v: 2` (Längen in UTF-16-Einheiten), `z` (1 =
  Zwischenstand, 0 = fertige Abgabe); im Escape-Modus `e = {esc, red, ctx}` – `ctx` ist der Steckbrief des
  Escape-Rooms (Jahrgangsstufe, Inhalte) aus `window.__ESCAPE_DATA__.ctx` bzw. `%ESCAPEDATA` (Feld `c`).
- **Live für Schüler:innen** (Branch `main`): vor jedem Push mit echten Dateien im Check testen.
