![Logo](admin/sony-bravia.png)

# ioBroker.sony-bravia

![Number of Installations](http://iobroker.live/badges/sony-bravia-installed.svg)
![Number of Installations](http://iobroker.live/badges/sony-bravia-stable.svg)
[![NPM version](http://img.shields.io/npm/v/iobroker.sony-bravia.svg)](https://www.npmjs.com/package/iobroker.sony-bravia)

![Test and Release](https://github.com/iobroker-community-adapters/iobroker.sony-bravia/workflows/Test%20and%20Release/badge.svg)
[![Translation status](https://weblate.iobroker.net/widgets/adapters/-/sony-bravia/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)
[![Downloads](https://img.shields.io/npm/dm/iobroker.sony-bravia.svg)](https://www.npmjs.com/package/iobroker.sony-bravia)

**This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.


## A Sony Bravia Android Smart-TV adapter for ioBroker

This is an ioBroker adapter for your Sony Bravia Smart-TV with Android OS. Tested with KD-65X8507C.

## TV Setup
* Turn on your TV
* On the TV go to Settings > Network > Home network setup > Remote device/Renderer > On
* On the TV go to Settings > Network > Home network setup > IP Control > Authentication > Normal and Pre-Shared Key
* On the TV go to Settings > Network > Home network setup > Remote device/Renderer > Enter Pre-Shared Key > 0000 (or whatever you want your PSK Key to be)
* On the TV go to Settings > Network > Home network setup > Remote device/Renderer > Simple IP Control > On

## Changelog
### 1.0.8 (2022-04-25)
* (Apollon77) Fix crash cases reported by sentry

### 1.0.7 (2022-04-24)
* (Apollon77) Fix tier definition

### 1.0.6 (2022-04-23)
* (ThomasBra) Audio volume/mute control
* (ThomasBra) value lists for AV Contents
* (Apollon77) Add Sentry error reporting

### 1.0.5
* (ThomasBra) Fix for content list request for older api versions

### 1.0.4
* (ThomasBra) Added info.modelInformation
* (ThomasBra) Added info.playingContentInfo - title of the used channel or port
* (ThomasBra) Set info.powerStatusActive changeable
* (ThomasBra) Turn over to tv channels - the first 150 listed tv channels
* (ThomasBra) Turn over to AV Content - external input
* (ThomasBra) Starting / Terminate Apps
* (ldittmar) Fixes from adapter checker

### 1.0.3
* (Apollon77) info.powerStatusActive added and other optimizations

### 1.0.2
* (raintonr) Added info.powerStatusActive
* (raintonr) Optimizations

### 1.0.1
* (ldittmar) compact mode compatibility added
* (ldittmar) add chinese support

### 1.0.0
* (ldittmar) Support of admin3

### 0.1.0
* (ldittmar) Test phase terminated. Adapter enabled.

### 0.0.5
* (ldittmar) Open beta test phase - please test it and give me feedback here as a issue or in the forum http://forum.iobroker.net/viewtopic.php?f=23&t=6406

### 0.0.1
* (ldittmar) initial release

## License
The MIT License (MIT)

Copyright (c) 2018-2022 ldittmar <iobroker@lmdsoft.de>

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
