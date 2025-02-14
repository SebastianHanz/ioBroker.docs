---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.hass/README.md
title: ioBroker.hass
hash: miH711nLAOxOLZP7MtUd6GLoOm4iN1J8JHPbulklyQU=
---
![商标](../../../en/adapterref/iobroker.hass/admin/hass.png)

![安装数量](http://iobroker.live/badges/hass-stable.svg)
![NPM 版本](http://img.shields.io/npm/v/iobroker.hass.svg)
![下载](https://img.shields.io/npm/dm/iobroker.hass.svg)

# IoBroker.hass
![测试和发布](https://github.com/ioBroker/ioBroker.hass/workflows/Test%20and%20Release/badge.svg)[![翻译状态](https://weblate.iobroker.net/widgets/adapters/-/hass/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

**此适配器使用 Sentry 库自动向开发人员报告异常和代码错误。**有关更多详细信息以及如何禁用错误报告的信息，请参阅[Sentry 插件文档](https://github.com/ioBroker/plugin-sentry#plugin-sentry)！从 js-controller 3.0 开始使用哨兵报告。

此适配器允许将 Home Assistant 连接到 ioBroker。

＃＃ 用法
在 HASS 中创建一个长期令牌并将其用作 PW（也将其复制到重复字段中）。

然后它应该读出所有设备的所有属性。服务可能是可控的（例如“turn_on”）。要控制服务，您有两种选择：

* 使用不是字符串的 ack=false 值设置状态（例如，布尔值 true），然后它也将在 HASS 中触发，无需额外的服务数据
* 使用 ack=false 字符串值设置状态，该字符串值是字符串化的 JSON 对象以调用服务并将 JSON 对象用作服务数据

对于 light.turn_off 上的最后一个选项，例如`{"transition":10,"flash":"short"}`这两个服务数据详细信息随对 HASS 的调用发送。可用字段及其数据定义可以在 native.fields 部分的 ioBroker 对象的 JSON 定义中看到，并且在上面的示例中如下所示：

` ...
本机：{“字段”：{“转换”：{“名称”：“转换”，“描述”：“进入下一个状态所需的持续时间。”，“选择器”：{“数字”：{“分钟” : 0, "max": 300, "unit_of_measurement": "seconds" } } }, "flash": { "name": "Flash", "description": "如果灯应该闪烁。", "advanced":真，“选择器”：{“选择”：{“选项”：[“长”，“短”]}}}}}，“实体ID”：“light.mi_control_hub_light”，“属性”：“关闭”，“类型“： “光” } ...
`

对于像 set_speed 这样的一些服务，通常需要使用像 `{speed: "high"}` 这样的 JSON 对象来调用以提供所需的值。在这种情况下，字段定义看起来例如喜欢：

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

＃＃ 配置
有一篇关于连接的好文章。

请检查它 https://www.smarthomejetzt.de/mit-iobroker-auf-eine-home-assistant-hass-io-installation-und-die-geraete-zugreifen/

**不幸的是只有德语，但[谷歌翻译效果不错](https://translate.google.com/translate?hl=en&sl=de&tl=en&u=https%3A%2F%2Fwww.smarthomejetzt.de%2Fmit-iobroker-auf-eine-home-assistant-hass-io-installation-und-die-geraete-zugreifen%2F)**

<!-- 下一个版本的占位符（在行首）：

### __工作进行中__ -->

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