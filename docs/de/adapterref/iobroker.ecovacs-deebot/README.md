---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.ecovacs-deebot/README.md
title: Ecovacs Deebot-Adapter für ioBroker
hash: zGQyWlxu2yuyzMud9BLBEfkleWc9C1h3vtEutAf4tNA=
---
![Logo](../../../en/adapterref/iobroker.ecovacs-deebot/admin/ecovacs-deebot.png)

![stabile Version](http://iobroker.live/badges/ecovacs-deebot-stable.svg)
![Letzte Version](http://img.shields.io/npm/v/iobroker.ecovacs-deebot.svg)
![Anzahl der Installationen](http://iobroker.live/badges/ecovacs-deebot-installed.svg)
![Anzahl der monatlichen Downloads](https://img.shields.io/npm/dm/iobroker.ecovacs-deebot.svg)
![Anzahl der Downloads](https://img.shields.io/npm/dt/iobroker.ecovacs-deebot.svg)

# Ecovacs Deebot-Adapter für ioBroker
[![github-workflow](https://github.com/mrbungle64/iobroker.ecovacs-deebot/actions/workflows/node.js.yml/badge.svg)](https://github.com/mrbungle64/iobroker.ecovacs-deebot)

Dieser Adapter verwendet die Bibliothek [ecovacs-deebot.js](https://github.com/mrbungle64/ecovacs-deebot.js).

## Merkmale
Einige bemerkenswerte Merkmale sind:

* Grundlegende Reinigungsfunktionen (z. B. automatische Reinigung, Fleckenbereich, benutzerdefinierter Bereich usw.)
* und verschiedene andere Befehle (z. B. Ton abspielen, Verbrauchsmaterialien zurücksetzen, Position verschieben usw.)
* Grundlegende Informationen abrufen (z. B. Akkustand, Reinigungsprotokoll, Verbrauchsmaterial, Reinigungs- und Ladestatus etc.)
* und diverse erweiterte Informationen (z. B. Ladeposition, aktuelle Karte, Netzinformationen)
* Informationen während des Reinigungsvorgangs abrufen (z. B. aktuelle Position und aktueller Spotbereich)
* Grund- und erweiterte Einstellung einstellen (z. B. Dauerreinigung, Nicht-Stören-Modus, TrueDetect 3D, Lautstärke etc.)
* Anpassung von Vakuumleistung und Wasserstand
* Speichern Sie den zuletzt verwendeten benutzerdefinierten Bereich und führen Sie die gespeicherten Bereiche erneut aus
* Abrufen von Informationen der Karten inkl. Spotbereiche, virtuelle Grenzen und No-Mop-Zonen
* Löschen, speichern und erstellen Sie einzelne virtuelle Grenzen sowie einen vollständigen Satz virtueller Grenzen
* Informationen über Datum und Uhrzeit der letzten Präsenz für jeden einzelnen Spotbereich
* Einige Funktionen bei der Rückkehr zur Ladestation oder beim Betreten/Verlassen des Spotbereichs
* Funktion zum Laden des aktuellen Kartenbildes
* Legen Sie individuelle Spot-Bereichsnamen fest

Bitte beachten Sie: Einige Funktionen sind nur für einige Modelle verfügbar und einige sind noch experimentell

## Modelle
### Unterstützte Modelle
* Debot 900/901
*Deebot OZMO 930
* Deebot-OZMO 920/950
* Deebot T8 AIVI (T8-Serie)

Bei den aufgeführten Modellen handelt es sich um solche, die ich selbst im Einsatz habe oder die technisch mit diesen identisch sind.

### Diese Modelle sollten richtig oder zumindest teilweise funktionieren
* Deebot Slim 2
* Deebot N79-Serie
*Deebot M88
* Debbot 500
* Debot 600/601/605
* Debot 710/711
* Deebot-OZMO 610
* Deebot-OZMO 900/905
*Deebot OZMO Slim 10/11
*Deebot OZMO T5
* Deebot U2-Serie
* Deebot N8-Serie
* Deebot T8-Serie
* Deebot T9-Serie
* Deebot X1-Serie

Die aufgeführten Modelle funktionieren entweder bereits oder sind diesen Modellen technisch ähnlich.
Trotzdem kann die Funktionalität teilweise eingeschränkt sein.

Ich versuche, eine möglichst breite Funktionalität zu erreichen, entscheide dies aber von Fall zu Fall je nach Komplexität und diversen anderen Kriterien.
Es besteht natürlich kein Anspruch auf volle Funktionalität.

## Installation
Es wird empfohlen, Version 12.x oder 14.x von Node.js zu verwenden. Die erforderliche Mindestversion ist 12.x

Dieser Adapter verwendet die Bibliothek [Knotenleinwand](https://www.npmjs.com/package/canvas) für einige kartenbezogene Funktionen, die möglicherweise die Installation einiger zusätzlicher Pakete erfordern.

Die Installation von Canvas ist optional und bei Modellen ohne Kartenfunktionalität nicht notwendig, für vollen Funktionsumfang installieren Sie bitte die folgenden Pakete.

Für Debian-basierte Linux-Systeme sollten die folgenden Befehle ausgeführt werden:

```bash
sudo apt-get update
sudo apt-get install build-essential libcairo2-dev libpango1.0-dev libjpeg-dev libgif-dev librsvg2-dev
```

Möglicherweise ist ein Neustart erforderlich, bevor der nächste Befehl ausgeführt wird

```bash
sudo npm install canvas --unsafe-perm=true
```

Anweisungen für andere Systeme finden Sie unter https://www.npmjs.com/package/canvas#compiling

## Verwendungszweck
* Informationen zur Verwendung dieses Adapters finden Sie [hier](https://github.com/mrbungle64/ioBroker.ecovacs-deebot/wiki)

### Zustände
* Informationen zu den Staaten finden Sie [hier](https://github.com/mrbungle64/ioBroker.ecovacs-deebot/wiki/States-%28EN%29) (Englisch) und [hier](https://github .com/mrbungle64/ioBroker.ecovacs-deebot/wiki/Datenpunkte-%28DE%29) (Deutsch)

## FAQ
* Häufig gestellte Fragen finden Sie [hier](https://github.com/mrbungle64/ioBroker.ecovacs-deebot/wiki/FAQ)

## Bekannte Probleme
* Die Generierung von Kartenbildern ist derzeit auf 32-Bit-Systemen nicht stabil
* Für einige Modelle (z. B. Deebot OZMO 930) wird es empfohlen

an [Neustart planen](https://www.iobroker.net/#en/documentation/admin/instances.md#The%20page%20content) einmal täglich, weil es einige Berichte gibt, dass die Verbindung nach ca. 24 Stunden

* Die "Edge"-Funktion funktioniert nicht mit Deebot U2 (startet stattdessen die automatische Reinigung)
* Einige "cleaninglog"-Zustände sind bei der T9-Serie leer ("last20Logs", "lastCleaningDate" und "lastCleaningMapImageURL")

## Haftungsausschluss
Ich bin in keiner Weise mit ECOVACS verbunden.

## Changelog

### 1.4.1 (alpha)
* Bumped ecovacs-deebot.js to 0.8.0
* Improved last time presence functionality
* Added option to reset the vacuum power (cleanSpeed) to standard on return
* Added option to keep modified spot area names (pre-selection on non 950 type models)
* Added states for current used custom and spot areas (currentUsedSpotAreas and customUsedCustomAreaValues)
* Handle error code 110 ("NoDustBox: Dust Bin Not installed")
* Bumped some dependencies

### 1.4.0
* Bumped ecovacs-deebot.js to 0.8.0 (beta)
* Implemented last time presence function (still experimental)
* Implemented cleanCount (permanent clean count) function (T8/T9/X1 series)
* Implemented trueDetect (enable/disable) function (T8/T9/X1 series)
* Added unit care to consumables (T8/T9/X1 series)
* Added Deebot X1 series
* Some improvements and fixes

### 1.3.4
* Bumped ecovacs-deebot.js to 0.7.2 (beta)
* Implemented some experimental functions for auto empty stations
* Some refactoring

### 1.3.3
* Bumped ecovacs-deebot.js to 0.7.1 (incl. fix for CVE-2022-0155)

### 1.3.2
* Bumped follow-redirects to 1.14.7 (fix for CVE-2022-0155) and some other dependencies
* Added N8 PRO+

### 1.3.1
* Fix the cleaning functions for the Deebot 710 series

### 1.3.0
* Using library version 0.7.0 (beta)
* The minimum required version of Node.js is now 12.x
* Some improvements for newer models (e.g. T9 series)
* Some other improvements and fixes

### 1.2.4
* Using library version 0.6.8
* Some optimizations
* Preparations for changing the minimum required Node.js version to 12.x

### 1.2.3
* Using library version 0.6.6
* Lots of code refactoring, optimizations and some fixes

### 1.2.2
* Added function to load current map image (non 950 type models, e.g. OZMO 930, Deebot 901)

### 1.2.1
* Some enhancements and fixes
* (benep) Added state to play sound by id

### 1.2.0
* Using library version 0.6.1
* Added functions for deleting, saving and recreating saved virtual boundaries (950 type models, e.g. OZMO 920/950, T8 series)
* Added functions for saving and recreating sets of virtual boundaries (950 type models, e.g. OZMO 920/950, T8 series)
* Added options to control clean speed and water level separately for each spot area
* Added function to save current spot area values
* Added function to load current map image (950 type models, e.g. OZMO 920/950, T8 series)
* Added some cleaning log values and some states for current cleaning stats
* Removed "Use alternative API call for lastCleaningMapImageURL and lastCleaningTimestamp" option
* Moved some states from "info" channel to sub channels "info.library" and "info.network"
* Quite a lot of improvements for processing map data, spot areas and virtual boundaries
* Some optimisations for js-controller 3.3
* Improved support for N8 series
* Initial support for T9 series
* Some improvements and fixes

### 1.1.1
* Using library version 0.6.0
  * Updated login process
  * Support for Chinese server login
* Initial support for some models (e.g. N3, N7 and N8 series)

### 1.1.0
* Stable release

### 1.0.13
* Using library version 0.5.6
* Some improvements and fixes

### 1.0.12
* Using library version 0.5.5
* Added some more T8 models
* Several improvements and fixes

### 1.0.11
* Enabled some features for OZMO 900
* Several minor improvements

### 1.0.10
* Using library version 0.5.4
* Several improvements and fixes
* Added available spot area boundaries to "map" channel (read only)

### 1.0.9
* Using library version 0.5.3
* Added some experimental features (for a few models only)
* Added option for virtual boundaries and some further improvements to adapter config
* Some improvements for js-controller 3.2.x

### 1.0.8
* Using library version 0.5.2
* Added available virtualBoundaries channel for Deebot 900/901 and Ozmo 930 (read only)
* Added "volume" and buttons for resetting consumable values for 950 type models (920/950/T8)
* Improved synchronization of spot area buttons
* Add option for setting the language for spot area names
* Added some experimental features (for a few models only)
* Several enhancements and fixes
* Bump some dependencies

### 1.0.7
* Using library version 0.5.1
* Initial support for Deebot U2 series
* Improved support for Ozmo T8 models
* (boriswerner) Fixed cleaning log for 950 type models (920/950/T8)
* (boriswerner) Added available virtualBoundaries to "map" channel (currently read only)
* Improved handling of device classes
* Several enhancements and fixes

### 1.0.6
* Using library version 0.5.0
* Fix for running multiple devices
* Support for additional Ozmo T8 models
* Add option to synchronize spotArea buttons
* Set state value for triggered buttons to false
* Add option to suppress "unknown" value for "map.deebotPositionCurrentSpotAreaID" state
* Further enhancements and fixes

### 1.0.5
* Bump library to 0.4.25
* Initial support for Ozmo T8 and T8+
* Implement buttons for resetting consumable values (currently Deebot 900/901 and Ozmo 930 only)
* Several enhancements and fixes

### 1.0.4
* Bump library to 0.4.21
* Remove canvas from dependencies
* Several bugfixes and improvements (especially for N79 series)
* Possibility to specify the number of reruns for a spot area
* Spot areas in the "control" channel are now created automatically
* Remove number of spot areas from adapter settings
* Some refactoring
* Bump dependencies

### 1.0.1 - 1.0.3
* Added support for Ozmo T8 AIVI
* Compact mode support
* Added a button to save the last used custom area values
* Added buttons to rerun saved custom areas
* Some enhancements and fixes

### 1.0.0
* Stable release

### 0.0.1 - 0.6.5
* [Changelog archive](https://github.com/mrbungle64/ioBroker.ecovacs-deebot/wiki/Changelog-(archive)#059)

## License

MIT License

Copyright (c) 2022 Sascha Hölzel <mrb1232@posteo.de>

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