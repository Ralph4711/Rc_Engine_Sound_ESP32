# Dies ist ein Arduino RC Motor Sound & Licht Controller für den ESP32

[![GitHub latest release version](https://img.shields.io/github/v/release/TheDIYGuy999/Rc_Engine_Sound_ESP32.svg?style=flat)](https://github.com/TheDIYGuy999/Rc_Engine_Sound_ESP32/releases/latest)
[![Github All Releases download count](https://img.shields.io/github/downloads/TheDIYGuy999/Rc_Engine_Sound_ESP32/total.svg?style=flat)](https://github.com/TheDIYGuy999/Rc_Engine_Sound_ESP32/releases/latest)
[![GitHub contributors](https://img.shields.io/github/contributors/TheDIYGuy999/Rc_Engine_Sound_ESP32.svg?style=flat)](https://github.com/TheDIYGuy999/Rc_Engine_Sound_ESP32/graphs/contributors)

Er basiert auf der ATmega 328 Version: https://github.com/TheDIYGuy999/Rc_Engine_Sound
und auf bitlunis Halloween Beispiel: https://github.com/bitluni/MotionPumpkin

Verdrahtungs- und Software-Installationsanweisungen sehe weiter unten. Arduino IDE oder Visual Studio Code (mit Platform IO-Erweiterung) werden unterstützt.

Video serie: https://www.youtube.com/playlist?list=PLGO5EJJClJBCjIvu8frS7LrEU3H2Yz_so

************************************************************************
Die Änderungen finden Sie im [Changelog](documentation/Changelog.md).
************************************************************************

Diskussions- und Support-Thread (in Deutsch & Englisch)findet Ihr hier: https://www.rc-modellbau-portal.de/index.php?threads/esp32-arduino-rc-sound-und-licht-controller.7183/

Komplett montiert, getestet und arbeitende 30-polige SMD-Version mit Schaltmodus PSU & Display-Anschluss. 
Bestellen Sie es hier: https://www.pcbway.com/project/shareproject/Arduino_RC_engine_sound_light_controller_for_ESP32_a9334731.html
![](documentation/pictures/30pinSmdSwitchModeVersion.png)

Neu: STL-Daten für ein schönes 3D-gedrucktes Gehäuse ist hier verfügbar:
https://thediyguy999.github.io/TheDIYGuy999_ESP32_Web_Flasher/products.html
![](documentation/pictures/ESP32SoundAndLightController.png)

Neu: Kompakte Ausführung des Kontrollers für Anhänger oder Traktor:
https://thediyguy999.github.io/TheDIYGuy999_ESP32_Web_Flasher/products.html
![](documentation/pictures/ESP32TrailerController.png)

Neuer: RZ7886 7A ESC:
https://thediyguy999.github.io/TheDIYGuy999_ESP32_Web_Flasher/products.html
![](documentation/pictures/RZ7886top.png)

Neu: Wireless-Konfigurationswebsite 192.168.4.1
![](documentation/pictures/Configuration.png)

Neu: LCD-Armaturenbrett (Original von Frevic)
![](documentation/pictures/dashboard2.JPG)
https://www.facebook.com/profile.php?id=100066616574355

LCD-Armaturen-Dashboard (original by Gamadril)
![](documentation/pictures/dashboard.JPG)

Vollständig montiert, getestet und funktionierende 30-polige SMD-Version, hergestellt und vormontiert von https://www.pcbway.com
![](documentation/pictures/30pinSmdVersion.jpg)

Vollständig montiert, getestet und arbeitend 30-polige Durchgangslochversion
![](documentation/pictures/30PinAssembled.jpg)

Kompakte Ausführung für Bagger (nur IBUS & Sound, geliefert von 6V BEC)
![](documentation/pictures/compact1.JPG)
![](documentation/pictures/compact2.JPG)
![](documentation/pictures/compact3.JPG)

## Eigenschaften:
- Einzigartige Fahrzeug-Massenträgheitssimulation (verbinden Sie Ihre Raupenart ESC mit Pin 33). Die Drosselabgabe wird beim Schalten eines mechanischen 3-Gang-Getriebes für sanftes Schalten, Gangschutz und realistischen Klang verändert. Funktioniert gut mit TAMIYA 3 Geschwindigkeitsübertragungen. Sollte auch mit Raupen 2 Geschwindigkeitsübertragungen funktionieren. Der ESC wird von einer Zustandsmaschine mit folgenden Zuständen gesteuert: Vorwärts & Rückwärtsfahren (Variable Beschleunigung, je nach Drosselstellung), Neutral, Vorwärts- und Rückwärtsbremsung (variable Verzögerung mit Feingranularität, nach "Reverse Gas"-Position). Es ermöglicht auch, die Bremslichter, den Bremston, das Rückfahrlicht und den Rückwärtston richtig zu steuern. Beschleunigung & Verzögerung (Küsten & Bremsen) sind für jedes Getriebe separat einstellbar, um maximalen Realismus zu gewährleisten. 
- Einzigartige "virtuelle Kupplung" ermöglicht es, den Motor unter eine einstellbare ESC-Ausgangsdrehzahl zu drehen. Oben greift die Kupplung ein und sorgt dafür, dass der Motorsound mit dem Raddrehzahlpunkt übereinstimmt. Klingt und verhält sich einfach super in Kombination mit einem Schaltgetriebe!
- Simuliertes Automatikgetriebe mit Drehmomentwandler (wenn Ihr Fahrzeug kein reales Schaltgetriebe hat)
- Simuliertes Doppelkupplungsgetriebe
- simuliertes, manuell geschaltetes 3-Gang-Getriebe (neu ab v5.5)
- Virtueller, schaltbarer Neutraler Gang ermöglicht es, den Motor zu drehen, während er stillsteht
- Jake-Bremse (simulierte pneumatische Motorbremse, hauptsächlich in US-Lkw)
- Verfolgter Modus (Dual-Gas-Eingang auf CH2 & CH3, für Tanks, Bagger usw. Keine ESC-Steuerung unterstützt in diesem Modus. (Neu ab v4.5)
- Tankkanone Sound & Flash (Neu in v4.6)
- Auslösen mehrerer Verriegelungs- und Nicht-Verriegelungsaktionen (Sounds, Lichter) pro analogem Kanal unter Verwendung der rcTrigger-Bibliothek (Neu in v4.7, noch experimentell)
- Viele wählbare Geräusche: Motorkurbeln, Motorleerlauf, Motordrehen, Turbo-Jammern, Diesel-Zündung "Knock", Wastegate-Ventil, Hupen, Sirenen, Rückfahr-Piep, Luftbremse, Feststellbremse, Gangschaltung usw.
- Realistischer Motorsound wird im Handumdrehen von bis zu 4 Sounds miteinander vermischt: Motorleerlauf, Turbo, Wastegate (alle mit variabler Abtastrate), Diesel-Zündklopfen (feste Abtastrate, so dass es in der Tonhöhe nicht variiert)
- Last (Drosselposition) abhängige Lautstärkegeräusche: im Leerlauf, Drehzahl, Dieselklopfen
- Motor-RPM-abhängige Lautstärkeklänge: Turbo, Wastegate
- Dutzende von Engine- und anderen Sounds enthalten, können Sie auch Ihre eigenen komponieren, mit Audacity und Bitlunis Conversion Tool (Link oben)
- Motordrehzahlbereich und Trägheit einstellbar, Lautstärke aller Sounds einstellbar, Motorgeräusche getrennt für Last und Leerlauf.
- Viele andere Parameter können angepasst werden. Alle Anpassungen sind in "AdjustmentsXyz.h" leicht zugänglich
- Sounddateien bis 22'050Hz, 8bit, mono können verwendet werden
- Kompatible Eingangssignale: PWM, PPM, SBUS (invertierte & nicht invertierte Signale), IBUS
- Funktioniert am besten mit einem PAM8403 Verstärkermodul, angeschlossen mit Pin 25 & 26, über 10kOhm Widerstände und ein 10kOhm-20kOhm Potentiometer (siehe Schaltplan unten)
- Die Motordrehzahl wird nach RC-Signaleingang auf Pin 13 *** VORSICHT, 3,3V max. auf allen Pins berechnet! *** 330 Ohm Widerstände auf allen empfohlenen I/O Pins!
- Nichtlineare Drosselkurven können in "curves.h" erzeugt werden
- Lichteffekte: Scheinwerfer (High & Low-Beam), Rückleuchten, Bremslichter, Nebelscheinwerfer, Dachbeleuchtung, Kabinenleuchten, Rückfahrleuchte, Blinker (Blinker), Warnblinker, blaues Licht etc. (max. 12 Ausgänge)
- Motorschwingungssimulation, mit einem Schüttlermotor mit exzentrischem Gewicht: Starke Vibration beim Kurbeln, mittlerer Vibration, leicht beim Drehen
- Einstellbare Lautstärke (über Fernbedienung)
- Verwenden eines ESP32, die CPU-Frequenz muss auf 240MHz eingestellt sein
- Eagle Schaltplan & Board-Datei enthalten. Vorgefertigte Gerber-Dateien ermöglichen es Ihnen, Ihr Board einfach zu bestellen.
- Lieferumfang: einfach zu bedienen .wav zu .h Sounddatei-Konverter
- Kanäle können einfach über die "remoteSetup.h" zugewiesen werden
- Vorgefertigte Konfigurationsprofile für Flysky FS-i6X und Arduino Mirco RC remote (neu ab v.5.5)
- Variable Länge für Horn & Sirene, mit Loop-Bereich in den Sound-Dateien (neu ab v5.6)
- BUS-Decoder für Servo- und Schaltservo (Servos mit CH1 & CH2)-Pins verbinden
- Sattelplatte (5. Rad) Servo kann an die CH4-Pins angeschlossen werden (ACHTUNG nicht im PWM-Kommunikationsmodus)
- TAMIYA Trailer-Präsenzschalter kann an Pin 32 angeschlossen werden (abhängig von der Einstellung "#define THIRD_BRAKELIGHT" auf der Registerkarte "6_adjustmentsLights.h")
- Unterstützung für nichtlineare Gas- und Lenkkurven (für eine genauere Steuerung um die Mittelposition). Verwenden Sie "EXPONENTIAL_THROTTLE" & "EXPONENTIAL_STEERING" in "2_adjustmentsRemote.h"
- Unterstützung für HOBBYWING Quicrun Fusion Motor / ESC combo. Verwenden Sie "#define QUICRUN_FUSION" in "3_adjustmentsESC.h"
- Unterstützung für Winde, verbunden mit CH3 (nur BUS-Kommunikationsmodus). Verwenden Sie "#define MODE2_WINCH" in "7_adjustmentsServo.h" Die Taste Mode 2 wird dann verwendet, um zwischen Horn / Sirenen-Kontrolle und Windensteuerung über CH4 zu wechseln. Die Winde wird von einer alten RC-Servo-Treiberplatine gesteuert. Die Geschwindigkeit und die neutralen Einstellungen werden mit "CH3L", CH3C" und CH3R" Positionen durchgeführt.
- Unterstützung für LCD-Dashboard
- Unterstützung für 2812 Neopixel LED (GPIO0)
- Unterstützung für Hydlaulikbagger (Hydraulikpumpe, Hydraulikfluss, Spurraspelgeräusche). Verwenden Sie #define FLYSKY_FS_I6S_EXCAVATOR profile for remote
- ESP-NOW based 2,4 GHz Wireless Trailer Control Unterstützung
- Anstelle eines Standard-Crawler-Typs RC ESC kann ein RZ7886-Motortreiber-IC verwendet werden
- Batterie-Niedrig-Spannung-Schutzoptionen
- Schaltbarer Crawler-Modus (mit nur minimaler virtueller Trägheit)
- Webseite der drahtlosen Konfiguration 192.168.4.1

## Auf der Todo-Liste:
- Kurvenleuchten (auf den Beacon-Ausgängen)
- Warnblinker einschalten, wenn der Motor im AUTO_LIGHTS-Modus ausgeschaltet wird

## Bekannte Themen:
- Arduino IDE 1.8.7 oder älter wird nicht unterstützt und verursacht Compilerfehler!
- Der ESP32 funktioniert nicht unter macOS Big Sur 11.x, aber dieses Problem kann leicht behoben werden, wie es hier beschrieben wird: Big Sur Fix (für v1.04)
- macOS Monterey 10.3 enthält Python 2 nicht mehr. Für Arduino IDE müssen Sie Python 3 installieren und den Pfad in pPlatform.txt ändern, gemäß:
https://forum.arduino.cc/t/mac-os-update-killed-esp32-sketch/969580/24

## So erstellen Sie neue .h-Sounddateien:

### Audacity:
- Importieren Sie die gewünschte WAV-Sounddatei in Audacity
- Konvertieren Sie es in Mono, wenn nötig
- Wählen Sie unten links die Projektfrequenz 22'050Hz aus
- Suchen Sie nach einem zyklischen Muster im Leerlauf (die Menge an Zündimpulsen ist normalerweise die gleiche wie die Zylinderzahl), schneiden Sie die "Leerlauf" -Probe auf genau diese Länge, werfen Sie einen genauen Blick auf die Nulldurchgänge, um Klickgeräusche zu vermeiden. Die lauteste Spitze sollte immer am Ende der Probe sein.
- Machen Sie das gleiche mit dem "Rev" -Sound. Es wird 2 - 4 mal kürzer sein als die "Leerlauf" -Probe, abhängig vom Motor und der Drehzahl der "Rev" -Probe
- Ändern Sie die "Rate" (Dropdown auf der linken Seite der Probe) der "rev" -Probe, bis die Länge die gleiche ist wie in der "Idle"-Probe. Das ist sehr wichtig!
- Duplizieren Sie einen Teil der "rev" -Probe (der mit der ursprünglichen, unveränderten "Rate" -Geschwindigkeit). Das ist die "Knock" -Probe. Schneiden Sie diese auf die maximale Länge: "Idle" Länge / Anzahl der Zylinder / Drehzahlbereich "MAX_RPM_PERCENTAGE" (normalerweise 2 - 4 oder 200 - 400%)
- Anpassen der Lautstärke aller Samples, so dass der gesamte Dynamikbereich verwendet wird
- Vielleicht möchten Sie auch High-Pass- oder Tiefpassfilter anwenden, um den Klang zu verfeinern
- Wählen > Audio exportieren > ausgewähltes Audio > WAV > 8-bit-PCM

### Konvertieren Sie die .wav-Datei mit dem modifizierten Konvertierungstool (neu ab v5.2):
![](pictures/converter.png)
- Öffnen Sie den mitgelieferten "Audio2Header.html" Konverter in Ihrem Browser. Es befindet sich im Ordner "Tools"
- Anpassen des Exportdateiformats (keine Änderungen erforderlich)
- Wählen Sie den Exportdateityp, abhängig von dem Sound, den Sie konvertieren (Idle, Rev, Horn usw.)
- Öffnen Sie die zu konvertierende WAV-Datei
- eine .h-Datei wird generiert und heruntergeladen
- Verschieben Sie es in Ihr "sketch/vehicles/sounds"-Verzeichnis

### Fügen Sie die neue Header-Datei mit Ihrem Sound in Ihre Fahrzeugvorgabe ein, passen Sie die Einstellungen an, bis Sie zufrieden sind:
- diese .h-Datei in "Adjustments.h" > "yourVehiclePreset.h" einschließen
- Klopf-Sound-Einstellungen: 
  - "dieselKnockInterval" = Anzahl der Zylinder
  - uncomment "V8" für V8-Motoren, R6 für Inline-6-Motoren oder "V2" für V2 (Harley) Motoren
  - "dieselKnockAdaptiveVolumePercentage" (wie laut die "stillen" Klopfimpulse mit den lauten verglichen werden) einstellen, nur aktiv, wenn definiert "V8", "R6" oder "V2"
- Spielen Sie mit den anderen Volumes, Start-, End- und Switch-Points, bis Sie glücklich sind
- Der "rev"-Sound ist optional und nur aktiv, wenn "REV_SOUND" definiert ist (// entfernt)
- Passen Sie den Übergang vom "Idle" zum "rev"-Sound mit "revSwitchPoint", "idleEndPoint", "idleVolumeProportionPercentage" an. Dieser Schritt ist sehr wichtig und kann einen großen Unterschied machen!

### Kompilieren Sie die neue Skizze:
- Kompilieren und Hochladen der Skizze in Arduino IDE
- Der neue Sound sollte nun fertig sein

## Schematisches Beispiel (PDF für aktuelle Version verwenden!):
![](documentation/pictures/schematic.png)

## PCB
### Enthaltene PCB-Dateien:
- Siehe Hardware-Ordner

### Empfohlener Hersteller:
https://www.pcbway.com (einschließlich SMD-Montagedienst, verwenden Sie Gerbers.zip für Board, es enthält auch Stückliste. xlsx und CPL.xlsx, wenn Sie den SMT-Montagedienst verwenden möchten) So bestellen Sie vormontierte Platten siehe /Eagle_PCB/So bestellen Sie Ihre PCB.pdf

### Der einfachste Weg, die 30pin SMD-Version mit Display-Anschluss zu bestellen:
https://www.pcbway.com/project/shareproject/Arduino_RC_engine_sound_light_controller_for_ESP32_a9334731.html

### Montageanleitung (für die 30-polige SMD-Version ohne Display-Anschluss):
https://www.youtube.com/watch?v=csQgTfxRd8Y&t=2s

### Montage-Tutorial (für die 36-Pin-Version):
https://www.youtube.com/watch?v=Vfaz3CzecG4&list=PLGO5EJJClJBCjIvu8frS7LrEU3H2Yz_so&index=13

## Verdrahtung:
### Bevor Sie beginnen:
- ACHTUNG dieses Gerät ist nicht vor falscher Polarität geschützt!
- Verwenden Sie immer Reihenwiderstände für LED-Schalter (außer für die Originale TAMIYA Anhängerplatine)
- Maximale Eingangsspannung auf "Sig"-Pins = 3,3V (vorsichtig mit sehr alten Empfängern, die 5V liefern können)
- Es wird Dringend empfohlen, eine Sicherung zwischen Ihrem Akku und dem Soundcontroller / ESC zu verwenden

### Versorgung für Audioverstärker, Shakermotor und LED:
- Verwenden Sie ein Y-Kabel zwischen Ihrem Akku, Ihrem ESC und dem "X1"-Anschluss. Der Batteriespannungsbereich beträgt 7 - 12,6V

### Spannung für den ESP32:
- Der ESP32 wird nicht über den "X1"-Anschluss versorgt
- Er kann über den Micro USB-Header versorgt werden
- oder durch die +V- und GND-Pin-Reihe auf der Oberseite der Platine (die Spannung kommt normalerweise vom BEC in Ihrem ESC, der an den "ESC" -Header angeschlossen werden muss)

### ESC-Verdrahtung:
- Verbinden Sie einen Hobbywing 1080 ESC mit dem ESC-Header (GND, V+ und Sig)
- Passen Sie die ESC-Parameter mit der Programmierkarte an, wie oben in "Adjustments.h" beschrieben
- Ich empfehle keinen anderen ESC
- Der ESC wird vom Sound-Controller und nicht direkt vom Empfänger gesteuert. Dies ermöglicht die Verwendung der einzigartigen "virtuellen Trägheit" -Funktion. HINWEIS: Verwenden Sie diese Funktion auf eigene Gefahr! Ich bin nicht verantwortlich, wenn irgendwelche Schäden verursacht werden. Es läuft sehr stabil und ich hatte nie ein Problem, aber man weiß nie.
- "escPulseSpan" kann verwendet werden, um die Höchstgeschwindigkeit Ihres Fahrzeugs zu begrenzen. 500 = nicht begrenzt, alles über 500 begrenzt die Höchstgeschwindigkeit

### Empfängerverdrahtung für PWM-Servosignale (die gängigste Verdrahtung):
- Kanalzuordnung nach "remoteSetup.h" und remoteSetup.xlsx", einfach einstellbar (neu ab v5.5). Es ist wichtig, die Drähte entsprechend der Kanalzuordnung anzuschließen
- CH5 & 6 kommen über die "35" & PPM"-Header
- Mindestens ein CH muss über einen 3-Pin-Draht angeschlossen werden, damit auch GND und V+ angeschlossen sind (Empfangsversorgung)
- CH1 - 4 Header sind Paare, parallel verdrahtet. Dies ermöglicht die Vorspeisung von Servosignalen, wodurch Y-Kabel entfallen
- Beachten Sie, dass Sie die Konfiguration wie unten beschrieben ändern müssen, wenn Sie diese Verdrahtungsmethode verwenden möchten

### Empfängerverdrahtung für PPM-Signale:
- Interne Kanalzuordnung wie oben
- Schließen Sie einen 3-Pin-Kabel aus Ihrem Receiver-PPM-Header an den RX (ab v5.5 geändert, war PPM) Header auf dem Sound-Controller (Sig, V +, GND) an
- Beachten Sie, dass Sie die Konfiguration wie unten beschrieben ändern müssen, wenn Sie diese Verdrahtungsmethode verwenden möchten
- In diesem Modus können 8 Kanäle gelesen werden

### Empfängerverkabelung für SBUS-Signale (empfohlen):
- Interne Kanalzuordnung wie oben
- Schließen Sie einen 3-poligen Draht von Ihrem Receiver SBUS-Header an den SBUS-Header am Soundcontroller (Sig, V+, GND) an
- Der "Sig"-Pin auf dem SBUS-Header ist 5V tolerant
- In diesem Modus können 13 Kanäle gelesen werden

### Empfängerverkabelung für IBUS-Signale:
- Interne Kanalzuordnung wie oben
- Schließen Sie einen 3-Pin-Draht von Ihrem Receiver IBUS-Header an den RX-Header am Sound-Controller an (Sig, V +, GND)
- In diesem Modus können 13 Kanäle gelesen werden

### Lautsprecher
- 4 oder 8 Ohm Lautsprecher sind kompatibel
- Sie können einen oder zwei Lautsprecher verwenden
- Verwenden Sie niemals zwei parallele Lautsprecher auf einem einzigen Anschluss
- Verwenden Sie niemals zwei Anschlüsse parallel, um einen Lautsprecher zu anzuschließen
- Schließen Sie niemals Kondensatoren an die Lautsprecher an

### LED
- Die LED muss "gebräuchlich positiv" verdrahtet sein. Das bedeutet, dass die langen LED-Beine alle miteinander verbunden sind und mit der 5V-Schiene verbunden sind, die vom Bordregler stammen
- Alle LEDs (mit Ausnahme der LEDs, die mit dem TAMIYA Anhängerstecker verbunden sind) benötigen einen Vorwiderstand
- Berechnen Sie den erforderlichen Widerstand nach: http://ledcalc.com (Lieferspannung = 5V)
- Es wird nicht empfohlen, LED parallel zu verdrahten und den Vorwiderstand zu teilen
- Unterstützung für WS2812 Neopixel LED (Details und Verdrahtung siehe "6_adjustmentsLights.h")

### LCD-Armaturenbrett
- Siehe "9_adjustmentsDashboard.h"

### Rüttler (Shaker)
- Der Rüttler Shaker wird für die Motorschwingungssimulation eingesetzt. Die Geschwindigkeit kann in der Fahrzeugkonfiguration eingestellt werden und variiert je nach Motorzustand und Drehzahl
- Er muss mit dem "Shaker" -Pin verbunden werden und die Spannung wird vom 5V-Regler an Bord geliefert. Die negative Seite wird durch den Bordmosfet geschaltet
- Bitte beachten Sie, dass der verwendete Mostfet ein Logikpegeltyp sein muss. Ansonsten funktioniert der Shaker nicht!
- Der Motor sollte nicht mehr als etwa 300mA @ 5V ziehen. Ich benutze einen Shaker-Motor von GT Power.

### RZ7886 7A DC-Motortreiber anstelle eines ESC:
Er ist für kleinere Fahrzeuge wie WPL gedacht

#### Prototype:
![](documentation/pictures/RZ7886.png)
![](documentation/pictures/RZ7886.JPG)
![](documentation/pictures/RZ7886_1.JPG)

#### Bestellen Sie Ihre Motortreiberplatine hier:
https://www.pcbway.com/project/shareproject/RZ7886_based_ESC_for_ESP32_Sound_and_Light_Controller_f8f4a805.html

## Software:
### Erforderliche Software für das Hoch- und Bearbeiten von Codes:
- Arduino IDE (nicht empfohlen): https://www.arduino.cc/en/Main/Software
- oder Visual Studio Code mit PlatformIO-Erweiterung (empfohlen): https://code.visualstudio.com
- Visual Studio benötigt diese Software (Neustart von VS-Code zwingend nötig), um Bibliotheken synchronisieren zu können: https://git-scm.com/download

### Herunterladen und Vorbereiten des Codes mit Arduino IDE:
- Laden Sie den Code von hier herunter (Hit "Code > Download zip"): https://github.com/TheDIYGuy999/Rc_Engine_Sound_ESP32
- Entpacken Sie den Ordner, falls erforderlich
- Entfernen Sie den "-master"-Teil des Ordnernamens
- Installieren Sie Bibliotheken und Boarddefinitionen unten zuerst, und dann starten Sie Arduino IDE neu
- Öffnen Sie "scr.ino" mit einem Doppelklick (die Arduino IDE sollte von selber starten)

### Erforderliche ESP32-Boarddefinition (nicht erforderlich, wenn Visual Studio Code als IDE verwendet wird):
- Installieren Sie es gemäß: https://randomnerdtutorials.com/installing-the-esp32-board-in-arduino-ide-windows-instructions/
- Verwenden Sie nur die v1.04, v1.05 oder neuer verursachen Neustartprobleme!
- Einstellungen anpassen nach:
![](documentation/pictures/settings.png)

### Erforderliche Bibliotheken. Sie müssen ALLE installieren, wenn Sie Arduino IDE verwenden. Nicht erforderlich, wenn Visual Studio Code als IDE verwendet wird:
- statusLED: https://github.com/TheDIYGuy999/statusLED
- SBUS: https://github.com/TheDIYGuy999/SBUS
- rcTrigger: https://github.com/TheDIYGuy999/rcTrigger
- IBUS: https://github.com/bmellink/IBusBM
- TFT: https://github.com/Bodmer/TFT_eSPI
- FastLED: https://github.com/FastLED/FastLED    

Laden Sie sie auf die gleiche Weise wie den obigen Hauptcode herunter. Speichern Sie die Ordner in Ihrem Pfad "Arduino/Bibliotheken". Installieren Sie sie gemäß: https://www.arduino.cc/en/Guide/Libraries

### Hochladen des Codes auf das Board:
- WICHTIG: Je nach Board müssen Sie möglicherweise die Taste "BOOT" drücken und halten, wenn die IDE nur "Verbinden..... _____......" Lassen Sie es los, sobald der Upload startet.
- Auf macOS Big Sur müssen Sie die folgende Korrektur anwenden (nur bei der Arduino IDE):  [Big Sur Fix](BigSurFix.md)

### Visual Studio Code (anstelle von Arduino IDE) überblick:
![](documentation/pictures/VScode.png)

## Anpassen der Dinge in "X_Xyz.h":
### Fahrzeugauswahl:

Beachten Sie, dass ab v5.5 die frühere Konfigurationsdatei "Adjustments.h" in mehrere Dateien unterteilt wurde.

Unkommentar (Entfernen //) des gewünschten Fahrzeugs in "Adjustments.h". 
Uncommentieren Sie nie mehr als ein Fahrzeug! 
Beachten Sie, dass Sie den Code nach dem Ändern der Einstellungen erneut hochladen müssen. 
Andernfalls wird es nicht wirksam. Wählen Sie >Skizze > Hochladen, um den Code hochzuladen. 
Wichtig! Wichtig! Heben Sie Ihr Fahrzeug beim Hochladen immer vom Boden ab.

Wenn Sie ein neues Fahrzeug anfertigen möchten, kopieren Sie Fahrzeuge/00_Master.h, speichern Sie es mit Ihrem Fahrzeugnamen. 
Bearbeiten Sie dann die Einstellungen, wie Sie möchten, fügen Sie Links zu den gewünschten Sounddateien hinzu. 
Fügen Sie anschließend einen Link zu Ihrem vehicle.h hinzu (siehe Beispiele unten) und entfernen Sie ihn

```
#include <Arduino.h>

// VEHICLE SETTINGS ****************************************************************************************************
// Select the vehicle preset you want (uncomment the one you want, remove //, never more than one)

// Master --------
//#include "vehicles/00_Master.h" // This master preset file contains all available sound files, which are not used in existing vehicle presets

// US trucks --------
//#include "vehicles/CaboverCAT3408.h" // Cabover truck with Caterpillar 3408 V8 Diesel
//#include "vehicles/PeterbiltDetroit8v92.h" // Peterbilt 359 with Detroit 8V92 V8 2 stroke Diesel
//#include "vehicles/KenworthW900ADetroit8V71.h" // Kenworth W900A with Detroit 8V71 V8 2 stroke Diesel
//#include "vehicles/KenworthW900ACAT3408.h" // Kenworth W900A with Caterpillar 3408 V8 Diesel (King Hauler)
//#include "vehicles/CAT3408OpenPipes.h" // Kenworth W900A with Caterpillar 3408 V8 Diesel and open pipes
//#include "vehicles/KenworthW900ACAT3408new.h" // Kenworth W900A with Caterpillar 3408 V8 Diesel (good bass speaker required)
//#include "vehicles/KenworthCummins335.h" // 1950ies Kenworth with Cummins 335 R6 Diesel
//#include "vehicles/MackSuperLiner.h" // MACK Super Liner
//#include "vehicles/M35.h"// AM General M35 "deuce and a half" military truck, turbocharged R6 universal fuel engine
//#include "vehicles/US_Firetruck.h"// US firetruck with CAT3408 V8 and Allison 6 speed automatic (horn & siren loop capable)
//#include "vehicles/FreightlinerCummins350.h" // Freightliner Cabover with Cummins 350 R6 Diesel

// EU trucks --------
//#include "vehicles/Tatra813.h" // Tatra 813 8x8 V12 Diesel military truck (old version for comparison, don't use it)
//#include "vehicles/Tatra813new.h" // Tatra 813 8x8 V12 Diesel military truck
//#include "vehicles/UnimogU1000.h" // Umimog U 1000 with turbocharged R6 Diesel incl. Feuerwehr "Martinshorn" siren
//#include "vehicles/MercedesActros1836.h" // Mercedes Actros 1863 or 3363 truck with R6 Diesel
//#include "vehicles/MercedesActrosV6.h" // Mercedes Actros V6 Race Truck incl. tire squealing
//#include "vehicles/ScaniaV8_50ton.h" // SCANIA V8 50 ton truck. Unknown model. Bad quality!
//#include "vehicles/ScaniaV8.h" // SCANIA V8 truck, unknown model
//#include "vehicles/1000HpScaniaV8.h" // 1000 HP SCANIA V8 truck with open pipes. Insane sound! Good bass speakers reqired
//#include "vehicles/Scania143.h" // SCANIA 143 V8 - the legend! The best sounding in my opinion
//#include "vehicles/ScaniaV8Firetruck.h" // SCANIA V8 firetruck, automatic Allison 6 speed transmission with torque converter, "Martinshorn" siren
//#include "vehicles/VolvoFH16_750.h" // Volvo FH16 750 truck. Inline 6, 750 horses, open pipes!
//#include "vehicles/VolvoFH16_OpenPipe.h" // Volvo FH truck. Inline 6, open pipes, alternative version
//#include "vehicles/ManTgx.h" // MAN TGX 680 V8 truck
//#include "vehicles/ManKat.h" // MAN KAT V8 Diesel German Bundeswehr military truck
//#include "vehicles/MagirusDeutz256.h" // Magirus Deutz 256 air coolded V8 Diesel truck
//#include "vehicles/MagirusMercur125.h" // Magirus Mercur air coolded V6 Diesel truck
//#include "vehicles/Saurer2DM.h" // Swiss Saurer 2DM R6 Diesel truck

// Russian trucks --------
//#include "vehicles/Ural4320.h" // URAL 4320 6x6 V8 Diesel military truck
#include "vehicles/Ural375D.h" // URAL 375D 6x6 V8 petrol military truck
//#include "vehicles/URAL375.h" // URAL 375D 6x6 V8 petrol military truck (new version with better V8 sound, but good bass speaker required)
//#include "vehicles/GAZ66.h" // GAZ-66 V8 petrol military truck

// Russian tanks -------
//#include "vehicles/IS3.h" // IS-3 WW2 battle tank, V12 Diesel (dual ESC mode, good bass speaker required)

// Tractors -------
//#include "vehicles/KirovetsK700.h" // Russian Kirovets K700 monster tractor. Extreme turbo sound!

// Excavators -------
//#include "vehicles/Caterpillar323Excavator.h" // Caterpillar 323 excavator (use "FLYSKY_FS_I6S_EXCAVATOR" remote profile)

// Dumpers -------
//#include "vehicles/Benford3TonDumper.h" // Benford 3 ton dumper

// US motorcycles --------
//#include "vehicles/HarleyDavidsonFXSB.h" // Harley Davidson FXSB V2 motorcycle

// US cars --------
//#include "vehicles/ChevyNovaCoupeV8.h" // 1975 Chevy Nova Coupe V8
//#include "vehicles/1965FordMustangV8.h"// 1965 Ford Mustang V8
//#include "vehicles/Chevy468.h" // Chevy 468 big block V8

// EU cars --------
//#include "vehicles/VwBeetle.h" // VW Käfer / Beetle
//#include "vehicles/JaguarXJS.h" // Jaguar XJS V12, manual transmission
//#include "vehicles/JaguarXJSautomatic.h" // Jaguar XJS V12, automatic transmission
//#include "vehicles/MGBGtV8.h" // MGB GT V8, manual transmission
//#include "vehicles/LaFerrari.h" // Ferrari LaFerrari, V12, 6 speed double clutch transmission

// US SUV & Pickups --------
//#include "vehicles/JeepGrandCherokeeTrackhawk.h" // Jeep Grand Cherokee Trackhawk V8 monster SUV with supercharger, 6 speed automatic
//#include "vehicles/FordPowerstroke.h" // Ford Powerstroke 7.3l V8 Diesel, 6 speed automatic (good bass speaker required)
//#include "vehicles/RAM2500_Cummins12V.h" // Dodge RAM 2500 with inline 6, 12V Cummins 5.9l Diesel, manual transmission
//#include "vehicles/RAM2500_Cummins12Vautomatic.h" // Dodge RAM 2500 with inline 6, 12V Cummins 5.9l Diesel, automatic transmission
//#include "vehicles/GMCsierra.h" // GMC Sierra V8 pickup, 3 speed automatic transmission
//#include "vehicles/ChevyNovaCoupeV8_P407.h" // 1975 Chevy Nova Coupe V8, special version for HG-P407, 3 speed automatic transmission
//#include "vehicles/JeepWranglerRubicon392V8.h" // 2021 Jeep Wrangler Rubicon HEMI 392 V8 (starter needs rework)
//#include "vehicles/JeepWranglerRubicon392V8_2.h" // 2021 Jeep Wrangler Rubicon HEMI 392 V8 (insane bass!)

// EU SUV --------
//#include "vehicles/DefenderV8Automatic.h" // Land Rover Defender 90 V8 automatic (very nice V8 with lots of bass)
//#include "vehicles/DefenderV8OpenPipeAutomatic.h" // Land Rover Defender 90 V8 automatic, open pipes (optimised for smaller speakers)
//#include "vehicles/DefenderV8CrawlerAutomatic.h" // Land Rover Defender 90 V8 automatic crawler
//#include "vehicles/DefenderTd5.h" // Land Rover Defender 90 Td5 R5 Diesel

// Asian SUV --------
//#include "vehicles/LandcruiserFJ40.h" // Landcruiser Fj40 with inline 6 petrol engine
//#include "vehicles/LandcruiserFJ40Diesel.h" // Landcruiser Fj40 with inline 6 12H Turbo Diesel engine
//#include "vehicles/LandcruiserFJ40Diesel2.h" // Landcruiser Fj40 with inline 6 12H Turbo Diesel engine
//#include "vehicles/HiluxDiesel.h" // Hilux Diesel with inline 6 12H Turbo Diesel engine (for HG-P407)

// US locomotives --------
//#include "vehicles/UnionPacific2002.h" // Union Pacific 2002 SD70M locomotive with enormous, low revving 16 cylinder Diesel

// Planes --------
//#include "vehicles/MesserschmittBf109.h" // Messerschmitt BF 109 WW2 German V12 plane

// Generic Diesels --------
//#include "vehicles/generic6zylDiesel.h" // Generic inline 6 Diesel, no turbo, manual transmission (optimised for smaller speakers)
```

### Schnittstellentyp (Kommunikationsmodus) Auswahl:

Beachten Sie, dass der Standardkommunikationsmodus SBUS ist. Sie müssen es wie folgt ändern, wenn Sie klassische RC-Servosignale verwenden möchten.

#### PWM (klassische RC-Signale auf "CH1" - "CH4", "35" & "PPM" Header, die gängigste Schnittstelle)
```
// COMMUNICATION SETTINGS **********************************************************************************************
// Choose the receiver communication mode (never uncomment more than one!) !!! ADJUST THEM BEFORE CONNECTING YOUR RECEIVER AND ESC !!!

// PWM servo signal communication (CH1 - CH4, 35, PPM headers, 6 channelschannelSetup.h) --------
// PWM mode active, if SBUS, IBUS and PPM are disabled (// in front of #define)

// SBUS communication (SBUS header, 13 channels. This my preferred communication protocol)--------
//#define SBUS_COMMUNICATION // control signals are coming in via the SBUS interface (comment it out for classic PWM RC signals)
boolean sbusInverted = true; // false = wired to non standard (inverted) SBUS signal (for example from "Micro RC" receiver)

// IBUS communication (RX header, 13 channels not recommended, NO FAILSAFE, if bad contact in iBUS wiring!) --------
//#define IBUS_COMMUNICATION // control signals are coming in via the IBUS interface (comment it out for classic PWM RC signals)

// SUMD communication (RX header, 12 channels, For Graupner remotes) --------
//#define SUMD_COMMUNICATION // control signals are coming in via the SUMD interface (comment it out for classic PWM RC signals)

// PPM communication (RX header, 8 channels, working fine, but channel signals are a bit jittery) --------
//#define PPM_COMMUNICATION // control signals are coming in via the PPM interface (comment it out for classic PWM RC signals)
```

#### PPM (Multiple-Kanäle Pulspause-Modulation, drahtgebunden auf "RX" Header, 8 Kanäle)
```
// COMMUNICATION SETTINGS **********************************************************************************************
// Choose the receiver communication mode (never uncomment more than one!) !!! ADJUST THEM BEFORE CONNECTING YOUR RECEIVER AND ESC !!!

// PWM servo signal communication (CH1 - CH4, 35, PPM headers, 6 channelschannelSetup.h) --------
// PWM mode active, if SBUS, IBUS, and PPM are disabled (// in front of #define)

// SBUS communication (SBUS header, 13 channels. This my preferred communication protocol)--------
//#define SBUS_COMMUNICATION // control signals are coming in via the SBUS interface (comment it out for classic PWM RC signals)
boolean sbusInverted = true; // false = wired to non standard (inverted) SBUS signal (for example from "Micro RC" receiver)

// IBUS communication (RX header, 13 channels not recommended, NO FAILSAFE, if bad contact in iBUS wiring!) --------
//#define IBUS_COMMUNICATION // control signals are coming in via the IBUS interface (comment it out for classic PWM RC signals)

// SUMD communication (RX header, 12 channels, For Graupner remotes) --------
//#define SUMD_COMMUNICATION // control signals are coming in via the SUMD interface (comment it out for classic PWM RC signals)

// PPM communication (RX header, 8 channels, working fine, but channel signals are a bit jittery) --------
#define PPM_COMMUNICATION // control signals are coming in via the PPM interface (comment it out for classic PWM RC signals)
```

#### SBUS (empfohlen, Standardeinstellung, verdrahtet auf "SBUS" Header, 13 Kanäle)
```
// COMMUNICATION SETTINGS  ********************************************************************************************************************
// Choose the receiver communication mode (never uncomment more than one!) !!! ADJUST THEM BEFORE CONNECTING YOUR RECEIVER AND ESC !!!

// PWM servo signal communication (CH1 - CH4, 35, PPM headers, 6 channels) --------
// PWM mode active, if SBUS, IBUS, and PPM are disabled (// in front of #define)

// SBUS communication (RX header, 13 channels. This is my preferred communication protocol)--------
#define SBUS_COMMUNICATION // control signals are coming in via the SBUS interface (comment it out for classic PWM RC signals)
boolean sbusInverted = false; // false = wired to non standard (inverted) SBUS signal (for example from my "Micro RC" receiver)
uint32_t sbusBaud = 100000; // Standard is 100000. Try to lower it, if your channels are coming in unstable. Working range is about 96000 - 104000.

// IBUS communication (RX header, 13 channels not recommended, NO FAILSAFE, if bad contact in iBUS wiring!) --------
//#define IBUS_COMMUNICATION // control signals are coming in via the IBUS interface (comment it out for classic PWM RC signals)

// SUMD communication (RX header, 12 channels, For Graupner remotes) --------
//#define SUMD_COMMUNICATION // control signals are coming in via the SUMD interface (comment it out for classic PWM RC signals)

// PPM communication (RX header, 8 channels, working fine, but channel signals are a bit jittery) --------
//#define PPM_COMMUNICATION // control signals are coming in via the PPM interface (comment it out for classic PWM RC signals)
```

SBUS nicht Standardsignal (wenn Ihr Empfänger ein nicht standardmäßiges SBUS-Signal sendet):
```
boolean sbusInverted = false; // false = wired to non standard (inverted) SBUS signal (for example from "Micro RC" receiver)
```

SBUS-Standardsignal (Standard, in den meisten Fällen verwendet)
```
boolean sbusInverted = true; // false = wired to non standard (inverted) SBUS signal (for example from "Micro RC" receiver)
```

SBUS baudrate Feineinstellung. 100000 ist Standard. Bei einigen Empfängern können die Indikatoren und andere Funktionen zufällig ausgelöst werden, da es Bitfehler gibt. 
Diese Variable ermöglicht es, das Baudrate fein einzustellen, um dieses Problem zu lösen.
```
uint32_t sbusBaud = 100000; // Standard is 100000. Try to lower it, if your channels are coming in unstable. Working range is about 96000 - 104000.
```

#### IBUS (nicht empfohlen, KEIN FAILSAFE, wenn schlechter Kontakt in der iBUS-Verkabelung! "RX"-Header, 13 Kanäle)
```
// COMMUNICATION SETTINGS **********************************************************************************************
// Choose the receiver communication mode (never uncomment more than one!) !!! ADJUST THEM BEFORE CONNECTING YOUR RECEIVER AND ESC !!!

// PWM servo signal communication (CH1 - CH4, 35, PPM headers, 6 channelschannelSetup.h) --------
// PWM mode active, if SBUS, IBUS, SERIAL and PPM are disabled (// in front of #define)

// SBUS communication (SBUS header, 13 channels. This my preferred communication protocol)--------
//#define SBUS_COMMUNICATION // control signals are coming in via the SBUS interface (comment it out for classic PWM RC signals)
boolean sbusInverted = true; // false = wired to non standard (inverted) SBUS signal (for example from "Micro RC" receiver)

// IBUS communication (RX header, 13 channels not recommended, NO FAILSAFE, if bad contact in iBUS wiring!) --------
#define IBUS_COMMUNICATION // control signals are coming in via the IBUS interface (comment it out for classic PWM RC signals)

// SUMD communication (RX header, 12 channels, For Graupner remotes) --------
//#define SUMD_COMMUNICATION // control signals are coming in via the SUMD interface (comment it out for classic PWM RC signals)

// PPM communication (RX header, 8 channels, working fine, but channel signals are a bit jittery) --------
//#define PPM_COMMUNICATION // control signals are coming in via the PPM interface (comment it out for classic PWM RC signals)
```

#### SUMD (Für Graupner-Fernbedienungen "RX"-Header, 12 Kanäle)
```
// COMMUNICATION SETTINGS  ********************************************************************************************************************
// Choose the receiver communication mode (never uncomment more than one!) !!! ADJUST THEM BEFORE CONNECTING YOUR RECEIVER AND ESC !!!

// PWM servo signal communication (CH1 - CH4, 35, PPM headers, 6 channels) --------
// PWM mode active, if SBUS, IBUS, and PPM are disabled (// in front of #define)

// SBUS communication (SBUS header, 13 channels. This is my preferred communication protocol)--------
//#define SBUS_COMMUNICATION // control signals are coming in via the SBUS interface (comment it out for classic PWM RC signals)
boolean sbusInverted = false; // false = wired to non standard (inverted) SBUS signal (for example from my "Micro RC" receiver)

// IBUS communication (RX header, 13 channels not recommended, NO FAILSAFE, if bad contact in iBUS wiring!) --------
//#define IBUS_COMMUNICATION // control signals are coming in via the IBUS interface (comment it out for classic PWM RC signals)

// SUMD communication (RX header, 12 channels, For Graupner remotes) --------
#define SUMD_COMMUNICATION // control signals are coming in via the SUMD interface (comment it out for classic PWM RC signals)

// PPM communication (RX header, 8 channels, working fine, but channel signals are a bit jittery) --------
//#define PPM_COMMUNICATION // control signals are coming in via the PPM interface (comment it out for classic PWM RC signals)
```

## Anpassen der Dinge in "Vehicles/yourVehiclePreset.h":
### Rüttler (Shaker)
Stellen Sie die Schüttelleistung für die verschiedenen Motorzustände an Ihre Bedürfnisse an:
```
// Shaker parameters (simulating engine vibrations) ---------------------------------------------------------------------
const uint8_t shakerStart = 100; // Shaker power while engine start (max. 255, about 100)
const uint8_t shakerIdle = 49; // Shaker power while idling (max. 255, about 49)
const uint8_t shakerFullThrottle = 40; // Shaker power while full throttle (max. 255, about 40)
const uint8_t shakerStop = 60; // Shaker power while engine stop (max. 255, about 60)
```
### Mehr zu kommt in der Zukunft...

## Prototypes:
![](documentation/pictures/top.jpg)

![](documentation/pictures/receiver_wiring.jpg)

![](documentation/pictures/Bestueckt_oben.jpg)

![](documentation/pictures/oben.jpg)

![](documentation/pictures/unten.jpg)


2019 - 2023, TheDIYGuy999
