---
BADGE-NPM version: http://img.shields.io/npm/v/iobroker.trashschedule.svg
BADGE-Downloads: https://img.shields.io/npm/dm/iobroker.trashschedule.svg
BADGE-Stable: http://iobroker.live/badges/trashschedule-stable.svg
BADGE-Installed: http://iobroker.live/badges/trashschedule-installed.svg
BADGE-Known Vulnerabilities: https://snyk.io/test/github/klein0r/ioBroker.trashschedule/badge.svg
BADGE-NPM: https://nodei.co/npm/iobroker.trashschedule.png?downloads=true
chapters: {"pages":{"de/adapterref/iobroker.trashschedule/README.md":{"title":{"de":"ioBroker.trashschedule"},"content":"de/adapterref/iobroker.trashschedule/README.md"},"de/adapterref/iobroker.trashschedule/blockly.md":{"title":{"de":"ioBroker.trashschedule"},"content":"de/adapterref/iobroker.trashschedule/blockly.md"},"de/adapterref/iobroker.trashschedule/faq.md":{"title":{"de":"ioBroker.trashschedule"},"content":"de/adapterref/iobroker.trashschedule/faq.md"}}}
---
![Logo](../../admin/trashschedule.png)

# ioBroker.trashschedule

## Voraussetzungen

1. Erstelle eine neue Instanz des **ical Adapters**
2. Konfiguriere die URL zu deinem Müllkalender (zum Beispiel ein Google Kalender)
3. Setze die "Tagesvorschau" auf einen Wert, welcher möglichst jeden Abfalltyp mindestens zweimal enthält (z.B. 45 Tage)
4. Falls Du die "Ereignisse" verwendest, stelle sicher, dass bei jedem Ereignis "anzeigen" ausgewählt wurde, welches für den Müllkalender ebenfalls relevant ist (andernfalls werden die Termine vom iCal Adapter ausgeblendet)

![ical](./img/ical.png)

## Konfiguration

1. Erstelle eine ```trashschedule``` Instanz und wähle die ical-Instanz aus, welche den Müllkalender enthält
2. Wechsle in das Tab "Abfalltypen" und füge so viele Zeilen ein, wie Du Abfalltypen hast
3. Vergib einen Namen für jeden Abfalltyp und lege fest, welche Termine im Kalender für diesen Typ relevant sind
4. Starte die Instanz

**Fragen?** Schaue in die [FAQ](./faq.md)

![trashschedule](./img/trashschedule.png)

![trashschedule_types](./img/trashschedule_types.png)

## VIS Widget

![VIS widget](./img/vis.png)

## Changelog

<!--
  Placeholder for the next version (at the beginning of the line):
  ### **WORK IN PROGRESS**
-->
### 2.0.0 (2022-05-04)

NodeJS 14.x is required (NodeJS 12.x is EOL)

* (klein0r) Added timestamp of last and next refresh
* (klein0r) Added icon to channels and fixed color
* (klein0r) Added default trash types for new installations
* (klein0r) Updated dependency for ical to 1.12.1
* (klein0r) Updated depedency for js-controller to 4.0.15

### 1.4.5 (2022-03-21)

* (klein0r) Allow spaces in next text seperator

### 1.4.4 (2022-03-14)

* (klein0r) Updated dependencies

### 1.4.3 (2022-02-21)

* (klein0r) Updated state roles
* (klein0r) Added hint for Admin 4 configuration

### 1.4.2 (2022-02-07)

* (klein0r) Added check for ical configuration

## License

MIT License

Copyright (c) 2022 Matthias Kleine <info@haus-automatisierung.com>

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