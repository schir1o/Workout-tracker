# PickMe 💌

Eine Single-File-Landingpage im Liebesbrief-Look: versiegelter Umschlag, Briefpapier,
Handschrift-Typografie, am Ende ein perforiertes Date-Ticket.

**Live:** https://schir1o.github.io/PickMe/

## Ablauf

0. **Umschlag** – Wachssiegel, tippen zum Öffnen
1. **Der Brief** – die Frage · der Nein-Zettel flüchtet und verschwindet nie,
   handgeschriebene Nachrichten flattern rein, „Ja" wächst mit jedem Ausweichen
2. **Planung** – Aktivitäten (mehrere möglich), eigenes Ideen-Feld, Uhrzeit
3. **Ticket** – Zusammenfassung zum Screenshotten, die Mails gehen von allein raus

Design: Nachtblau-Verlauf mit Filmkorn und schwebendem Staub, Papier in Creme,
Rubin als Akzent. Schriften: *Fraunces* (Serif) und *Caveat* (Handschrift) von Google Fonts —
fallen ohne Netz sauber auf Systemschriften zurück. Reduzierte Bewegung wird respektiert
(`prefers-reduced-motion`).

Fürs Handy: `dvh`-Höhen, Safe-Area fürs Notch, Tap-Ziele ≥ 46 px,
16 px Eingabefelder (kein Auto-Zoom in iOS), kein Bounce-Scrolling.

Es gehen **zwei Mails** an `keller.dke@gmail.com`:

- sofort beim Klick auf **Ja** („hat JA gesagt!") — falls sie die Planung nicht fertig macht
- nach dem Abschicken mit allen Details (Wann / Was / Eigene Idee)

Sie muss nichts auswählen und nichts bestätigen. Scheitert der Versand, schickt die Seite
die Mail still über einen zweiten Weg (verstecktes Formular statt AJAX) — ohne dass sie es merkt.

## ⚠️ Einmalig freischalten (wichtig!)

Der Mailversand läuft über [FormSubmit](https://formsubmit.co) (kostenlos, ohne Anmeldung).
Beim **allerersten** Absenden schickt FormSubmit eine Bestätigungsmail an `keller.dke@gmail.com`
mit einem Aktivierungslink. Erst nach dem Klick kommen die Antworten wirklich an.

**Also: die Seite einmal selbst komplett durchklicken, dann die Mail von FormSubmit
bestätigen** — bevor du den Link verschickst.

## Anpassen

Alles steckt in `index.html`. Ganz oben im `<script>`:

```js
var NAME = "Tatjana";
var MAIL = "keller.dke@gmail.com";
```

Weiter unten:

- **Sprüche des Nein-Buttons**: Array `texts`
- **Süße Nachrichten**: Array `sweet`
- **Date-Ideen**: die `.opt`-Buttons in `#opts`
- **Uhrzeiten**: die `.chip`-Buttons in `#times`
- **Farben**: die CSS-Variablen ganz oben (`--yes`, `--bg1`…`--bg3`)
- **Wie stark Ja wächst**: `scale*1.18` bzw. das Maximum `3.2`

## Änderungen hochladen

```bash
git add -A && git commit -m "update" && git push
```
