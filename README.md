# HelferOrga · Status

Der Wächter von außen für [HelferOrga](https://helferorga.de). Alle fünf
Minuten fragt er `https://helferorga.de/status` ab: 200 heißt, das Programm
läuft und alle Datenbanken lassen sich lesen; alles andere ist eine Störung.
Er läuft bei GitHub und nicht auf dem Server von HelferOrga — deshalb meldet
er auch dann, wenn die ganze Maschine weg ist.

**Die Seite:** [status.helferorga.de](https://status.helferorga.de)

## [Stand jetzt](https://status.helferorga.de): <!--live status--> **🟩 All systems operational**

<!--start: status pages-->
<!--end: status pages-->

## Wie es funktioniert

- **Prüfen** — GitHub Actions ruft die Adresse alle fünf Minuten ab
  (`.github/workflows/uptime.yml`, eingestellt in `.upptimerc.yml`).
- **Melden** — fällt sie aus, öffnet sich hier ein Issue, und GitHub schickt
  eine Mail. Antwortet sie wieder, schließt sich das Issue von selbst.
- **Zeigen** — die Seite wird aus diesem Repository gebaut und über GitHub
  Pages ausgeliefert.

Geprüft wird mit Absicht nur die Adresse des ganzen Hauses und keine einer
Organisation: dieses Repository ist öffentlich, und ein Kürzel darin nennte
jedem einen Kunden.

Was es mit dem Wächter auf sich hat, steht im Repository von HelferOrga in
`SERVER.md`, Abschnitt 11.6.

## Lizenz

Gebaut mit [Upptime](https://upptime.js.org) von Anand Chowdhary, MIT-Lizenz
(`LICENSE`).
