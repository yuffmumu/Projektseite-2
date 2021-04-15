# Projektseite-2

[1 Einleitung](#1)

[2 Besonderheiten im 2. Projekt](#2)

[3 Das Programm](#3)

[3.1 Beschreibung des Programms](#3.1)

[3.2 Wie funktionieren die Einzelteile des Programms](#3.2)

[3.3 Besondere Herausforderungen](#3.3)

[4 Schlusswort](#4)


### <a name="1"></a>Einleitung:
Unser zweites Projekt erstellten wir in Greenfoot, doch der Weg zu dieser Entschiedung war ein Längerer, als man eventuell erwarten würde.
Uns war bewusst, was uns in der Welt des textbasierten Programmierens erwarten würde. Natürlich auf der einen Seite eine Menge Arbeit und schwierigkeiten aber vor allem auch theoretisch fast uneingeschränkte Möglichkeiten.
So sahen wir uns um, in welcher Form sich diese Möglichkeiten in unserem Offensichtlich, des grundsätzlich kurzen Halbjahrs wegen, eingeschränktem Zeitramen verwirklichen lassen würden.
Die "Unreal Engine" und "Greenfoot" kristallisierten sich als die 2 Kandidaten heraus, zwischen denen wir entscheiden mussten. Die Vorgebene Engine der "Unreal Engine" bestach dabei natürlich durch das Niveau das sich, sollte man sich tatsächlich so einen Projekt widmen, einstellen würde, doch wir mussten Anerkennen, das das Programmieren in der Unreal Engine unrealistisch war, und entschieden uns so für Greenfoot, was als Lernumgebung deutlich anfängerfreundlicher war.

Final erarbeiteten wir dann in Greenfoot eine Art proof of concept von dem retro Spiel "Tetris".
Tetris eignete sich in unserem Ramen gut, da es sich um ein theoretisch grundlegend fassbares Spielprinziep handelt und sich das proof of concept trotz unseres extrem eingeschränkten Zeitramens so zum Großteil realisieren ließ.

### <a name="2"></a>Besonderheiten im 2. Projekt:
Im 2. Projekt gab es 2 Dinge die unsere Progammierrfahrung mit Greenfoot extrem markant beeinflusst haben. 
Das erste ist natürlich Corona. Infolge des Virus wurde unser Präsenzunterricht absoulut minimiert und die Arbeitszeit, die man gemeinsam in einer gewohnten und angemessen Umgebung hatte somit auch. Dementsprechend wurde es zusätzlich herausfordernd sich ins textbasierte Prgrammieren einzuarbeiten.
Dies bringt uns dann auch zur 2. Besonderen Herausforderung: dem Textbasierten Programmieren.
Unsere Vorstellung von dem, was wir im Projekt erreichen wollten, war simpel genug um es mit unseren Fähigkeiten aus der blockbasierten prgrammiersprache "Snap!", welche wir ja in unserem ersten Projekt verwendeten, zu realisieren. 
Dementsprechend gab es nur wenige Stellen, an denen wir gezwungen waren, uns von der Denkweise, die wir uns in "Snap!" angeeignet hatten zu lösen und von daher hatten wir auch grundsätzlich meistens eine prinzipielle Idee, wie wir unsere Mechaniken im Spiel machen könnten, doch offensichtlich war die Realisierung dessen, was wir uns Theoretisch denken konnten die Herausforderung, denn die Begriffe und das Programmieren war in Greenfoot selbstverständlich ein anderes als in "Snap!". Die 2. größte Herausforderung im 2. Projekt war also die Anwendung unserer Vorstellung im textbasierten Programmieren.

### <a name="3"></a>Das Programm:

### <a name="3.1"></a>Beschreibung des Programms:

Die Grundidee hinter Tetris, die wir erreichen wollten, ist, dass Blöcke, die herunter fallen, eine Reihe auffüllen und diese daraufhin verschwindet.
Im tatsächlichen Spiel gibt es dabei noch verschiedene Aspekte wie unterschiedliche Formen oder einen "score counter", der die erreichte Anzahl an aufgelösten Reihen anzeigt.
Diese Features wurden aber im Ramen der Zeit schon von Anfang an ausgeschlossen.
 
### <a name="3.2"></a>Wie funktionieren die Einzelteile des Programms:


### <a name="3.3"></a>Besondere Herausforderungen:
Das große Problem was sich am Ende herauskristallisierte war, dass die Überprüfung der Reihen bzw. der Blöcke über die "actors" stattfand.
Es gibt 2 Möglichkeiten um die Reihen zu überprüfen. Die eine Möglichkeit ist über die "world" festzulegen, ob die unterste Reihe in dem Grid ausgefüllt ist.
Vorraussetzung dafür ist, das die Welt klar unterteilt ist. Hat man solche Bereiche festgelegt kann man abfragen ob ein Bereich, wie die unterste Reihe, komplett mit Blöcken ausgefüllt ist und sofern dies der Fall ist diesen Bereich Löschen.
Unsere herangehensweise hingegen bezog sich, wie in "Wie funktionieren die Einzelteile des Programms" erklärt, von anfang an nicht auf die Welt, sondern auf die Blöcke bzw. actor Klassen an sich.
Aus diesem Grund ließ sich der über die "bottom detectors" ermittelte Bereich in der Welt nicht einfach löschen, da es an sich nur möglich ist die ganze "block"-Klasse zu löschen oder einen einzelnen Block. 
Auch wenn die dahinter steckende Logik, das Spielfeld einzuteilen und das Programm auf diesem Weg erkennen zu lassen, welche Blöcke es löschen soll, die gleiche ist, wurde das Pferd sozusagen von der flaschen Seite aufgezogen, bzw. die Lösung des Problems wäre jedenfalls nicht so elegant möglich gewesen, wie wenn es über die "world" unterteilt worden, wäre.
Ein unverwirklichter Lösungsansatz für unseren Ansatz wäre gewesen, ein seperaten Block bei jedem "respawn" zu erstellen, anstatt die "block"-klasse bei jedem respawn praktisch zu klonen, um zu gewährleisten, dass die Variablen der Objekte individuell sind, und man dadurch auf die einzelnen Blöcke zugreifen und somit einzeln Löschen könnte.
Eine neue Klasse für jeden Respawn zu erstellen gelang uns jedoch im Zeitrahmen, trotz recherche und ggf. des unglücklichen Ansatzes wegen, bis zum Ende nicht.

 

### <a name="4"></a>Schlusswort:

