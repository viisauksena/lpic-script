Dieses Verzeichnis enthält beispielhafte Fragen wie Sie wären einer LPIC 1 - 101 Prüfung kommen könnten, dies sind in keinem Falle original Fragen. Der Autor steht auch nicht mit LPI in Verbindung. Dieses Programm ist gedacht als Lernhilfe für eine Zertifizierung nach LPI 1.

Dieser Test ist absichtlich als Shell script hinterlegt.

Sie können diesen Test herunterladen mit 
git clone fooofoooo

Dependencys
"normales" Debian/Redhat Based Linux mit BASH Shell (default für die meisten)
xcowsay

ggf nachinstallieren mit 
$ sudo apt-get install xcowsay bash

Sie können in dem Verzeichnis question lokal auch eigene Fragen hinzufügen, beachten Sie folgenden Syntax:

die erste Zeile enthält informationen zu der Antwort
in der Form von 
#blabla
wobei bla ein Freitextantwort ist
#001000
wobei gefolgt von der Frage in Zeile 2 in mehreren Zeilen nummerierte Antworten Folgen, wobei der Nutzer dann diese Nummern als Antworten angeben kann,
#001000 bedeutet nur die 3. Frage ist korrekt
#110101 bedeutet die 1.,2.,4. und 6. Antwort ist korrekt.
Die maximale Anzahl hier sind 6 Möglichkeiten.

in der Datei highscore werden neben Datum und Uhrzeit noch die jeweils Richtigen / Unrichtigen Antworten archiviert mit den damals "falschen" Antworten, demnach könnte man nach vielen Durchläufen beispielsweise daraus seine schwächen schnell erkennen, bspw.
$ cat highscore |cut -d " " -f 4- |grep -Eo [a-z0-9]+ | sort | uniq -c

(Es ist aufgrund der einfachen Struktur nicht möglich auf Freitextantworten alternativen anzugeben)
(aus dem gleichen Grund gibt es auch keine kommentierten Antworten, wenn das auch sehr wünschenswert wäre)

Wer mag kann das Script auch dahingehend umbauen das diese Dinge eingebaut werden, oder auch seine Fragen hier hinzufügen. Dazu einen PR stellen.
Denkbar wäre auch meherere Branches zu haben für LPIC 101 102 201 202.
