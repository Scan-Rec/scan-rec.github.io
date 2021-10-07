---
title: Schutzmaßnahmen gegen Kennzeichenerfassung
permalink: /Schutzmassnahmen-gegen-Kennzeichenerfassung
---

# Schutzmaßnahmen gegen Kennzeichenerfassung
## Allgemeines zu Schutzmaßnahmen gegen die automatisierte Kennzeichenerfassung
[Leider werden die Kennzeichen an immer mehr Stellen erfasst](https://www.sueddeutsche.de/digital/erfassung-von-nummernschildern-parken-in-der-grauzone-1.2184331), sodass Schutzmaßnahmen angeraten sind 

[Im Fall des LKW Schützen wurden ebenfalls Millionen von Kennzeichen erfasst ](https://www.sueddeutsche.de/auto/automatische-kennzeichenerkennung-wo-ihr-nummernschild-erfasst-wird-1.2188409)

Man darf nicht vergessen, es wird zwar behauptet, dass die Kennzeichen nicht gespeichert würden. Aber niemand kann das kontrollieren und selbst wenn, es bedarf nur eines Mausklicks und schon werden Kennzeichen gespeichert. Wer weiß wie oft das passiert? Schnell kann es dann passieren, dass man als [Unschuldiger unnötigen Stress und Ärger mit der Polizei bekommt](https://www.zeit.de/digital/datenschutz/2011-06/polizei-dresden-vorratsdaten). In der Vergangenheit kam dies Öfters vor, siehe auch die [mehrfache Rasterung des Mobilfunk durch die Berliner Polizei](https://www.spiegel.de/netzwelt/netzpolitik/handy-ueberwachung-berliner-polizei-rasterte-mehrfach-mobilfunk-nutzer-a-810660.html) Besonders brisant: Hier wird auch noch gelogen wie sie dem Täter auf die Schliche kamen. Da man von den Kennzeichenscannern kaum in der Presse liest (außer die Behörden möchten damit prahlen ähnlichem dem Jugendliche mit seinem aufgemotzten, tiefergelegten Sportwagen), verhält es sich mit den Kennzeichenscannern wahrscheinlich ähnlich.
[Weitere Berichte zur Erschreckenden Handyrasterfahndung](https://www.teltarif.de/funkzellenabfrage-transparenter-polizei-ermittlungen/news/74647.html) oder [4,2 Millionen Handy-Datensätze durch Polizei abgegriffen](https://www.tagesspiegel.de/berlin/handyueberwachung-polizei-pruefte-mindestens-4-2-millionen-handy-datensaetze/6097162.html)

Auch [Demonstranten bzw. deren Kennzeichen werden regelmäßig Opfer der Kennzeichenerfassung](https://www.daten-speicherung.de/data/Berufungsbegruendung_Kfz-Massenscanning_By_2009-11-30.pdf) und die Daten können 10 Jahre oder gar lebenslänglich gespeichert werden (S. 47). Die Versammlungsfreiheit ist durch Überwachung bedroht. Es reicht auch nur zufällig in der Nähe zu sein und man ist im Visier.

Wer weiß weswegen ausgeschrieben ist und aufgrund der Kennzeichenerfassung gestoppt wird. Fiktiver Fall: Euer Freund hat den Lappen abgegeben und die Polizei vermutet er fährt ohne Führerschein? Vielleicht landet er deshalb in der Fahndungsdatenbank. Nehmen wir es einmal an und nehmen weiter an ihr leiht euch nun seinen Wagen. Werdet ihr nun angehalten, freut euch auf eine langwierige Prozedur den Beamten klar zu machen, dass ihr das Auto nicht gestohlen habt. 

Zugegeben dieser Fall klingt sehr konstruiert, aber da die Polizei bei der Anhaltung niemals zugibt, dass sie aufgrund des Kennzeichenabgleichs getan hat, können wir nicht wissen ob es sich in der Realität so zuträgt. Wenn ja: Wäre das nicht übertrieben? Wir wissen nicht wegen welcher Lappalien die Polizei ausschreibt. Früher wurden sogar Autos herausgefischt, weil sie ihre Versicherung nicht bezahlt hatten. 

### Dauerhafte Speicherung von KFZ-Kennzeichen bei Falschtreffer
Wie bei der Funktionsweise geschrieben wurde, gibt es pro Minute einen Fehlalarm. Dieser Fehlalarm verbleibt als MD5 Hash gespeichert [Quelle 1](https://www.daten-speicherung.de/wp-content/uploads/Gericht_Kfz-Massenscanning_By_2012-12-10.pdf) S. 7 und [Quelle 2](https://www.daten-speicherung.de/wp-content/uploads/Land_Schriftsatz_Kfz-Massenscanning_By_2012-01-03.pdf) S. 3

Die Behörden behaupten dieses Vorgehen genüge dem Datenschutz. Ein MD5-Hash lässt sich sehr schnell berechnen. Durch einen Bruteforce-Angriff kann innerhalb kürzester Zeit aus dem Hashwert das Kennzeichen zurückgerechnet werden. Es ist nichts von einem Salted-Hash zu lesen. In der Konsequenz kann dieser Angriff durch eine Rainbow-Table erheblich beschleunigt werden und ein Kennzeichen führt immer zu demselben Hashwert. Selbst ohne Bruteforce-Berechnung oder Rainbowtables genügt ein weiterer Falschtreffer um dem Beamten den MD5-Hash und das zugehörige Kennzeichen zu bekommen. Mit diesem Hash kann er die Datenbank durchsuchen und hat ein detailliertes Bewegungsprofil des zugehörigen Fahrzeugs. Da monatlich 40 bis 50 Tausend Falschtreffer auftreten (da sich die Anzahl der Scanner und der Verkehr erhöht hat, ist mittlerweile mit geschätzten 70 bis 80 Tausend Falschtreffern zu rechnen) bedeutet das im Umkehrschluss die Erstellung von mind. 40 bis 50 Tausend Bewegungsprofilen pro Monat! [Die Behörden behaupten diese Pseudonymisierung sei ausreichend](https://www.daten-speicherung.de/wp-content/uploads/Landesanwaltschaft_Schriftsatz_Kfz-Massenscanning_By_2012-05-03.pdf) S. 16, da es einen „erheblichen und damit völlig unverhältnismäßigen technischen und zeitlichen Aufwand nach sich ziehe“. Mitnichten wie dieser [Grafikkarten Hashcat Benchmark](https://gist.github.com/epixoip/a83d38f412b4737e99bbef804a270c40)! Eine NVidia GTX 1080 Grafikkarte schafft rund unvorstellbare 25 Milliarden Hashes pro Sekunde. Alle denkbaren Kennzeichen sind XXX-YY-ZZZZ, das macht 26 hoch 5 mal 10 hoch 4 = 118.813.760.000 Möglichkeiten. In 4,8 Sekunden hat man alle Möglichkeiten durchprobiert, im Mittel braucht man nur die Hälfte der Zeit, also 2,4 Sekunden. Selbst ein Salted Hash im MD5 Verfahren schützt hier nicht mehr. Es führt lediglich dazu, dass für jeden Hash die Bruteforce-Methode anzuwenden ist. Anmerkung: Korrekterweise sind noch die Kennzeichen XX-YY-ZZZZ, X-YY-ZZZZ usw. hinzuzuaddieren. Die Zeit erhöht sich dadurch jedoch nur unwesentlich (weniger als Verdoppelung, sodass es hier nicht betrachtet wurde).

Auch unter dem Gesichtspunkt der Falschtreffer ist dieser Schutz gegen die Erstellung eines Bewegungsprofils geboten.

## Aktive AKE Schutzmaßnahmen
### AKE Umfahrung über Standstreifen
Es fällt auf je Fahrspur ist ein Scanner verbaut für den Standstreifen keiner. Das bietet Potential ![](https://camo.githubusercontent.com/dea75882d66567a56772f52891db9c016847045c/68747470733a2f2f6769746875622e6769746875626173736574732e636f6d2f696d616765732f69636f6e732f656d6f6a692f756e69636f64652f31663630312e706e67) Also gleich mal ausprobiert. Der Scanner bei Röthenbach löst nicht aus ![](https://camo.githubusercontent.com/6cbdd0c1b5a6649b97e3487dec87adc6e2c50d22/68747470733a2f2f6769746875622e6769746875626173736574732e636f6d2f696d616765732f69636f6e732f656d6f6a692f756e69636f64652f31663630642e706e67) (durch 2 Kameras verifiziert, Rollingshutter-Fehler kann somit ausgeschlossen werden). Mautbrücken über den Standstreifen unerkannt zu passieren klappt übrigens nicht, diese haben eine extra Scaneinheit für den Standstreifen. 

Damit die Umfahrung über den Standstreifen für möglichst wenig Aufsehen sorgt und somit kein unnötiger Verdacht entsteht: Warnblinkanlage einschalten, auf den Standstreifen fahren und leicht bremsen um die Geschwindigkeit zu verringern. Nach Passieren des Kennzeichenscanners ein paar Hundertmeter rollen lassen, anschließend wieder Beschleunigen, Warnblinkanlage ausmachen, links blinken und wieder vorsichtig in den Verkehr einfädeln.

Fazit: Die einfachste Schutzmaßnahme und meist verfügbar: Einfach über den Standstreifen fahren ![](https://camo.githubusercontent.com/dea75882d66567a56772f52891db9c016847045c/68747470733a2f2f6769746875622e6769746875626173736574732e636f6d2f696d616765732f69636f6e732f656d6f6a692f756e69636f64652f31663630312e706e67)

Auf der A6 in Richtung Tschechien bei Wernberg Köblitz befindet sich auf Höhe der Auffahrt ebenfalls ein Scanner. Wer hier erst ziemlich am Ende der Auffahrt auf die Autobahn fährt, sollte auch hier nicht erfasst werden. Hier kann man also ganz legal den Scanner umfahren indem man die Abfahrt und sogleich wieder die Auffahrt nimmt. Wir freuen uns auf ein Video um diesen Sachverhalt zu verifizieren.

Leider ist Umfahren nicht immer möglich. So z.B. bei Waidhaus, dort befindet sich statt eines Standstreifens die Auffahrt und die wird ebenfalls mit überwacht. Bei Marktredwitz fehlen noch Bilder bei Tag. Hier sieht es so aus als ist der Scanner hinter dem Ausfahrtsschild angebracht. Durch die ungewöhnliche Position wird hier eventuell nur die Ausfahrt und die rechte Fahrspur überwacht. Wir hoffen auf eure Bilder um das näher zu beurteilen.

Sollte man von einem Kennzeichenscanner erfasst worden sein und Besuch befürchten, ist immer noch nicht alles verloren. Jetzt heißt es runter von der Autobahn an einer der nächsten Ausfahrten. Je nach Motivation und Langeweile der Polizei besteht das Begrüßungskomitee aus mehreren Streifenwägen, zivilen Fahrzeugen und einem Hubschrauber. Hat man ein sehr auffälliges Auto, das nur selten vorkommt, ist man aus der Luft gut zu erkennen. Wälder, Tiefgaragen, Parkdecks und Ähnliches schützen hier, wenn man genug Zeit mitbringt um abzuwarten, bis sich die Lage beruhigt hat. Es wird hier bewusst keine Empfehlung gegeben in welche Richtung die Fahrt fortgesetzt werden soll, überlege warum... Diese Situation sollte sowieso nie auftreten, da es mit Sonnenschutzfolie und Lasertarnfarbe (siehe unten) wirkungsvolle Schutzmaßnahmen gegen die Kennzeichenerkennung gibt und man diese selbstverständlich getroffen hat, wenn man mit einem Begrüßungskomitee rechnet.


## Laserstörer gegen Kennzeichenscanner
Eine weitere nach außen unsichtbare Möglichkeit, außer man hat eine IR-Kamera wie wir, dem Kennzeichenscanner zu entgehen, stammt aus dem Radarbereich. Da die neuesten Blitzer in Städten ebenfalls mittels Lidar messen und auf demselben Prinzip wie der Kennzeichenscanner basieren, können diese damit theoretisch ebenso wirkungsvoll gestört werden. Dieses System wurde nicht getestet. Die Wirksamkeit kann man sehr leicht festgestellt werden, wenn man bei Nacht durch so eine Anlage fährt und man keinen IR-Blitz auf der Aufnahme feststellt. Anbringung vorzugsweise außerhalb des Wagens um nicht die Scheibe passieren zu müssen. Bei getönten Heckscheiben wird eine Anbringung im Innenraum definitiv nicht funktionieren.

[Laserstörer werden im rdforum diskutiert](https://www.rdforum.org/index.php?threads/24500/) Es gibt wohl kommerzielle Geräte hierfür, welche aber erst so ab 500 € beginnen. Beitrag 7 ist sehr interessant. Dort schreibt ein Nutzer, dass er erfolgreich mehrere von diesen [905nm 5mW IR-Laserdioden](http://www.aixiz.com/store/product_info.php/cPath/65/products_id/359/osCsid/50ae33bfe1f3ffbf187097457e2727e9) einsetzt. Mit 40 Dollar pro Stück sind diese erschwinglich. Geschätzt sind 4 Stück ausreichend um eine solche Anlage sicher stören zu können. Auf der Webseite steht „This laser module is completely self contained and useful for sensor, biomedical and laser radar / **laser radar jamming systems**“

## Passive Schutzmaßnahmen gegen Kennzeichenerfassung
### Sonnenschutzfolie
Schauen wir uns diese Bilder an 

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Schutzfolie/Kennzeichen%20unter%20IR950%20_V.jpg) 
![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Schutzfolie/IR950%20Frontal%20_V.jpg)

Hier wurde das Kennzeichen unter IR-Licht mit 950 nm Wellenlänge und einer speziellen Schutzfolie gegen IR abgebildet. Die Folie lag auf dem Kennzeichen und war nicht geklebt. Beim 2. Bild hatte die Kamera nicht auf SchwarzWeiß umgeschaltet, daher die violette Farbe. Auffällig am ersten Bild ist die linke weiße Fläche. Wo sonst die blaue Europafarbe mit den Sternen ist, ist unter IR950 das Kennzeichen hochreflektiv und unterscheidet sich nicht vom restlichen Bereich.

Zur Unkenntlichmachung des restlichen Kennzeichens wurde diesen Bereiche blau eingefärbt, sonst könnte man das Schwarze in der Mitte damit verwechseln. Sollte die Folie der Rennleitung auffallen, [ist man mit „nur“ 65 € dabei, aber kein Punkt](https://www.bussgeldkatalog.org/autokennzeichen/) Natürlich nur sofern man die Anbringung zugibt ![](https://camo.githubusercontent.com/02343e80ed1cedb5796be7b103c575177b03ec6f/68747470733a2f2f6769746875622e6769746875626173736574732e636f6d2f696d616765732f69636f6e732f656d6f6a692f756e69636f64652f31663630392e706e67). Euer Fahrzeug parkt doch öfters auf öffentlichem Grund, die Folie muss jemand Fremdes angebracht haben um euch eins auszuwischen. Sie ist euch gar nicht aufgefallen…. ![](https://camo.githubusercontent.com/dea75882d66567a56772f52891db9c016847045c/68747470733a2f2f6769746875622e6769746875626173736574732e636f6d2f696d616765732f69636f6e732f656d6f6a692f756e69636f64652f31663630312e706e67) (Die Einmalhandschuhe beim Aufkleben nicht vergessen)


### Aussehen der Folie für das menschliche Auge:

Ohne Blitz frontal:

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Schutzfolie/Ohne%20Blitz%20frontal%20_V.jpg)

Mit Blitz frontal:

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Schutzfolie/Handyblitz%20Blitz%20frontal%20_V.jpg)

Ohne Blitz seitlich:

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Schutzfolie/Ohne%20Blitz%20seitlich%20_V.jpg)

Mit Blitz seitlich:

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Schutzfolie/Handyblitz%20seitlich%20_V.jpg)

Um das Vorhandensein der Folie deutlich erkennbar zu machen wurde Diagonal ein Streifen kennzeichenseitig angebracht.

Wenn das Kennzeichen komplett mit der Folie bespannt ist, fällt sie kaum auf.
### Die Sonnenschutzfolie gegen automatisierte Kennzeichenerfassung
Die Folie ist eigentlich fürs Fenster zum Sonnenschutz gedacht und hervorragend für Datenschutzzwecke geeignet. Die IR-Rückweisung beträgt 97 %, sichtbares Licht wird dabei nur wenig blockiert, sodass die Folie bei Tag kaum auffällt [Datenblatt 3M Prestige 70 Exterrior Sonnenschutzfolie](https://multimedia.3m.com/mws/media/1435984O/produktinformation-3m-prestige-70-ext-window-film.pdf)

Die Folie ist sehr günstig, [40x40 cm kosten aktuell 9,90 €](http://dasfolienkartell.de/Gebaeudefolien/Sonnenschutzfolien/3M-Prestige-70-Exterior.html) und reicht für 2 Kennzeichen  Woanders eventuell sogar noch günstiger erhältlich. Es gibt eine Exterior und eine Interior Variante. Exterior ist für den Außeneinsatz. Die Bilder entstanden mit der Exterior Variante. 

Sofern die Aufnahmekameras der Kennzeichenscanner über keinen IR-Filter verfügen (sichtbares Licht ausblenden) könnte durch die Kennzeichenbeleuchtung das Kennzeichen schwach lesbar sein. Vermutlich ist der Kontrast jedoch so gering, dass die automatisierte Leseerkennung versagt, die [Fehlerquote beträgt **ohne** Folie bereits 93 % bis 99,8 %](https://www.buzzfeed.com/de/marcusengert/kennzeichenerfassung-der-polizei-funktioniert-nicht). Die Wahrscheinlichkeit eines lesbaren Kennzeichens reduziert sich weiter, da durch die hohe Geschwindigkeit eine kurze Belichtungszeit und dadurch ein massiver Infrarotblitz benötigt wird. Dieser Blitz sollte die Kennzeichenbeleuchtung stark überstrahlen. 
Ohne IR-Filter im Kennzeichenscanner wäre die Lesbarkeit durch den Folienschutz bei Tag wahrscheinlich kaum beeinträchtigt, dann muss zur aktiven Maßnahme gegriffen werden. Da der Infrarotblitz auch bei guten Lichtverhältnissen tagsüber ausgelöst wurde ist jedoch von einem eingebauten IR-Filter auszugehen. 

## Lasertarnfarbe Veil Laserstealth gegen Kennzeichenerfassung
Diese Methode haben wir nicht getestet. Das Produkt kann aktuell unserer Kenntnis nach nur direkt beim Hersteller aus Amerika bezogen werden, Versand nach Deutschland ist möglich. 

Veil Laserstealth wurde entwickelt um den Laserstrahl von Radarpistolen deutlich weniger zu reflektieren und so bei einer Lasermessung mehr Zeit zur Erkennung zu haben. Der Hersteller bietet ein interessantes Bild eines Kennzeichens unter IR-850 an. Wie man sieht, sieht man das Kennzeichen nicht. Die Kennzeichenscanner blitzen bei 940 nm. Es ist davon auszugehen, dass Veil Laserstealth auch unter dieser Wellenlänge das Kennzeichen unlesbar macht. Wir freuen uns über eure Rückmeldungen. Veil Laserstealth fällt wahrscheinlich mit bloßem Auge überhaupt nicht auf. Es wird auch billiger, wenn die Rennleitung es jemals feststellen sollte. Man kann euch höchstens vorwerfen, dass das Kennzeichen nicht den Vorschriften entspricht und damit gibt’s 10 €, solltet ihr das zugeben, siehe oben zur Folie.

Veil Laserstealth auf die Windschutzscheibe aufgetragen verhindert (sofern unter 940 nm wirksam), dass an Mautbrücken Aufnahmen von eurem Gesicht angefertigt werden und lässt im Sommer weniger Hitze ins Innere gelangen. Die Auftragung könnte zu Schlieren, besonders bei Regen und allgemein schlechterer Sicht führen. Bevor aussagekräftige Tests durchgeführt wurden, raten wir von der Aufbringung auf Scheiben ab.

Der Hersteller behauptet, der Schutz wäre dauerhaft und wäscht sich nicht ab. Er sollte trotzdem regelmäßig durch Kontrolle (insbesondere bei Auftragung auf die Windschutzscheibe) unter IR-Licht überprüft werden. 

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Schutzfolie/Veil.jpg)
Quelle https://www.stealthveil.com/

## Geeignet zur Unbrauchbarmachung von Blitzern

Uns verwundert, dass über diese Folien oder die Lasertarnfarbe noch nie im Radersektor berichtet wurde. So sollten sie doch effektiv die LIDAR Erfassung der modernen Blitzersäulen und letztendlich den Blitz (hier mit sichtbarem Licht) verhindern, insbesondere, weil [das Anbringen lediglich eine Ordnungswidrigkeit darstellt ](https://www.waz-online.de/Gifhorn/Gifhorn-Stadt/Bekenner-Mail-zu-Blitzer-Streich). Klar das ist verboten und sollte man nicht tun, aber wütende Autofahrer zerstören des Öfteren Blitzer auf brachiale Art und Weise. Die Behörden bekommen das dann natürlich sofort mit. Ebenso, wenn man den Blitzer mit Abdeckfolie, Mülltüten oder Ähnlichem verhüllt. Oder wurde die Folie schon öfters eingesetzt und außer ausbleibenden Einnahmen fiel niemandem etwas auf?

## Schutz vor Tunnelblitzern

In Tunneln wird sogar mit IR-Licht geblitzt, nennt sich dann „Blackflashtechnologie“. Zusätzlich an der Windschutzscheibe angebracht verhindern sie dann auch noch Fahreraufnahmen. Der TÜV darf die Folie natürlich nicht sehen. 



## Exkurs: Umgehung von Mautsäulen und Mautbrücken
Die neuen blauen Mautsäulen sind in der Nacht schwach rot leuchtend sichtbar. Demnach sollte das 850 nm Infrarotlicht sein. Bei 850 nm wirkt die Folie nicht mehr ganz so effektiv, aber auch hier sollte die automatisierte Erkennung fehlschlagen. Da Mautbrücken auf derselben Infrarottechnik wie die Kennzeichenscanner basieren, funktionieren jedoch alle zu IR-Licht beschriebenenen Maßnahmen analog. 

Senkrechte Aufnahme mit IR-Licht und Kamera auf einer Ebene:

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Schutzfolie/IR850%20Frontal.jpg)

Seitliche Aufnahme:

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Schutzfolie/IR850%20seitlich.jpg)

Interessant: Der Europabereich links ist hier leicht gräulich zu erkennen.

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Schutzfolie/IR850%20seitlich2.jpg) 

Ohne Umschalten auf SchwarzWeiß ist das Kennzeichen besser zu erkennen.


