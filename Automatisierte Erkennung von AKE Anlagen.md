---
title: Automatisierte Erkennung von AKE Anlagen
permalink: /Automatisierte-Erkennung-von-AKE-Anlagen
---
# Automatisierte Erkennung von AKE Anlagen
Für die Automatisierte Erkennung wurden zahlreiche Möglichkeiten entdeckt, die bisher lediglich als Prototyp existieren. Wir freuen uns auf eure Mithilfe die Protyphase zu verlassen.
## Mautbrücken automatisiert erkennen
Auch wer keinen Kennzeichenscanner in der Nähe hat, kann sich an der (Hardware)Entwicklung/Test zur automatisierten Erkennung beteiligen. Mautbrücken funktionieren sehr ähnlich und sind viel häufiger anzutreffen. Diese haben für jede Fahrspurt inklusive Strandstreifen gleich mindestens 2 Scanner. Gut zu wissen: Laut dem [Wikipedia Mautbrücken Artikel](https://de.wikipedia.org/wiki/Mautbr%C3%BCcke) dürfen aus Datenschutzgründen nicht alle Mautbrücken gleichzeitig betrieben werden. Es sollen nur 10 % aller LKWs kontrolliert werden. Bei unseren Tests über Monate hinweg zu verschiedenen Tages und Nachtzeiten bei verschiedenen Mautbrücken auf verschiedenen Autobahnen waren diese immer aktiv.

Mautbrücken waren nicht das Ziel dieses Projekts und wurden nicht so detailliert wie die Kennzeichenscanner untersucht, daher sind die nachfolgenden Informationen nicht als 100%ig gesichert anzusehen und dienen rein informativen Zwecken.

Mautbrücken verfügen entweder über ein gepulstes/flackerndes IR-Licht oder eine weitere Lidar-Einheit mit wesentlich stärkerem Laser, im Bild mit „IR-Licht?“ gekennzeichnet. Da Mautbrücken deutlich mehr IR-Licht als Kennzeichenscanner abgeben, kommt es vor, dass die automatisierte Enttarntechnik an ihnen funktioniert während sie an den Kennzeichenscannern versagt, wie der Laserwarner und der Slaveblitz, siehe unten.

Durchfahrt durch eine Mautbrücke bei Nacht (nur rechte Spur und Standstreifen der Mautbrücke aufgenommen):

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Mautbruecke/Mautbr%C3%BCcke%20Durchfahrt%20Nacht.jpg)


Mautbrücke Überblick:
![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Mautbruecke/Mautbr%C3%BCcke%20%C3%9Cberblick.jpg)

Mautbrücke mit Anmerkungen:
![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Mautbruecke/Mautbr%C3%BCcke%20Detail.jpg )
In der Mitte (kleinstes rotes Rechteck) ist eine Videoüberwachungskamera. Die beiden Einheiten ganz oben scheinen ebenfalls IR-Blitzeinheiten zu sein.
## Softwarelösungen zur AKE Erkennung
Großer Vorteil bei Softwarelösungen ist der unschlagbare Preisvorteil. Dank OpenSource kann entstehen keine zusätzlichen Kosten. Basis ist hier OpenCV. Da wir leider nicht beurteilen können wie aufwändig die jeweilige Maßnahme ist, zählen wir hier alle Möglichkeiten auf.

Wenn jemand einen entsprechenden Algorithmus entwickelt hat bitte über „Issues“ Kontakt aufnehmen. Wir verfügen über eine Menge Videomaterial der Anlagen und testen den Algorithmus gerne daran. Es ist der Sache schon sehr geholfen wenn potentielle Stellen des Videos erkannt werden um dann bei einer manuellen Nachkontrolle nur noch die Falschpositiven zu entfernen.

