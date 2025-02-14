---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.hass/README.md
title: ioBroker.hass
hash: miH711nLAOxOLZP7MtUd6GLoOm4iN1J8JHPbulklyQU=
---
![Logo](../../../en/adapterref/iobroker.hass/admin/hass.png)

![Anzahl der Installationen](http://iobroker.live/badges/hass-stable.svg)
![NPM-Version](http://img.shields.io/npm/v/iobroker.hass.svg)
![Downloads](https://img.shields.io/npm/dm/iobroker.hass.svg)

# IoBroker.hass
![Testen und freigeben](https://github.com/ioBroker/ioBroker.hass/workflows/Test%20and%20Release/badge.svg) [![Übersetzungsstatus](https://weblate.iobroker.net/widgets/adapters/-/hass/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

**Dieser Adapter verwendet Sentry-Bibliotheken, um Ausnahmen und Codefehler automatisch an die Entwickler zu melden.** Weitere Details und Informationen zum Deaktivieren der Fehlerberichterstattung finden Sie unter [Sentry-Plugin-Dokumentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry Reporting wird ab js-controller 3.0 verwendet.

Dieser Adapter ermöglicht die Verbindung von Home Assistant mit ioBroker.

## Verwendungszweck
Erstellen Sie ein Langzeit-Token in HASS und verwenden Sie es als PW (kopieren Sie es auch in das Wiederholungsfeld).

Dann sollte es alle Attribute für alle Geräte auslesen. Dienste können steuerbar sein (z. B. "turn_on"). Um Dienste zu steuern, haben Sie zwei Möglichkeiten:

* Setzen Sie den Status mit einem ack=false-Wert, der kein String ist (z. B. Boolean true), dann wird er auch in HASS ohne zusätzliche Servicedaten ausgelöst
* Setzen Sie den Status mit einem ack=false String-Wert, der ein stringifiziertes JSON-Objekt ist, um den Dienst aufzurufen und das JSON-Objekt als Dienstdaten zu verwenden

Für die letzte Option auf einem light.turn_off mit z.B. `{"transition":10,"flash":"short"}` diese beiden Dienstdaten werden mit dem Anruf an HASS gesendet. Die verfügbaren Felder mit ihrer Datendefinition sind in der JSON-Definition des ioBroker-Objekts im Abschnitt native.fields zu sehen und würden im obigen Beispiel wie folgt aussehen:

` ...
native: { "fields": { "transition": { "name": "Transition", "description": "Dauer bis zum nächsten Zustand.", "selector": { "number": { "min" : 0, "max": 300, "unit_of_measurement": "seconds" } } }, "flash": { "name": "Flash", "description": "Wenn das Licht blinken soll.", "advanced": true, "selector": { "select": { "options": [ "long", "short" ] } } } }, "entity_id": "light.mi_control_hub_light", "attr": "turn_off", "type ": "hell" } ...
`

Für einige Dienste wie set_speed ist es im Allgemeinen erforderlich, mit einem JSON-Objekt wie `{speed: "high"}` aufzurufen, um erforderliche Werte bereitzustellen. In diesem Fall sieht die Felddefinition z.B. wie:

```
...
    native: {
        "fields": {
            "speed": {
                "name": "Speed",
                "description": "Speed setting.",
                "required": true,
                "example": "low",
                "selector": {
                    "text": null
                }
            }
        }
        ...
    }
...
```

## Aufbau
Es gibt einen guten Artikel über Verbindungen.

Bitte prüfen Sie es https://www.smarthomejetzt.de/mit-iobroker-auf-eine-home-assistant-hass-io-installation-und-die-geraete-zugreifen/

**Leider nur auf deutsch, aber die [google translate funktioniert ziemlich gut](https://translate.google.com/translate?hl=en&sl=de&tl=en&u=https%3A%2F%2Fwww.smarthomejetzt.de%2Fmit-iobroker-auf-eine-home-assistant-hass-io-installation-und-die-geraete-zugreifen%2F)**

<!-- Platzhalter für die nächste Version (am Zeilenanfang):

### __LAUFENDE ARBEIT__ -->

## Changelog
### 1.1.0 (2022-03-24)
* IMPORTANT: You need to re-enter the password once after installing this version!
* (Apollon77) Implement Service triggers to use any value to trigger or stringified JSON to call with fields
* (Apollon77) Optimize unload handling
* (Apollon7) Add Sentry for crash reporting

### 1.0.1 (2021-09-04)
* IMPORTANT: js-controller 2.0 is needed st least!
* (Apollon77) Fix start issue
* (Apollon77/Garfonso) Fix issue where value could not be set in hass

### 1.0.0 (2020-12-13)
* (bluefox) added the support of compact mode

### 0.1.0
* (bluefox) initial release

## License
The MIT License (MIT)

Copyright (c) 2018-2022 bluefox <dogafox@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.