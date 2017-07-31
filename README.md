Dieses Verzeichnis enthält beispielhafte Fragen wie Sie in einer LPIC Prüfung kommen könnten, dies sind in keinem Falle original Fragen. Lediglich Beispielhafte Fragen durch viele einzelne Personen zusammen getragen. Der Autor steht auch nicht mit LPI in Verbindung. Dieses Programm ist gedacht als Lernhilfe für eine Zertifizierung nach LPI.

Dieser Test ist absichtlich als Shell script hinterlegt.

## Sie können diesen Test herunterladen mit 
```
git clone https://github.com/viisauksena/lpic-script
```

## Dependencys
"normales" Debian/Redhat Based Linux mit BASH Shell (default für die meisten)
`xcowsay`

ggf nachinstallieren mit 
```
$ sudo apt-get install xcowsay bash
```

Sie können in dem jeweiligen Verzeichnis  lokal auch eigene Fragen hinzufügen, beachten Sie folgenden Syntax:
(also in 101 oder 202 beispielsweise)

die erste Zeile enthält informationen zu der Antwort
in der Form von 
```
#blabla
```
wobei bla ein Freitextantwort ist
```
#001000
```
wobei gefolgt von der Frage in Zeile 2 in mehreren Zeilen nummerierte Antworten Folgen, wobei der Nutzer dann diese Nummern als Antworten angeben kann,
```
#001000 bedeutet nur die 3. Frage ist korrekt
#110101 bedeutet die 1.,2.,4. und 6. Antwort ist korrekt.
```
Die maximale Anzahl hier sind 6 Möglichkeiten. In diesem Fall muss eine Zeile mit 1. beginnen.

in der Datei highscore werden neben Datum und Uhrzeit noch die jeweils Richtigen / Unrichtigen Antworten archiviert mit den damals "falschen" Antworten, demnach könnte man nach vielen Durchläufen beispielsweise daraus seine schwächen schnell erkennen, bspw.
    $ cat highscore |grep 101 | cut -d " " -f 4- |grep -Eo [a-z0-9]+ | sort | uniq -c

zur vereinfachung gibt es ein script Namens `result`

(Es ist aufgrund der einfachen Struktur nicht möglich auf Freitextantworten alternativen anzugeben)
(aus dem gleichen Grund gibt es auch keine kommentierten Antworten, wenn das auch sehr wünschenswert wäre)

Wer mag kann das Script auch dahingehend umbauen das diese Dinge eingebaut werden, oder auch seine Fragen hier hinzufügen. Dazu einen PR stellen.
