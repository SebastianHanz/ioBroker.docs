![Logo](admin/snmp.png)
# ioBroker.snmp

![Number of Installations](http://iobroker.live/badges/snmp-installed.svg)
![Number of Installations](http://iobroker.live/badges/snmp-stable.svg)
[![NPM version](http://img.shields.io/npm/v/iobroker.snmp.svg)](https://www.npmjs.com/package/iobroker.snmp)

![Test and Release](https://github.com/iobroker-community-adapters/iobroker.snmp/workflows/Test%20and%20Release/badge.svg)
[![Translation status](https://weblate.iobroker.net/widgets/adapters/-/snmp/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)
[![Downloads](https://img.shields.io/npm/dm/iobroker.snmp.svg)](https://www.npmjs.com/package/iobroker.snmp)

**This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.**
For more details and for information how to disable the error reporting see [Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

## Info
This adapter polls information from SNMP Device like Printers, Network ...

## Changelog
### 1.0.0 (2022-03-21)
* IMPORTANT: This release will change the object structures!!
* (McM1957) reduce latency for update of info.connection 
* (McM1957) avoid excessive error logs if target is unreachable, optimize logging
* (McM1957) add additional online at ip base to indicate target is reachable
* (McM1957) output warning if OIDs specify different communities for one device
* (Apollon77) Add Sentry for crash reporting

### 0.5.0
* (Marcolotti) Add documentation (de,en,ru)
* (Marcolotti) Add languages (de,en,ru)

### 0.0.3
* (Apollon77)  Fix Object Type

### 0.0.2
* (Bluefox)    Fixes

### 0.0.1
* (Bluefox)    refactoring
* (Marcolotti) initial release

## License
The MIT License (MIT)

Copyright (c) 2017-2022 Marcolotti <info@ct-j.de>, ioBroker Community Developers 

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
