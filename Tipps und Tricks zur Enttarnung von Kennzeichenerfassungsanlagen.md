---
title: Tipps und Tricks zur Enttarnung von Kennzeichenerfassungsanlagen
permalink: /Tipps-und-Tricks-zur-Enttarnung-von-Kennzeichenerfassungsanlagen
---


# Tipps und Tricks zur Enttarnung von Kennzeichenerfassungsanlagen
Hier finden sich ein paar Tipps und Tricks, die es zu beachten gilt.
## Getönte Heckscheiben vermeiden
Getönte Heckscheiben zeigten sich in unseren Tests nur wenig IR-Durchlässig. Wir haben keine Enttarnungsfahrt mit Filmen durch getönte Heckscheiben durchgeführt. Mit einer Raspberry-PI-NOIR Kamera könnte es klappen, bei den alternativen Enttarnungsmethoden, wie einer Handykamera, gehen wir davon aus, dass hier nichts sichtbar sein wird.
Auch die aktive Schutzmaßnahme mit Laserstörern ist durch eine getönte Heckscheibe hindurch zum Scheitern verurteilt.
## Sichtbarmachung des Lidars und IR-Blitz bei Tag
Die Raspberry PI NOIR V2 Kamera reagiert neben dem Infrarotlicht auch auf das normale sichtbare Licht. Bei Tag wird das IR-Licht der Kennzeichenscanner durch sichtbares Licht verdeckt. Durch die Anbringung eines IR-Filters wird das sichtbare Licht stark gedämpft und die IR-Signale wieder sichtbar. Wir empfehlen das [Neewer Infrarot Filterset ](https://www.amazon.de/Neewer%C2%AE-St%C3%BCck-Infrarot-R%C3%B6ntgen-Filter/dp/B015XMSUB0/)
Obwohl nur der 850 nm Filter benötigt wird, bleibt das Preis-Leistungsverhältnis hier unschlagbar. Der kleinste Durchmesser ist ausreichend. Der Filter wird mit Klebeband für die Raspberry-PI-Kamera geklebt. Aufgrund des Rolling-Shutter Effekts wird bei Tag der IR-Blitz oft nicht aufgenommen. Die Kennzeichenscanner sind jedoch über das Lidar zweifelsfrei identifizierbar.

## Scharfstellen der Kamera
Normalerweise wird die NOIR V2 Kamera auf die Ferne fokussiert ausgeliefert. Sollte sie bei euch unscharf sein, könnt ihr mit dem weißen Plastikring die Kamera nachstellen. 
Sehr einfach gelingt dies, wenn ihr einen Monitor über HDMI anschließt und dann 
`raspivid -t 1000 `
ausführt. Hierbei ist das Bild stark gezoomt und das Scharfstellen wird deutlich erleichtert. Als Vorlage eignet sich eine groß gedruckte Sehtafel (Bildersuche), ähnlich denen beim Optiker in ca. 4 Metern Entfernung platziert. Der Zoom entsteht durch ein anderes Sichtfeld, „FoV, Field of View“. Details sind in der [PI Camera Dokumentation](https://picamera.readthedocs.io/en/release-1.13/fov.html#sensor-modes) nachzulesen.
  
## Rolling Shutter Effekt / Zu kurzer IR-Blitz
Durch den Rolling-Shutter-Effekt und der sehr kurzen Dauer es IR-Blitzes kann es passieren, dass der IR-Blitz auf den Aufnahmen nicht zu sehen ist. Vereinfacht ausgedrückt werden die einzelnen Pixel zum falschen Zeitpunkt ausgelesen. Je mehr Pixel den IR-Blitz abbekommen, desto wahrscheinlicher ist zumindest ein Teil davon zu sehen ist. Bei Nacht war lediglich auf ca. einer von 20 direkten IR-Blitzaufnahmen die Erkennbarkeit durch den Rolling-Shutter-Effekt eingeschränkt. Rolling-Shutter bedeutet, dass die Pixel nacheinander ausgelesen werden. In Wikipedia ist im [Rolling Shutter Artikel](https://en.wikipedia.org/wiki/Rolling_shutter) unter „Temporal aliasing“ der Effekt von verlorenen Bildinhalten beschrieben. Gegenüber Kameras mit Global Shutter hat der Rolling Shutter den Vorteil, dass der IR-Blitz wenigstens teilweise zu sehen ist. Beim Global Shutter wäre er komplett oder gar nicht zu sehen. 

Beispielbilder:
![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Rolling-Shutter/Rollingshutter%20Verlust%20Original%20Videobild.jpg)
Dieses Bild ist unbearbeitet. Je nach Blickwinkel ist hier kaum ein IR-Blitz zu erkennen.


![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Rolling-Shutter/Rollingshutter%20Verlust%20durch%20Gammakorrektur%20besser%20sichtbar%20gemacht.jpg)
Dreht man das Gamma hoch, sind die Reste des IR-Blitzes deutlich zu erkennen. Tipp: Im VLC die Hardwarebeschleunigung deaktivieren um dort die Gamma-Erhöhung direkt beim Videoabspielen zu nutzen. [Anleitung](https://forum.videolan.org/viewtopic.php?t=145008) Wichtig: VLC danach beenden und neustarten, dann klappt es mit dem Gamma.

Deutlich bemerkbar macht sich der Rolling-Shutter-Effekt bei Tageslichtaufnahmen mit IR-Filter, da dort nur wenige Pixel belichtet werden und die Wahrscheinlich hoch ist, dass diese wenigen gerade nicht ausgelesen werden. Ebenfalls deutlich in Erscheinung tritt der Effekt, wenn man den Kennzeichenscanner von oben filmt. Wir dachten zunächst er arbeitet nicht zuverlässig und übersieht Autos, bis wir auf den Rolling-Shutter-Effekt stießen. Beispielbild von der Brücke Renzenhoferstraße auf den Kennzeichenscanner an der A9 bei Röthenbach. Der IR-Blitz ist deutlich zu sehen, die 3 Punkte auf einer Linie sind von einer entfernten Schilderbrücke. Der helle Punkt darunter ist das LIDAR.
![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Rolling-Shutter/2%20Von%20Br%C3%BCcke%20Renzenhoferstr%20aus%20-%20rechte%20Spur.jpg)


## Speicherbedarf
Größenordnung der Videos mit NoIR-Kamera

ca. 30 MB/Minute bei Tag (ca. 4 Mbit/s) [1,8 GB/Stunde]

ca. 7 MB/Minute bei Nacht (ca. 1 Mbit/s) [ca. 400 MB/Stunde]

ca. 13 MB/Minute bei Tag mit IR 850 Filter (ca. 2 Mbit/s) [ca. 800 MB/Stunde]

***

externe Kamera Logitech C920

ca. 30 MB/Minute bei Tag (ca. 4 Mbit/s) [1,8 GB/Stunde]

Bei der externen Kamera muss, wie in Funktionsweise geschrieben, beachtet werden:
Es wird etwas mehr als die doppelte Menge an freiem Speicherplatz wie die größte umzuwandelnde h264-Datei benötigt
