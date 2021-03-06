# Projektseite-2

[1 Einleitung](#1)

[2 Besonderheiten im 2. Projekt](#2)

[3 Das Programm](#3)

[3.1 Beschreibung des Programms](#3.1)

[3.2 Wie funktionieren die Einzelteile des Programms](#3.2)

[3.3 Besondere Herausforderungen](#3.3)

[4 Schlusswort](#4)


### <a name="1"></a>Einleitung:
Final erarbeiteten wir in Greenfoot den Großteil einer Art "proof of concept" des retro Spiels "Tetris".
Wir wählten Tetris, da es sich um ein theoretisch grundlegend fassbares Spielprinziep handelt und sich das proof of concept so, trotz unseres sehr eingeschränkten Zeitramens, möglichst weit umsetzen ließ.

Der Weg zu dieser Entschiedung jedoch, war ein Längerer, als man eventuell erwarten würde.
Uns war bewusst, was uns in der Welt des textbasierten Programmierens erwarten würde. Natürlich auf der einen Seite eine Menge Arbeit und Schwierigkeiten, aber vor allem auch theoretisch fast uneingeschränkte Möglichkeiten.
So sahen wir uns um, in welcher Form sich diese Möglichkeiten in unserem Offensichtlich, des grundsätzlich kurzen Halbjahrs wegen, eingeschränktem Zeitramen möglichst umfangreich verwirklichen lassen würden.
Die "Unreal Engine" und "Greenfoot" kristallisierten sich als die 2 Kandidaten heraus, zwischen denen wir entscheiden mussten. Die Vorgebene Engine der "Unreal Engine" bestach dabei natürlich durch das Niveau das sich, sollte man sich tatsächlich so einen Projekt widmen, einstellen würde, doch wir mussten Anerkennen, das das Programmieren in der Unreal Engine unrealistisch war, und entschieden uns so für Greenfoot, was als Lernumgebung deutlich anfängerfreundlicher war.
Dies Stellte sich insbesondere infolge des 2. Lockdowns durch die Coronapandemie, als eine sehr gute Entscheidung heraus.

### <a name="2"></a>Besonderheiten im 2. Projekt:
Im 2. Projekt gab es 2 Dinge die unsere Progammierrfahrung mit Greenfoot extrem markant beeinflusst haben. 
Das erste ist natürlich Corona. Infolge des Virus wurde unser Präsenzunterricht absoulut minimiert und die Arbeitszeit, die man gemeinsam in einer gewohnten und angemessen Umgebung hatte somit auch. Dementsprechend wurde es zusätzlich herausfordernd sich ins textbasierte Prgrammieren einzuarbeiten.
Dies bringt uns dann auch zur 2. Besonderen Herausforderung: dem Textbasierten Programmieren.
Unsere Vorstellung von dem, was wir im Projekt erreichen wollten, war simpel genug um es mit unseren Fähigkeiten aus der blockbasierten prgrammiersprache "Snap!", welche wir ja in unserem ersten Projekt verwendeten, zu realisieren. 
Dementsprechend gab es nur wenige Stellen, an denen wir gezwungen waren, uns von der Denkweise, die wir uns in "Snap!" angeeignet hatten zu lösen und von daher hatten wir auch grundsätzlich meistens eine prinzipielle Idee, wie wir unsere Mechaniken im Spiel machen könnten, doch offensichtlich war die Realisierung dessen, was wir uns Theoretisch denken konnten die Herausforderung, denn die Begriffe und das Programmieren war in Greenfoot selbstverständlich ein anderes als in "Snap!". Die 2. größte Herausforderung im 2. Projekt war also die Anwendung unserer Vorstellung im textbasierten Programmieren.

### <a name="3"></a>Das Programm:

### <a name="3.1"></a>Beschreibung des Programms:

Die Grundidee hinter Tetris, die wir erreichen wollten, ist, dass Blöcke, die herunter fallen, eine Reihe auffüllen und diese daraufhin verschwindet.
Im tatsächlichen Spiel von Alexei Paschitnow aus dem Jahre 1984 gibt es dabei noch verschiedene Aspekte, wie unterschiedliche Formen oder einen "score counter", der die erreichte Anzahl an aufgelösten Reihen anzeigt.
Diese Features wurden aber im Ramen der Zeit schon von Anfang an ausgeschlossen, da sie auch für die Funktionsweise des tatsächlichen Spiels irrelevant sind.
 
### <a name="3.2"></a>Wie funktionieren die Einzelteile des Programms:
Unser "World constructor" spannt als erstes die Welt an sich auf.

![image](https://user-images.githubusercontent.com/69623479/115037665-fffaa500-9ece-11eb-9e1e-08a36ca42942.png)


Danach platziert er alle Objekte in der Welt (sowohl den Ersten Block, als auch die "bottom_detectors")

![image](https://user-images.githubusercontent.com/69623479/115037738-11dc4800-9ecf-11eb-8c15-a7beacd5dc50.png)


Nun sind alle Objekte des Programms in der Welt platziert und können ihrer Funktionsweise nachkommen.

![image](https://user-images.githubusercontent.com/69623479/115020375-cddf4800-9eba-11eb-8ed4-0eb92adc07c5.png)


Alle Methoden des Blockes werde hier in der "public act" Methode der Block-Klasse aufgerufen um sie modular aufzuteilen. Außerdem werden alle Variablen definiert, die in den Methoden benötigt werden.

![image](https://user-images.githubusercontent.com/69623479/115037802-26204500-9ecf-11eb-8104-aecd544b61e4.png)

Die erste Methode, die die Blöcke permanent ausführen müssen ist das nach unten Fallen.
Dazu wird eine Variable ("counter") jeden tick um einen erhöht. Der Operator modulo (Division mit Rest als Ergebnis) setzt die Vaiable "counter" auf 0 soblad sie, in unserem Fall, 30 erreicht, da erst dann das Ergebnis nicht identisch mit dem ursprünglichen Wert ist. Die if-Schleife wir nun nur ausgelöst, wenn die Variable "counter" 0 ist, d.h bei jedem 30. tick.

![image](https://user-images.githubusercontent.com/69623479/115020511-fcf5b980-9eba-11eb-84a4-1cac7748f4ea.png)

Die zweite Methode zur Bewegung der Blöcke ist die Steuerung nach Links und Rechts.
Prinzipiell ist es nur die Abfrage nach einem Tastendruck. Jedoch wurde dabei noch eine zusätzliche Bedingung über eine Variable gesetzt, um zu gewährleisten, dass sich die Blöcke, wenn sie unten angekommen sind, nicht mehr bewegen können.

![image](https://user-images.githubusercontent.com/69623479/115021174-ec920e80-9ebb-11eb-8134-d447fb1153c7.png)

Die nächste Mechanik, die zwingend notwendig war, war der Respawn.
Prinzipiell ging es darum, einen neuen Block in der Welt zu generieren, wenn einer der "bottom detectors" berührt wird.
Zusätzlich musste noch gewährleistet werden, dass nur ein Block gespawnt wird und nicht unendlich viele, sobald ein "bottom detector" belegt wird. Dies lösten wir wieder über eine zusätzliche Bedingung mit der Varaiblen "activated".

![image](https://user-images.githubusercontent.com/69623479/115025146-4812cb00-9ec1-11eb-8fac-284f0e82e448.png)

Zur erkennung des Bodens wurde die Klasse "bottom_detector" mit ihren 5 unterklassen eingefügt. Diese wurden genutzt um Variablen, die der Block benötigt entsprechend zu setzen.
Einmal das berühren eines der 5 "bottom_detector" subclasses:

![image](https://user-images.githubusercontent.com/69623479/115033802-228abf00-9ecb-11eb-9d2e-504a87a190c8.png)

und einmal in der Überklasse "bottom_detector" der Fall, dass alle Berührt werden um theoretisch den Command "delete_row" im Block zu initiieren (welcher jedoch nicht fertig ist und somit an dieser Stelle nicht weiter auftaucht):

![image](https://user-images.githubusercontent.com/69623479/115034035-5b2a9880-9ecb-11eb-9aff-a299fadb2a2e.png)


### <a name="3.3"></a>Besondere Herausforderungen:
Das große Problem was sich am Ende herauskristallisierte war, dass die Überprüfung der Reihen bzw. der Blöcke über die "actors" stattfand.
Es gibt 2 Möglichkeiten um die Reihen zu überprüfen. Die eine Möglichkeit ist über die "world" festzulegen, ob die unterste Reihe in dem Grid ausgefüllt ist.
Vorraussetzung dafür ist, das die Welt klar unterteilt ist. Hat man solche Bereiche (arrays) festgelegt kann man abfragen ob ein Bereich, wie die unterste Reihe, komplett mit Blöcken ausgefüllt ist und sofern dies der Fall ist, diesen Bereich Löschen.
Unsere herangehensweise hingegen bezog sich jedoch von anfang an nicht auf die Welt, sondern auf die Blöcke bzw. actor Klassen an sich.
Aus diesem Grund ließ sich der über die "bottom detectors" ermittelte Bereich in der Welt nicht einfach löschen, da es an sich nur möglich ist die ganze "block"-Klasse zu löschen oder einen einzelnen Block. Eine Liste wo die 5 Blöcke, die die Reihe füllen, eingetragen sind (wie sie auch im Block erklärt ist) wäre sicherlich mit mehr Zeit ein logischer Ansatz gewesen, jedoch lässt sich schwer sagen, ob es tatsächlich zur Lösung des Problems geführt hätte.
Auch wenn die dahinter steckende Logik, das Spielfeld einzuteilen und das Programm auf diesem Weg erkennen zu lassen, welche Blöcke es löschen soll, die gleiche ist, wurde das Pferd sozusagen von der falschen Seite aufgezogen, bzw. die Lösung des Problems wäre jedenfalls nicht so elegant möglich gewesen, wie wenn es über die "world" unterteilt worden wäre.

### <a name="4"></a>Schlusswort:

Unsere Erfahrung mit Greenfoot war von externen Umständen stark geprägt. 
Erst am schnell erreichten Ende der Arbeitszeit kamen wir langsam in einen Rythmus, in dem sich tatsächlich in Greenfoot arbeiten ließ.
Das erkennen von Problemen in Greenfoot z.B. über "break points", sowie das Aneignen von "keywords" wie z.B. "new" braucht Zeit.
Obwohl unsere Versuche über die reproduktion von mechaniken aus unserem ersten Projekt in "Snap!" an sich von Erfolg gekrönt war, insofern, als dass wir ein paar Grundbegriffe, wie "if commands" oder variablen wieder anwenden konnten, war es dennoch fast bis ganz zum Ende sehr schwer die Arbeit mit der Greenfoot API, dem Greenfoot Buch, Video reihen wie "the joy of code" und anderen Sourcecodes zu integrieren und sich an dieses, doch im Gegensatz zu "Snap!", sehr andere System zu gewöhnen.
Zum Schluss lässt sich aber doch sagen, dass das im Ramen der Zeit tatsächliche Ziel, nämlich die Grundzüge von OOP im Sinne der Klassen und Objekte etc. zu verstehen, durchaus erreicht wurde und wir für uns einen klaren Fortschritt im textbasierten Programmieren verzeichnen können.
Wir denken es ist durchaus anzunehmen, dass sich mit mehr Zeit das "proof of concept" von Tetris mit unseren erlangten Fähigkeiten hätte verwirklichen lassen können, da wir die Arbeitsweise und das Verständniss für die Informationsbeschaffung zum Arbeiten in Greenfoot uns im Endeffekt doch erfolgreich angeeignet haben und die Grundzüge von Greenfoot mit den geschafften Ergebnissen darstellen konnten.



