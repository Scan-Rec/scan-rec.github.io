---
title: Funktionsweise der KFZ-Kennzeichen-Scanner
permalink: /Funktionsweise-der-KFZ-Kennzeichen-Scanner
---

# KFZ-Kennzeichen-Scanning Funktionsweise
## Funktionsweise der automatisierten Kennzeichenscanner
Die stationären Kennzeichenscanner nehmen die Autos von hinten in einem Abstand von ca. 8-15 Metern auf. Je Fahrspur gibt es maximal eine Aufnahmeeinheit. Ist sie ziemlich exakt zwischen 2 Fahrstreifen über der Fahrbahnlinie, hat sie beide Fahrspuren im Blick. Ist sie mittig über einer Fahrspurt, hat sie genau diese im Blick. Eine LIDAR Einheit erfasst die Fahrzeuge (pro Einheit maximal 3 Fahrspuren). Die Lidareinheit ist äußerlich nicht von einer Fotoeinheit zu unterscheiden. Meinst ist sie etwas stärker geneigt als die Fotoeinheiten. Aus ihr wird nur LIDAR abgegeben, kein IR-Blitz, wie Aufnahmen von der Brücke aus des Kennzeichenscanners auf der A9 bei Röthenbach und des Scanners am Irschenberg zeigten. Im richtigen Abstand zur Aufnahmeeinheit wird ein unsichtbarer Infrarotblitz im Bereich von 900-950 nm ausgelöst und fotografiert das gesamte Fahrzeug mit Kennzeichen. Das Kennzeichen ist auch im IR-Bereich sehr reflektiv, wodurch es durch IR-Licht sehr gut aufgenommen werden kann. 

