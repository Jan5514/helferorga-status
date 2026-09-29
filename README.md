# HelferOrga · Wächter von außen

Fragt alle fünf Minuten `https://helferorga.de/status` ab. Antwortet die
Seite nicht mit 200, öffnet sich hier ein Issue mit der Marke `ausfall`, und
GitHub schickt eine Mail; antwortet sie wieder, schließt es sich von selbst.
200 heißt dort: das Programm läuft, und alle Datenbanken lassen sich lesen.

Der Wachhund auf dem Server merkt vieles, aber nicht, dass die ganze
Maschine weg ist — dann ist er es auch. Dafür ist dieser Wächter da, und
deshalb läuft er bei GitHub und nicht dort.

## Was es hier nicht gibt

**Keine öffentliche Statusseite.** Wer eine Seite ausliefert, sieht die
Adressen ihrer Besucher, und die gehen niemanden außerhalb von HelferOrga
etwas an. Die Statusseite für Menschen steht auf dem Server selbst:
[helferorga.de/status](https://helferorga.de/status), und für jede
Organisation unter ihrer eigenen Adresse. Hier sieht GitHub nur seine
eigenen Abrufe.

**Kein Kürzel einer Organisation.** Dieses Repository ist öffentlich — nur so
sind die Läufe kostenlos —, und ein Kürzel darin nennte jedem einen Kunden.
Die Seite des ganzen Hauses prüft ohnehin alle Datenbanken.

## Wie es gebaut ist

Eine Datei: `.github/workflows/waechter.yml`. Kein Zugangsschlüssel — der
eingebaute Token darf Issues öffnen und einmal im Monat
`lebenszeichen.txt` schreiben. Das ist nötig, weil GitHub Zeitpläne in einem
öffentlichen Repository abschaltet, in dem 60 Tage lang nichts passiert ist.

**Den Alarm proben:** unter *Actions → Wächter → Run workflow* eine Adresse
eintragen, die es nicht gibt. Es öffnet sich ein Issue; der nächste
planmäßige Lauf schließt es wieder.

GitHub hält seine Zeitpläne nicht auf die Minute ein; unter Last kommt eine
Prüfung auch zehn Minuten später. Für einen Dienst dieser Größe reicht das.
Mehr in HelferOrga, `SERVER.md` 11.6.
