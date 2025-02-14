![Logo](admin/youtube.png)

# ioBroker.youtube

[![NPM version](http://img.shields.io/npm/v/iobroker.youtube.svg)](https://www.npmjs.com/package/iobroker.youtube)
[![Downloads](https://img.shields.io/npm/dm/iobroker.youtube.svg)](https://www.npmjs.com/package/iobroker.youtube)
[![Stable](http://iobroker.live/badges/youtube-stable.svg)](http://iobroker.live/badges/youtube-stable.svg)
[![installed](http://iobroker.live/badges/youtube-installed.svg)](http://iobroker.live/badges/youtube-installed.svg)
[![Known Vulnerabilities](https://snyk.io/test/github/klein0r/ioBroker.youtube/badge.svg)](https://snyk.io/test/github/klein0r/ioBroker.youtube)
![Test and Release](https://github.com/klein0r/ioBroker.youtube/workflows/Test%20and%20Release/badge.svg)

[![NPM](https://nodei.co/npm/iobroker.youtube.png?downloads=true)](https://nodei.co/npm/iobroker.youtube/)

Statistics like views, subscribers and videos

## Sponsored by

[![ioBroker Master Kurs](https://haus-automatisierung.com/images/ads/ioBroker-Kurs.png)](https://haus-automatisierung.com/iobroker-kurs/?refid=iobroker-youtube)

## Installation

Please use the "adapter list" in ioBroker to install a stable version of this adapter. You can also use the CLI to install this adapter:

```
iobroker add youtube
```

## Configuration

To get an API-Key you have to go to [console.developers.google.com](https://console.developers.google.com/apis/dashboard).

1. Create a new Project
2. Create a new API key
3. Add "YouTube Data API v3" of the library
4. Use that API-Key in the options panel
5. Add multiple channels in the channels tab by using the id and a custom name

## Changelog

<!--
  Placeholder for the next version (at the beginning of the line):
  ### **WORK IN PROGRESS**
-->
### **WORK IN PROGRESS**

NodeJS 14.x is required (NodeJS 12.x is EOL)

* (klein0r) Updated depedency for js-controller to 4.0.15

### 3.0.1 (2022-03-17)

* (klein0r) Just perform video info request if previous request was successful
* (klein0r) Improved error handling when API key is missing
* (klein0r) Updated logging

### 3.0.0 (2022-02-12)

* (klein0r) Updated state roles
* (klein0r) Added hint for Admin 4 configuration

### 2.0.4 (2021-12-23)

* (klein0r) Translated all objects
* (klein0r) Updated dependencies

### 2.0.3 (2021-11-07)

* (klein0r) Fixed missing VIS widget

### 2.0.1 (2021-11-06)

* (klein0r) Fixed missing translations

## License

The MIT License (MIT)

Copyright (c) 2022 Matthias Kleine <info@haus-automatisierung.com>

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
