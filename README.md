# PickMe 💌

Eine Single-File-Landingpage: „Tatjana, willst du morgen mit mir auf ein Date?"
Der **Nein**-Button flüchtet (auch auf dem Handy), der **Ja**-Button wird immer größer.

**Live:** https://schir1o.github.io/PickMe/

## Ablauf

1. **Frage** – Nein hüpft weg und verschwindet nie, süße Nachrichten poppen auf
2. **Planung** – Aktivitäten auswählen (mehrere möglich), eigenes Ideen-Feld, Uhrzeit
3. **Fertig** – die Mails gehen von allein raus

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
