# LayoutManager
/*Zunächst werden zwei Konstanten festgelegt: GAP legt den Zwischenraum
zwischen dem Behälterrand und dem ersten Wort bzw. zwischen zwei Worten
fest, MINROWHEIGTH bezeichnet die minimale Zeilenhöhe.
Bei der Berechnung des Layouts wird die aktuelle Zeilenhöhe mit der minimalen
initialisiert. Dann wird die Breite des Behälters ermittelt, für den das
Layout zu berechnen ist. Dabei wird die Breite eines möglichen Behälterrahmens
abgezogen (die Methode getInsets liefert die dafür notwendigen Informationen).
Nach diesen Vorbereitungen wird die aktuelle Position im Behälter initialisiert: 
Die x-Koordinate xPos wird auf den linken Rand gesetzt
(0). Die y-Koordinate yPos erhält denWert des oberen Randes (inset.top)
zzgl. eines Zwischenraums (GAP).
Der Reihe nach wird dann für die Komponenten comp des Behälters folgendes
durchgeführt: Ist comp eine Zeilenumbruchsmarkierung, wird der aktuelle
x-Wert auf den Anfang der Zeile gesetzt, der aktuelle y-Wert um die
ermittelte Zeilenhöhe zuzüglich einer minimalen Höhe (als zusätzlicher Absatzabstand)
inkrementiert und die Zeilenhöhe neu initialisiert.
Andernfalls setzt der Layout-Manager die aktuelle Größe der Komponente
auf deren bevorzugte Größe. Wenn in der Zeile bereits Komponenten
platziert sind (posX != 0) und die nächste Komponente nicht mehr in die
Zeile passt ((x + width + gap) > maxwidth), wird ein Zeilenumbruch
vorgenommen. Im Übrigen wird ein horizontaler Zwischenraum eingefügt,
comp an die aktuelle Position platziert, die x-Postion um die Breite von comp
verschoben und die Zeilenhöhe auf das Maximum der bisherigen Höhe und
der Höhe von comp festgelegt.
Nach jeder aus
der Textdatei gelesenen Zeile wird in der Behälterkomponente eine Umbruchsmarkierung
in Form einer LineBreak-Komponente eingefügt. Da
auch leere Zeilen zu einem Umbruch führen, kann man mittels Leerzeilen
Absätze erzeugen.*/
