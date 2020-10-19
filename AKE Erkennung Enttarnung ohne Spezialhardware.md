---
title: AKE Erkennung / Enttarnung ohne Spezialhardware
permalink: /AKE-Erkennung-Enttarnung-ohne-Spezialhardware
---
# AKE Erkennung / Enttarnung ohne Spezialhardware
Kennzeichenscanner zu enttarnen ist jetzt noch einfacher. Für die Erkennung der Kennzeichenscanner ist nicht notwendigerweise eine Spezialhardware erforderlich.
## Kennzeichescanner Erkennung per Auge
Bei der einfachsten Erkennungsmöglichkeit sucht man nach den Scannern per bloßem Auge. Jeder Autobahnfahrer hat schon Mautbrücken gesehen und die Aufnahmeeinheiten. Wenn solche Einheiten die Fahrzeuge von hinten erfassen, handelt es sich um Kennzeichenscanner. Auch unsere [Kennzeichenscanner Karte](https://umap.openstreetmap.fr/en/map/ake-deutschland_234435) gibt Inspirationen. An manchen Anlagen erhöhen die weißen Technikkästen die Auffälligkeit, wie bei Hengersberg oder Röthenbach.

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/AKE-Bayern-Bilder/A3-Hengersberg-Richtung-Regensburg.jpg)

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/AKE-Bayern-Bilder/A9-R%C3%B6thenbach-Richtung-Bayreuth.jpg)

## Nutzung von Smartphones oder Webcams zur AKE Erkennung
### Aufzeichnung der Fahrt
Man kann die Fahrt mit einer herkömmlichen Kamera aufzeichnen. Beim Filmen durch die Windschutzscheibe wird die Kamera leicht nach links gedreht um den Gegenverkehr optimal aufzunehmen. Dashkameras, sofern drehbar, sind ideal geeignet und natürlich filmt man auch durch die Heckscheibe. Man sieht sich zuerst das Video der Kamera von vorne an, sind hier stellen des Gegenverkehrs durch Brücken oder ähnliches verdeckt, greift man zum Video der „Rückfahrkamera“. Da man beim Filmen durch die Windschutzscheibe die Brücke kommen sieht, sind diese Videos wesentlich schneller und angenehmer durchzusehen.

### Enttarnung des Kennzeichenscanners durch IR-Blitz bei Nacht
Um nun sicher zu gehen, dass es sich um einen Kennzeichenscanner handelt, müssen wir den IR-Blitz aufzeichnen.

Manche Smartphones oder Webcams verfügen über einen so schlechten IR-Filter, dass der IR-Blitz damit sichtbar gemacht werden kann. Bei einem geeigneten Smartphone kann man es in eine Handyhalterung spannen. Sehr geeignet erwies sich für uns diese [Handyhalterung](https://www.amazon.de/gp/product/B078NVJQ2X) Das Handy und die Halterung werden jeweils um 180° gedreht eingespannt mit dem Display in Richtung des Haltearms. Es ist so in einem perfekten Aufnahmewinkel minimal nach oben hin ausgerichtet. Mit einer Dashcam-App fürs Handy wird sogar noch die GPS-Position mit integriert, ähnlich wie bei der Raspberry PI Scan-Rec Anlage.

## Zur AKE Detektion geeignete Kameras
Sehr gut geeignet ist eine **Logitech C920 HD Webcam** im Lieferzustand. Mit ihr ist sogar noch das Lidar deutlich zu erkennen. 
Es gibt sogar Anleitungen zum Entfernen des IR-Filters der C920 um klare IR-Aufnahmen zu erhalten. Wer nicht genau weiß was er da tut, empfehlen wir lieber zur Pi NOIR-Kamera zu greifen.

Ebenfalls gut geeignet ist ein **Samsung Galaxy S7**

## Erkennung geeigneter Kameras zur Kennzeichenscannerdetektion
Auch wenn alle bisher getesteten Kameras das Licht einer IR-Fernbedienung angezeigt haben, eignen sie sich leider nicht alle für die Erkennung.
Wir haben bisher nur 3 verschiedene Kameras Live am Kennzeichenscanner getestet. Wir empfehlen sie zuvor an einer Mautbrücke zu testen. 
### Nicht funktionierende Methoden
Eine Methode um die IR-Tauglichkeit zu testen bestand daran die Kamera und parallel dazu eine IR-Fernbedienung in 5 cm Abstand eine weiße Wand zu halten. Während bei einem Galaxy S7 hier deutlich etwas zu sehen war, zeigte sich bei der Logitech C920 kaum Reaktion. Im Praxiseinsatz war die C920 jedoch etwas besser als das Galaxy S7, da das Lidar hier deutlicher sichtbar war.

### Beste Eignungsprüfung zur AKE Detektion
Wir haben bisher nur 3 Kameras getestet und der zuverlässigste Indikator ob man den IR-Blitz sehen wird, sind Farbverfälschungen beim Filmen einer Kerzenflamme aus wenigen Zentimetern (ca. 10 – 20 cm). Gibt es hier Farbveränderungen, ist die Kamera geeignet.

Beispiele:
Galaxy S7:

![](https://github.com/Scan-Rec/Scan-Rec/raw/master/Ressourcen/Nicht-IR-Kameras/Artefakte%20Galaxy%20S7%20isoliert.jpg)

Logitech C920 (zur besseren Sichtbarkeit wurde die Farbsättigung erhöht):

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Nicht-IR-Kameras/Logitech%20C920%20Artefakte%20isoliert.jpg)

## Beispielbilder normaler Kameras
Zunächst die Bilder einer wenig geeigneten Kamera. Ohne zu wissen wo der IR-Blitz auftritt, besteht kaum Chance den IR-Blitz zu erkennen. Ob ihr ihn seht hängt sehr von eurem Monitor und Blickwinkel ab. Wenn ihr ihn nicht seht, im nachfolgenden Bild ist er markiert.

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Nicht-IR-Kameras/SchlechteIR-Kamera.jpg)

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Nicht-IR-Kameras/SchlechteIR-Kamera_Markiert.jpg)

Bei den nachfolgenden Bildern mit tauglichen Kameras wurde der rotmarkierte Abschnitt am Rand nochmals vergrößert abgebildet. Aufgrund der geringeren IR-Empfindlichkeit ist das Lidar auf wesentlich weniger Einzelbildern zu sehen als bei der NOIR Kamera und auch nicht gemeinsam mit dem IR-Blitz auf einem Bild.

Galaxy S7 Lidar:

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Nicht-IR-Kameras/Galaxy%20S7%20Lidar.jpg)

Galaxy S7 IR-Blitz:

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Nicht-IR-Kameras/Galaxy%20S7%20IR-Blitz.jpg)

Es sieht so aus als wird der IR-Blitz von 2 IR-Laserdioden oder IR-Panels erzeugt.


C920 Lidar:

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Nicht-IR-Kameras/Logitech%20C920%20Lidar.jpg)

C920 IR-Blitz:

![]( https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/Nicht-IR-Kameras/Logitech%20C920%20IR%20Blitz.jpg)

Zum Vergleich IR-Blitz mit der NOIR-Kamera:

![](https://raw.githubusercontent.com/Scan-Rec/Scan-Rec/master/Ressourcen/BlitzSerie/1.jpg)