Das aufgenommene Kennzeichenbild wird mittels OCR in Text umgewandelt. Laut offiziellen Angaben wird das so erfasste Kennzeichen mit einer Datenbank abgeglichen und bei keiner Übereinstimmung sofort angeblich wieder unwiederbringlich gelöscht. Quelle [Bayerisches Innenministerium](https://www.stmi.bayern.de/med/pressemitteilungen/pressearchiv/2018/303b/index.php) Kontrollieren kann das keiner. Es bedarf vermutlich nicht mehr als ein paar Mausklicks und schon werden alle vorbeifahrenden Kennzeichen gespeichert. Sofern die Bilder hierzu nicht gespeichert werden, gerät man als Unschuldiger besonders schnell ins Visier, da die korrekte Erkennungsrate sehr niedrig ist, siehe Buffeed News [Kennzeichenerfassung der Polizei funktioniert nicht](https://www.buzzfeed.com/de/marcusengert/kennzeichenerfassung-der-polizei-funktioniert-nicht)

Sehr wahrscheinlich werden die Kennzeichen immer mal wieder gespeichert, so ist es zumindest zwischen den Zeilen [diesem Dokument](https://www.daten-speicherung.de/data/Bf_Schriftsatz_Kfz-Massenscanning_By_2011-08-11_Anlage.pdf) S.3  zu entnehmen. 
>Zu Frage 3 der FDP-Fraktion: Bei negativem Abgleich würden die Daten unwiederbringlich gelöscht. Dementsprechend sei kein Bewegungsbild möglich. Anders sehe es in Fällen der polizeilichen Beobachtung aus. Hier würden Treffer zusammengeführt und an die ausschreibenden Stellen übermittelt. Rechtsgrundlage sei Art. 36 PAG.

Staatliche Behörden legen Gesetze sehr kreativ aus. Vorstellbar ist: Man definiert einfach alle vorbeikommenden Personen / Fahrzeuge als zu beobachten und sieht sich im Recht alle vorbeikommenden Kennzeichen zu speichern.
Daneben gibt es auch noch mobile Anlagen, die oftmals zusammen mit Blitzern aufgestellt werden, damit sie nicht wahrgenommen werden. Auch hier ist eine Enttarnung möglich, siehe [Automatisierte Erkennung von AKE-Anlagen](https://scan-rec.github.io/Automatisierte-Erkennung-von-AKE-Anlagen)

Update: Wie zu vermuten war, wurden teilweiese sämtliche Kennzeichen inkl. des Fahrzeuges auf Vorrat gespeichert ohne gezielt nach einem bestimmten Kennzeichen gesucht zu haben, Quelle: [Heise AKE Bayern und Brandenburg speichern Kennzeichen auf Vorrat]( https://www.heise.de/newsticker/meldung/Kfz-Kennzeichen-Scanning-Bayern-und-Brandenburg-speichern-Fahrer-auf-Vorrat-4420441.html)

Die [offizielle AKE Funktionsbeschreibung](https://www.daten-speicherung.de/data/Gericht_Kfz-Massenscanning_By_2011-10-17.pdf) ist ab Seite 2 nachzulesen.

>1. Wie funktioniert die Kennzeichenerfassung (technisch) genau?

>Dazu erläutern die Beklagtenvertreter: "Bei stationären Kennzeichenerfassungsanla­gen handelt es sich um digitale Kameras, die den fließenden Verkehr von hinten er­fassen und bei denen die digitale Aufnahme des Kennzeichens durch einen Infrarot­blitz ausgelöst wird. Durch den Infrarotblitz wird auf dem digitalen Bild im Wesentli­chen nur das reflektierende Kennzeichen erfasst; allerdings kann man aus den Auf­nahmen auch Rückschlüsse darauf ziehen, ob es sich beispielsweise um einen Lkw, einen Pkw oder ein Kraftrad handelt."

>Zur Verdeutlichung und Erläuterung derartiger Aufnahmen wird ein Beispiel eines sog. Treffers als Bildschirmabzug übergeben und zu den Gerichtsakten genommen. 

>Die Klägerseite erhält ebenfalls eine Kopie.

>Die Beklagtenvertreter erläutern weiter: "Der Infrarotblitz wird dabei ausgelöst durch einen sog. Laser-Trigger; d.h. wenn durch ein Fahrzeug der auf die Fahrbahn gerich­tete Laserstrahl unterbrochen wird, kommt es zur Bildaufnahme. Dieses digitale Bild wird dann durch die eingesetzte OCR-Software ausgelesen; die Buchstaben und Zif­fern des Kennzeichens werden dabei in eine Buchstaben-Ziffern-Folge umgewandelt. 

>Dabei ist bereits in die Aufnahmekamera ein entsprechender Computer integriert, auf dem diese OCR-Software installiert ist.“

>Auf Nachfrage: "Das hier beschriebene System stationärer Kennzeichener­fassungsgeräte wird in Bayern seit 2006 einheitlich eingesetzt. Das beschriebene stationäre Erfassungssystem ist dabei regelmäßig an einer Schilderbrücke über der Fahrbahn angebracht. Der digitale Datensatz mit den Ziffern und Nummern des Kennzeichens wird von dort über eine Datenleitung an einen am Fahrbahnrand in einem entsprechenden Behältnis untergebrachten stationären Rechner weitergeleitet. 

>Auf diesem Rechner befindet sich ein Datenbanksystem, in dem die abzugleichen­den Dateien abgespeichert sind und mit denen das erfasste Kennzeichen abgeglichen wird. Dieser stationäre Rechner selbst ist entweder über eine Funkverbindung (UMTS) oder eine Datenstandleitung mit dem Bayer. Landeskriminalamt (LKA) ver­bunden, wobei diese Verbindung allein dazu benutzt wird, die im Computer gespeicherten Fahndungsdateien laufend zu aktualisieren. Daneben gibt es eine weitere Verbindung dieses Rechners mit der jeweiligen Einsatzzentrale der Polizei, worüber im Trefferfall die Einsatzzentrale (des jeweils zuständigen Polizeipräsidiums) benachrichtigt wird. Der Datenabgleich zwischen dem erfassten Kennzeichen und den Fahndungsdateien selbst wird im Arbeitsspeicher dieses stationären Rechners durch­geführt. Kommt es zu einer Übereinstimmung zwischen dem erfassten Kennzeichen und den gespeicherten Datensätzen erfolgt die Speicherung dieses sog. Treffers temporär in d er Datenbank au f dem Rechner; von dort wird er unmittelbar an die Einsatzzentrale der Polizei übertragen. Nach dieser zuletzt genannten Übertragung an die Einsatzzentrale wird der in der Datenbank auf dem Rechner vor Ort gespei­cherte Treffer gelöscht. Ob diese Löschung des Treffers im Datenbanksystem völlig "rückstandslos" erfolgt oder nicht, entzieht sich unserer genau en Kenntnis. Der bis­her beschriebene Vorgang dauert dabei etwa 0,5 Sekunden. Wird im stationären Rechner vor Ort keine Übereinstimmung mit den abgeglichenen Datenbeständen festgestellt (sog. Nichttreffer), erfolgt die Löschung des digitalen Kennzeichensatzes unmittelbar aus dem Arbeitsspeicher des Rechners“

>Von Klägerseite wird insoweit die Frage gestellt, ob die Datenabfrage bei d er auf dem Rechner vorgehaltenen Datenbank nicht gleichwohl selbst in einer sog. Log- Datei auf der Festplatte dieses Computers erfasst wird. Im Hinblick  uf diese Frage ist aus Sicht des Senats noch ergänzend zu klären, inwieweit hier eine rückstandslo­se Löschung der Nichttreffer im System gewährleistet ist.

>Auf Nachfrage des Gerichts erklären die Beklagtenvertreter: „Der Datenabgleich fin­det ausschließlich mit Dateien des Bayerischen Landeskriminalamts statt; nur die dort geführten Fahndungsdateien sind auch auf dem Rechner vor Ort aufgespielt.“ Auf Frage der Klägerseite: "Bisher ist keiner dieser Rechner abhanden gekommen oder sonst beschädigt worden."

>Auf weitere Nachfrage: "Bei Kennzeichenerfassungsanlagen an Autobahnen werden regelmäßig Kameras für jede einzelne Fahrspur installiert."

>Die Beteiligten sind sich darüber einig, dass damit bis auf die oben protokollierten noch offenen Punkte Frage 1 abschließend beantwortet ist.

## Funktionsweise der AKE Enttarnungsanlage
Digitalkameras reagieren sehr empfindlich auf Infrarot-Licht, daher haben gewöhnliche Kameras einen Sperrfilter für Infrarotlicht. Die Raspberry PI Camera V2 NOIR verzichtet auf den Sperrfilter. Dadurch eignet sie sich ideal zum Erkennen den IR-Blitz der Kennzeichenscanner. Wir richten die Kamera einfach nach hinten aus, nehmen das Video auf und schauen es zu Hause auf der Suche nach dem IR-Blitz an. Die Videos können in bis zu 4facher Geschwindigkeit (Rechnerabhängig ob es flüssig läuft) auf der Suche nach dem Infrarotblitz angesehen werden. [AKE Erfassung Beispielvideo](https://github.com/Scan-Rec/Scan-Rec/blob/master/Ressourcen/BlitzSerie/IR%20Blitz%20von%20hinten.mp4)

Videos der PI Camera werden grundsätzlich im H264-Format aufgenommen. Dieses Format ist unpraktisch, da nicht festgelegt, wieviel Bilder pro Sekunde angezeigt werden sollen und man so im Player kaum vorwärts und rückwärts springen kann. Deswegen werden für bessere Handhabbarkeit die Videos nach der Aufnahme in MP4 umgewandelt.

Wenn man den Raspberry-PI einfach ausschaltet, bleibt nur die .h264 Datei zurück. Um diesen nervigen Wandlungsschritt zu umgehen wurde mp4-Boxing aktiviert, d.h. der Raspberrpi verpackt das h264 automatisch in MP4 mit der richtigen Bildrate. Stoppt man die Aufnahme, muss man ihm auch genug Zeit geben diese Umwandlung durchzuführen, sonst steht das Video nur mit „Busy“ in der Downloadliste. Wenn es dort nach dem Stoppen nicht mehr mit Busy steht, noch ca. 30 Sekunden warten, dann kann der Raspberry-PI sicher über die Weboberfläche heruntergefahren werden (unten „System“ à „shutdown system“). Das Ende der Wandlung erkennbar daran, wenn grüne LED nur noch ab und zu blinkt.

## Details
Als Basis dient [RPi_Cam_Web_Interface](https://github.com/silvanmelchior/RPi_Cam_Web_Interface)
Um sich mit der Bedienung der Weboberfläche vertraut zu machen, den Abschnitt „Basic Usage“ durchlesen. Die restlichen Details werden nicht benötigt.
Nachfolgende Dienste laufen standardmäßig
### GPS-Einblendung.py
Es wurde ein wenig erweitert. Über die Datei /dev/shm/mjpeg/user_annotate.txt kann beliebiger Text ins Video eingeblendet werden. Dies wird genutzt um die aktuelle Position, Datum und Uhrzeit (GPS-Zeit in UTC und lokale Uhrzeit des Raspberry-PI) einzublenden. Die lokale Zeit wird automatisch über GPS gesetzt.
### GPS-Logger.sh
Schreibt nach /var/www/html/media/ das GPS-Log im NMEA Format. Kann zum Beispiel mit GPSBabel nach Google-Earth konvertiert werden.
### Webcam-Aufzeichnung.sh
Um eine 2. Perspektive wie z.B. eine Front-Kamera zu haben, dient diese Datei. Wichtig: Die Webcamera muss den Videostream h264 codiert liefern können. Die Logitech C920 Webcam ist dazu in der Lage und sogar genügend IR empfindlich, siehe [AKE Erkennung mit einfachen Mitteln](https://scan-rec.github.io/AKE-Erkennung-Enttarnung-ohne-Spezialhardware)

Eine Texteinblendung ist bei der USB-Kamera nicht möglich. 

Die Aufnahmen dieser zusätzlichen Webcam werden ebenfalls im H264 Format gespeichert. Bei einem Neustart des RaspberryPI werden alle h264 Aufnahmen in MP4 umgewandelt. Je nach Größe der Aufnahmen, kann dies ein paar Minuten dauern. Man erkennt diesen Fall daran, dass die Weboberfläche angezeigt wird, aber noch kein Bild angezeigt wird und die grüne LED des Raspberry fast dauerhaft leuchtet. Dann bitte geduldig sein und einfach abwarten.

Achtung: Es wird etwas mehr als die doppelte Menge an freiem Speicherplatz wie die größte umzuwandelnde h264-Datei benötigt

Wurde auf diesem Weg eine unfertige Aufnahme gewandelt, taucht sie nur über http://raspberrypi/html/media auf, in der „normalen“ Downloadseite für Videos wird sie nicht betrachtbar sein.

Zum Löschen dieser gewandelten Aufnahmen und der GPS-Logs per SSH verbinden dann nur über die Kommandozeile über cd /var/www/html/media mit suo rm [Dateiname] die gewünschte Datei löschen

### throttleMonitor.sh
Dieses Skript dient der Fehlersuche. Die Anlage lief bei uns unzählige Stunden problemlos. Wenn bei euch Probleme auftreten und im Video im ThrottleStatus etwas anderes als 0x0, dann per SSH verbinden und sich die Ursache anzeigen lassen. Meistens ist die Ursache eine zu geringe Spannung aufgrund von schlechten Mikrousb-Kabeln oder schwachen Powerbanks, erkennbar am status „Undervolted“.

„Run“ bedeutet hier, dass seit dem Hochfahren dieser Zustand auftrat (z.B. unter hoher Last), „Now“ das aktuell der Zustand auftritt. 

Überhitzung sollte unter normalen Bedingungen nicht auftreten, wenn dann mit einem Kühlkörper auf der CPU nachhelfen. Ab ca. 82 °C beginnt der Raspberry-PI die Leistung wegen Übertemperatur zu drosseln.
### startHostapd.sh
Baut das WLAN auf um sich unterwegs zu verbinden, die Kamera auszurichten und die Videoaufnahme zu starten. Konfiguration über hostapd.conf, siehe auch [Kennzeichenscanner Finder](https://github.com/Scan-Rec/Scan-Rec)