### Infrarotblitzerkennung bei Nacht
Der ungefähre Algorithmus dafür sieht so aus. Erkenne eine großflächige Veränderung von Pixeln mit hohem Helligkeitswert, die nur auf einem Bild vorhanden sind. Der IR-Blitz ist durch die kurze Dauer nur auf einem einzigen Bild zu sehen. Davor und danach ist es schwarz. Zur Veranschaulichung: 

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/BlitzSerie/0.jpg)

Die Punkte entstehen durch die schnelle Vorbeifahrt am Lidar. Der Laser tastet mehrmals pro Sekunde die gesamte Umgebung ab. Wenn er dabei auf die Kameralinse trifft, entsteht der helle Punkt.

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/BlitzSerie/1.jpg)

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/BlitzSerie/2.jpg)

Es ist noch ein kleiner Überrest vom Scanner zu sehen

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/BlitzSerie/3.jpg)

Das komplette Video gibt es hier https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/BlitzSerie/IR%20Blitz%20von%20hinten.mp4 zum Download

Sollte die Rechenleistung ausreichen kann die Erkennung direkt auf auf dem Raspberry-PI durchgeführt werden, und automatisch der passende Videoausschnitt gespeichert werden. 

Aber auch bei einer Offlineerkennung am PC wird durch den Wegfall der manuellen Sichtung viel Zeit gespart.


### AKE Detektion durch Lidar
Universaleinsetzbar sind die Lidarpunkte. Diese lassen sich auch bei Tag mittels vorgesetztem 850 nm IR-Filter erkennen. Beispielbilder für das Lidar bei Tag mit IR-Filter. Die nachfolgende Bilderserie sind aufeinanderfolgende Bilder aus dem ursprünglichen Video. Das Lidar ist nur auf Bild 2 deutlich an den stecknadelkopfgroßen Punkten zu erkennen. Die Bilder sind unbearbeitet zum Training eines Algorithmus. 

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/AKE-Lidar-Tag/LidarA8_1.jpg)

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/AKE-Lidar-Tag/LidarA8_2.jpg)

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/AKE-Lidar-Tag/LidarA8_3.jpg)


## AKE Erkennung Hardwarelösungen
### AKE Erkennung via Radarwarner
Gerade aus dem Bereich der Radarwarner gibt es zahlreiche Geräte um Lasermessungen zu erkennen. Hierbei muss man zwischen „echten Lasermessungen“ mittels Laserpistole und der Lidarmessung unterscheiden. Lidarfähige Geräte werden meist als Poliscan-Speed tauglich verkauft. Sie schlagen regelmäßig bei Mautbrücken an. Ein uns kostenlos zur Verfügung gestellter Whistler GT-130XI an der Heckscheibe sowohl waagerecht als auch im 45° Winkel montiert, schlug leider bei einem Kennzeichenscanner mit nur einer LIDAR-Einheit nicht an. Wir vermuten, dass er entweder nicht empfindlich genug ist oder durch die moderne Wärmeschutzverglasung und der senkrechten Position der Heckscheibe das IR-Licht in der Scheibe zu sehr gedämpft wird. 
Wir freuen uns über eure Tests mit Radwarnern zur Erkennung der Kennzeichenscananlagen und werden diese hier veröffentlichen. Wenn möglich bitte bei Tag und bei Nacht messen. Erfahrungsgemäß gibt es auf der Autobahn viel „Störradar“. Bitte achtet deshalb genau drauf ob die Laserwarnung bei euch losgeht. Ihr müsst das Gerät direkt hinter die Heckescheibe legen. Trotz beworbener rundum-Lasererkennung wird durch den steilen Einfallwinkel des Lidars kein Laser zum Warner an der Frontscheibe vordringen.

