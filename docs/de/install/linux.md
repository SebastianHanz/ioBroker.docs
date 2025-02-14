---
title:       "Linux"
lastChanged: "05.12.2020"
---

# ioBroker Installation unter Linux


!> Diese Anleitung gilt NICHT für fertige Images der Webseite!
Die manuelle Installation ist jedoch einem Image gegenüber zu bevorzugen. 

Die Installation erfolgt über ein Skript, welches die benötigten Installationsschritte durchführt und evtl. noch erforderliche Softwarepakete nachlädt.
Während der Installation wird im System ein neuer Benutzer “iobroker” angelegt sowie ein zugehöriges Home-Verzeichnis (/home/iobroker). 
Der ioBroker läuft dann unter diesem User. 

Wem das Nachladen eines Skripts zu gefährlich ist der kann das Skript vorher unter 
[diesem Link](https://raw.githubusercontent.com/ioBroker/ioBroker/stable-installer/installer.sh) prüfen.

Diese Installationsanleitung für ioBroker zeigt die Installation auf Linux am Beispiel vom Raspberry Pi 
mit Raspberry OS 'Buster'. 

Es kann auf Grund von Abhängigkeiten zu anderen Paketen oder zusätzlichen Installationen 
bei der Installation immer wieder zu Besonderheiten kommen.

## Benötigte Hardware
### Raspberry Pi 2/3/4

oder jede andere beliebige Hardware mit einem gängigen Linux. Empfohlen wird jedoch Debian, Ubuntu oder eine der darauf basierenden Distributionen. 

Wir raten davon ab, einen Pi 1 als Master einzusetzen. Dieser ist einfach nicht leistungsstark 
genug (500 MB RAM, usw.). Aufgrund der unterschiedlichen Hardware passt diese Anleitung 
ohnehin nicht für einen Pi 1.

Auch ein Pi 2 oder Pi 3 hat nur max. 1 GB RAM. Bei 15 Adapter-Instanzen sollte dieser noch 
ausreichen, aber darüberhinaus kann es knapp werden. Jede Adapter-Instanz benötigt etwa 40 MB 
(und auch schon mal 200MB und mehr) an RAM. Daher sollte man immer die RAM-Auslastung 
im Auge behalten werden, bevor weitere Adapter-Instanzen aktiviert werden – 1 GB RAM sind endlich.

Daher empfiehlt sich aus der Raspberry-Reihe der Raspberry4 mit 4, besser 8 GB RAM. 

### Netzteil
es ist wichtig ein gutes Netzteil zu haben. Mit schwachem Netzteil sind Stabilitätsprobleme zu erwarten

### Speicherkarte
oder SSD, USB-Stick, usw. (je nach verwendeter Hardware)

## benötigte / wichtige Links
* Download Image: https://www.raspberrypi.org/software/operating-systems/
* Win32DiskImager: https://sourceforge.net/projects/win32diskimager/  **oder**
* Balena Etcher: https://www.balena.io/etcher/
* Putty: http://www.putty.org/

## Installationsanleitung
### Installation Betriebssystem

* Das gewünschte Basis-Betriebssystem (Raspberry OS Bullseye, Ubuntu, Debian, usw.) – je nach verwendeter Hardware installieren.

    Hilfe und Anleitungen zu den jeweiligen Versionen gibt es auf den entsprechenden Supportseiten, 
Youtube, usw.

* NUR wenn root-Zugang per SSH oder sftp unbedingt benötigt wird, **KANN** auch der 
Root Zugang für SSH freigeschaltet werden.

    Wir raten, aus den bekannten Sicherheitsaspekten, davon ab. Für die Installation von ioBroker 
reicht es aus, den Befehl sudo zu verwenden und dem jeweiligen Befehl voran zu stellen.

### Installation Node.js
!> mit dem aktuellen Installer von ioBroker (siehe unten) wird **auf einem System ohne node.js** automatisch die aktuell empfohlene Version von node.js mit installiert! Eine vorherige separate Installation von node.js ist somit **nicht** mehr nötig.

Die folgende Anleitung ist auch bei einem Downgrade zu verwenden.

Die momentan empfohlene Version ist node 14.x; bei anderen gewünschten Versionen in Schritt 4.1. die “14.x” gegen Y.x” austauschen.

!> Node.js < 12.x wird nicht mehr supported


<span style="color:red"> ungerade nodejs-Versionen sind grundsätzlich nicht empfohlen, da es sich um Entwicklerversionen handelt. </span>

<span style="color:red"> npm wird zusammen mit nodejs passend installiert. Eine manuelle Installation oder Upgrade von npm ist nicht ratsam!  </span>


1. System-Update: ``sudo apt-get update && sudo apt-get upgrade``

    Je nach verwendetem OS kann das Update auch mittels ``sudo apt update && sudo apt upgrade`` 
ausgeführt werden.

2. Auf bereits vorhandene Versionen von nodejs und npm testen.

    ``node -v``

    ``nodejs -v``

    ``npm -v``

    nur wenn **ALLE** diese Befehle kein Ergebnis bringen (also keine Versionsnummer mehr 
anzeigen) mit Schritt 4. dieses Abschnittes weitermachen, sonst, oder wenn die Version nicht der 
gewünschten entspricht folgendes vorher ausführen:

3. Die existierenden node & node.js Versionen deinstallieren

    ``sudo apt-get --purge remove node`` (Es kann sein, dass hier eine Fehlermeldung kommt. Bitte weiter machen!)

    ``sudo apt-get --purge remove nodejs``

    ``sudo apt-get autoremove``

    ``sudo reboot``

4. Node.js neu installieren für Linux und Raspberry 2/3
    
    ``curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -``
    
    ``sudo apt install -y nodejs``

    ``sudo reboot``

    Nach der Installation müssen die Kommandos “node -v” und “nodejs -v” die gleiche 
Versionsnummer zurückgeben.
    
    Falls ``node -v`` eine Fehlermeldung wie “nicht gefunden” erzeugt, dann bitte ein 

    ``sudo ln -s /usr/local/bin/nodejs /usr/bin/node`` an der Konsole ausführen.
    
    
    In neueren Installationen kann es sein, dass der Befehl ``nodejs -v`` eine Fehlermeldung wie “nicht gefunden” erzeugt. 
    Dies ist prinzipiell unbedenklich, da der Befehl ``nodejs`` schon länger nicht mehr verwendet wird, kann aber über einen Symlink mit dem 
    Befehl ``sudo ln -s /usr/bin/node /usr/bin/nodejs`` "repariert" werden.
    
---    

Sind die Versionen unterschiedlich, bitte nochmals den Abschnitt 
[Installation Node.js](#installation-nodejs) abarbeiten

Als letzte Überprüfung bitte noch die Version von npm mittels ``npm -v`` überprüfen.

Ergibt dies eine Version < 6, bitte noch mit ``sudo -H npm install -g npm@6`` ein 
npm-Update durchführen

---

### Installation ioBroker
Die Installation kann mit dem User pi aber auch mit dem User root erfolgen. 

An der Konsole ausführen:

``curl -sLf https://iobroker.net/install.sh | bash -``

---

Die Installation erfolgt in 4 Schritten:

``Installing prerequisites (1/4)``

``Creating ioBroker user and directory (2/4)``

``Installing ioBroker (3/4)``

``Finalizing installation (4/4)``

Zum Abschluss kommt dann noch die Meldung

``ioBroker was installed successfully``

``Open http://localhost:8081 in a browser and start configuring!``

---

ioBroker nun über die angegebene IP im Webbrowser aufrufen: ``http://<IP-Adresse>:8081``
 

**Hinweis:**

Nach Installationsänderungen kann es zu Rechteproblemen kommen.

 

In diesem Fall bitte den Installations-Fixer anwenden:

``curl -sL https://iobroker.net/fix.sh | bash -``

oder kurz `iobroker fix`


 

nähere Informationen im Forum:

https://forum.iobroker.net/topic/20211/iobroker-installation-fixer-beta-verf%C3%BCgbar
