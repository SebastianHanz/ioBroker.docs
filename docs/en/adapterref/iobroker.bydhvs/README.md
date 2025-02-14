![Logo](admin/bydhvs.png)

## bydhvs adapter for ioBroker

BYD HVS Battery poll data

## English:

## Introduction

This Adapter takes data from a byd PV battery ( https://www.bydbatterybox.com/ ) and puts them into datapoints in the adapter. Unfortunally there is no official API and no documentation, so I used wireshark and a byd-hvs-simulater to try to understand the communication. My adapter simulates the byd-app, sends similar packets to the device and analyses the responses. 

## be careful

There are two steps in the beConnect app, in the first step you get the normal data, in the second step you get detail-data for all cells (individual cell temperature and voltage and some more details) To get the detail-data there has to be a delay after one of the data-packets till I can get the result. I think in the meantime alle cells are measured, but I am not sure. I am definetely not shure if you harm your battery with polling this data too often, so be aware: You are on your own risk!

## hint for systems with 5 modules

People who have 5 modules: The cell details are read only for the first 4 modules - the protocol is the same for 2-4 modules. I would like to extend it for 5 modules but either somebody buys me the three missing modules ;-) so I can analyse the protocol or I get a wireshark capture from a working connection.

## settings

Interval: That's easy: how often (s) shall the data be polled
IP-Adress: Thats self explaining. Either you use the standard address ( 192.168.16.254 ) and change the routing at home, e.g.: https://www.photovoltaikforum.com/thread/150898-byd-hvs-firmware-update/?postID=2215343#post2215343 . The advantage is: The beConnect app works, too. Other possibility: You change the IP-Adress of the box. But: Be warned: the text on the webpage is confusing and if you are not absolutely shure about the things you do: PLEASE do not touch the settings. In the German forums I read from people who were locked out of their system and there is no way back, either byd sends you a replacement HVU or you have to buy a new one. 
Battery-details: As explained above: Do you need the details of the battery? If so: set the checkobx.
Battery-details - every ... cycles :Also like above, should be clear
Test Mode - show data in error log: If you check this box: the sent and recieved data are displayed in the error-log, so you can easily download the data and send it to me in case of errors.


## German:


## Ein wenig Erklärungen:

Prinzipiell ist der Adapter durch Anaylse der Datenpakete zwischen der BYD-App und dem BYD-Akku-System entstanden. Es werden im Wesentlichen die Daten aus dem TAB System Info und aus dem TAB Diagnosis dargestellt. Offensichtlich sind die Daten für "System Info" sofort in der Batterie bereit zum abholen, für die Diagnose-Daten sieht es so aus als wäre ein Messvorgang erforderlich, zwischen der Abfrage und den Werten muss ein Zeitintervall von gut 3 Sekunden eingehalten werden. 

Ich bin mir nicht sicher ob das BYD-System durch zu häufige Abfragen beschädigt wird, also: Es ist Dein Risiko was Du hier einträgst!

## Zu den Einstellungen:
Intervall: Zeitlicher Abstand zwischen den Abfragen des Adapters

IP-Adresse: Eigentlich logisch, damit ist die IP-Adresse des Adapters gemeint. Dafür gibt es zwei Möglichkeiten: Entweder hält man sich an die Anleitung von Becker3 aus dem Photovoltaik-Forum, ist hier verlinkt: https://www.photovoltaikforum.com/thread/150898-byd-hvs-firmware-update/?postID=2215343#post2215343 . Das hat den Vorteil das auch die BYD-APP läuft und man mit dieser direkt an die Daten, auch zum Vergleich, herankommt. Oder man trägt "nur" die IP-Adresse die die BYD-Box per DHCP erhalten hat ein. Ausdrücklich waren möchte ich vor Änderungen an den IP-Einstellungen der BOX! Im Forum kann man Berichte von Leute lesen die sich die Erreichbarkeit der Box dauerhaft ruiniert haben. 

Batterie-Details: Steuerung, ob die Details zu den Zellen gelesen werden sollen

Lesezyklen zu Batterie-Details: Anzahl der "Normal-Lese-Zyklen" bis wieder einmal die Diagnose-Daten gelesen werden. Hier die Warnung dazu: Ich habe keine Idee ob man sich durch häufige Diagnose-Messungen Nachteile einhandelt, daher empfehle ich den Wert möglichst hoch zu setzen. Ich wüsste auch nicht was man mit den Diagnose-Daten im regelmäßigen Poll anfangen sollte. 

Zu den Batterie-Größen: Der Adapter funktioniert auch für Zelltemperaturen und ZellSpannungen bei 2,3 und 4 Batterie-Modulen. Bei einem System mit 5 Modulen werden nur die Zellspannungen der ersten 128 Zellen angezeigt. Für die Zellen 129 bis 160 ist mir nicht bekannt wo die Daten gespeichert werden. Ich würde das gerne mit in den Adapter einbauen, benötige aber dafür einen Wireshark-Mittschnitt der Kommunikation zwischen der beConnect App und dem Speicher. Ich helfe auch gerne wenn jemand nicht weiß wie man den Mittschnitt machen kann, entweder per Teamviewer oder per Postings im Forum. Offensichtlich funktioniert die Kommunikation für die 5. Einheit anders als bei den ersten 4 Einheiten. 


## Changelog
<!--
	Placeholder for the next version (at the beginning of the line):
	### __WORK IN PROGRESS__
-->

### 1.3.1 - testing
* Better detection of battery type and inverter
* SOC not only from normal data but from diagnosis-data, too. There we have one decimal place more
* removed frequency limit for battery detail data
* increased max count of temperature measurements for HVS to 64

### 1.3.0 (2021-11-06)
* updated even more dependencies
* official release with new state SOH

### 1.2.4-0 (2021-11-02)
* Added state: SOH
* updated dependencies as suggested from bot

### 1.2.3 (2021-06-18)
* changed ratio of logo

### 1.2.2 (2021-06-14)
* bump to new patch-level (to get rid of the "-0")

### 1.2.2-0 (2021-05-30)
* Create States for Diagnose-Data only if necessary
* changes according review of the adapter

###

## License
MIT License

Copyright (c) 2021 Christian <github@familie-herrmann.de>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.