### AKE Erkennung via Infrarotimpulsdetektor 
Dieses Gerät funktioniert zuverlässig in der Nacht, wahrscheinlich in der Dämmerung und eventuell sogar am Tag. Ein sehr einfacher Infrarot-Impulsdetektor ist ein [Slaveblitz von Somikon](https://www.amazon.de/Somikon-Blitz-2in1-Aufsteckblitz-Fernauslöse-Funktion-Blitzgerät/dp/B0045IYQI0) Ein Slaveblitz ist eigentlich dafür gedacht um den schwachen Blitz einer Kompaktkamera zu verstärken indem der schwache Blitz erkannt und der zusätzliche starke Blitz dazu abgefeuert wird. Bei der Durchfahrt unter eine Mautbrücke im 45° Winkel gehalten löst er zuverlässig auf den Infrarotblitz aus. Bei der Durchfahrt durch eine Kennzeichenscananlage leider nicht. Entweder ist auch hier die IR-Dämpfung der Heckscheibe zu stark oder das IR-Licht im Vergleich zur Mautbrücke mit wesentlich mehr IR-Quellen zu schwach. 

Auf eine Infrarotfernbedienung löst er aus einem Abstand von bis zu ca. 50 cm, abhängig von den Lichtbedingungen (bei Tageslicht kürzer) aus. Fernsehapparate erkennen die Fernbedienung zuverlässig aus mehreren Metern Entfernung. Hier freuen wir uns über Unterstützung eines Elektronikers, der eine solche Empfängerschaltung modifiziert um ein Signal bei IR-Blitz zu liefern. Ansatz: Sehr kurzer IR-Impuls, wahrscheinlich unter 50 ms. Mit einem digitalen Speicheroszilloskop kann die Impulsdauer kann an Mautbrücken ermittelt werden. Der Lidar Laser könnte ähnlich erkannt werden: Periodische IR-Impulse mit einer bestimmten Frequenz, die sich durch die Vorbeifahrt leicht verschiebt, daher wird der aufgezeichnete IR Impuls durch diesen Lidarfrequenz überlagert sein. Es wird die Messung bei Nacht empfohlen um IR Impulse durch Schatten und Spiegelung des Tageslichts zu verhindern. Ihr habt eine taugliche Hardware(idee), dann einfach Kontakt über „Issues“ aufnehmen. 

Sollte es funktionieren, rechnen wir mit Hardwarekosten von maximal 10 €. Damit ist es, wenn die Erkennung auch bei Tag zuverlässig klappt, unser Favorit. Der IR-Blitz der Kennzeichenscanner wurde bei unseren Tests auch am Tag bei besten Lichtverhältnissen ausgelöst.

# Mobile AKE / Kennzeichenscanner Erkennung
Mobile Kennzeichenscanner sehen aus wie Blitzer und blitzen wahrscheinlich zur Tarnung sogar bei einer Geschwindigkeitsüberschreitung. Im Gegensatz zu den stationären Anlagen messen sie von vorne. Die Erkennung ist mitdenselben automatisierten Erkennungstechniken möglich. Das Gerät muss lediglich statt auf der Hutablage vorne auf der Windschutzscheibe mit Blickrichtung nach vorne positioniert werden. Wird ein IR-Blitz festgestellt, handelt es sich definitiv um einen Kennzeichenscanner. Abgesehen von Tunneln wird immer mit sichtbarem Licht (oder komplett ohne) „geblitzt“. Bei einer Messung von hinten, wie auf dem folgenden Bild zu erahnen, ändert sich gegenüber der Erkennung von stationären Kennzeichenscannern wenig. Die Kamera sollte etwas weiter nach unten ausgerichtet werden und solltet ihr den Laserstörer wie in [Schutzmaßnahmen gegen Kennzeichenerfassung](https://scan-rec.github.io/Schutzmassnahmen-gegen-Kennzeichenerfassung) beschrieben verwenden, auch hier an die tiefere Positionierung/Ausrichtung denken.

Eine kurzfristige Warnung über Radiosender oder/und auch die Blitzer.de Option „Verkehrskontrolle“ hilft andere Verkehrsteilnehmern zu warnen und so ihr Recht auf informationelle Selbstbestimmung zumindest teilweise wahrzunehmen.

Das bayerische Fernsehen brachte einen Bericht über die neuen mobilen Scanner der Polizei. Es gibt Scanner auf Stativen und Scanner im Blaulichtbalken der Streifenwagen integriert. Vom technischen Aufbau sehen sie ähnlich wie die neuen Mautsäulen aus. Denkbar ist hier ein dauerhaftes IR-Licht zur Beleuchtung. Eine automatisierbare Enttarnmethode ist hier mit zwei Kameras aufzunehmen. Eine IR und eine normales Licht. Ist es in der IR-Kamera hell wo es bei der Normallichtkamera dunkel bleibt, wurde IR-Licht und ein Scanner gefunden. Ein solcher Vergleichsalgorithmus (einfache Subtraktion zweier Bilder) ist für Profis leicht zu implementieren. Die Scanner im Blaulichtbalken messen euch von hinten, d.h. das Polizeiauto muss hinter euch fahren um euch zu erfassen. Wir freuen uns auch hier über Einsendungen über „Issues“.
Mobile Kennzeichenscanner am Straßenrand sind etwa auf Kennzeichenhöhe angebracht. Für stationäre Scanner ist diese Position untauglich, da bei Regen und insbesondere im Winter Salzwasser die Scanner durch das hochgeschleuderte Wasser sehr schnell verdrecken.


Bilder aus dem BR Bericht:
Mobiler Scanner auf Stativ:

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Mobile-Scanner/BR%20Ansicht%20mobiler%20Scanner%20Stativ.jpg)

Mobiler Scanner im Blaulichtbalken:
![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Mobile-Scanner/BR%20Ansicht%20mobiler%20Scanner%20im%20Blaulicht.jpg )

## Mobile AKE Erkennung via Auge
Das ZDF brachte in heute am 05.02.2019 einen Beitrag über die Entscheidung des Bundesverfassungsgerichts zum  Kennzeichenscanning und dazu mehrere Szenen von mobilen Kennzeichenscannern. Radarkontrollen aus einem Fahrzeug heraus blitzen durch eine getönte Heckscheibe um die Radartechnik vor dem Autofahrer besser zu verstecken. Getönte Heckscheiben lassen lassen nur sehr wenig Infrarotlicht durch, deswegen kann die Kennzeichenscan-Technik nicht hinter einer getönten Heckscheibe versteckt werden. Die ZDF Bilder zeigen das. Dort ist dann z.B. ein Fahrzeug mit einer herkömlichen Heckscheibe, aber getönten Seitenscheiben zu sehen. Eine Kombination, die so nicht verkauft wird und alle Alarmglocken schrillen lässt. Ein blitzerähnlicher Aufbau in einem Fahrzeug ohne getönte Heckscheibe ist mit an Sicherheit grenzender Wahrscheinlichkeit ein Kennzeichenscanner!

Fahrzeug mit getönten Seitenscheiben aber normaler Heckscheibe

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Mobile-Scanner/ZDF%20heute%2005.02.2019%20Mobiler%20Kennzeichenscanner%20mit%20unget%C3%B6nter%20Heckscheibe%20und%20get%C3%B6nten%20Seitenscheiben.jpg)


Weiterer Kennzeichenscanner im Fahrzeug

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Mobile-Scanner/ZDF%20heute%2005.02.2019%20Mobiler%20Kennzeichenscanner%20im%20Fahrzeug.jpg)


Weiterer mobiler Kennzeichenscanner 

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Mobile-Scanner/ZDF%20heute%2005.02.2019%20Mobiler%20Kennzeichenscanner.jpg)



Hier noch ein weiterer sehr unauffälliger mobiler Scanner aus dem SR-Fernsehen

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Mobile-Scanner/SR%20aktuell%2005.02.2019.jpg)


Folgendes Scannermodell dürfte schon etwas älter sein

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Mobile-Scanner/ZDF%20heute%20%2005.02.2019%20mobiler%20Scanner%20Stativ.jpg)
