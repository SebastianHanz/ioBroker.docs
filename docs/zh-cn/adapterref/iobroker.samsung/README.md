---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.samsung/README.md
title: 无题
hash: jh8cSyMnRQLumhvkFReWrgiKqYwaL3zAjaUcM4Y07Js=
---
![商标](../../../en/adapterref/iobroker.samsung/admin/samsung.png)

![安装数量](http://iobroker.live/badges/samsung-stable.svg)
![NPM 版本](http://img.shields.io/npm/v/iobroker.samsung.svg)
![下载](https://img.shields.io/npm/dm/iobroker.samsung.svg)

### IoBroker.samsung
![测试和发布](https://github.com/iobroker-community-adapters/ioBroker.samsung/workflows/Test%20and%20Release/badge.svg) <!-- [![翻译状态](https://weblate.iobroker.net/widgets/adapters/-/samsung/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)-->

**此适配器使用 Sentry 库自动向开发人员报告异常和代码错误。**有关更多详细信息以及如何禁用错误报告的信息，请参阅[Sentry 插件文档](https://github.com/ioBroker/plugin-sentry#plugin-sentry)！从 js-controller 3.0 开始使用哨兵报告。

＃＃＃＃ 描述
三星电视适配器

### 初始创建
该适配器最初由 @soef 在 https://github.com/soef/ioBroker.samsung 创建，但不再维护，因此我们将其移至 iobroker-community 以便修复错误。感谢@soef 的工作。
此后，jogibear9988 和 mwp007 使用更多 Api 扩展了适配器。

＃＃＃＃ 配置
输入三星电视的 IP。
选择您的 API：Samsung Remote - 2014 年之前的电视 安装后，您必须确认电视上的新连接 Samsung HJ - 2014 和 2015 首次连接后，您需要输入电视上显示的 Pin 图。
Samsung2016 - 自我解释 SamsungTV - 2016 年后的 Tizen 电视

＃＃＃＃ 安装
通过 ioBroker 管理员。

否则在 iobroker 根目录下执行以下命令（例如在 /opt/iobroker 中）

```
iobroker install samsung
```

要么

```
npm install iobroker.samsung
```

＃＃＃＃ 要求
三星电视<br>我在 UE55HU7200 上测试的 HJ 系列。自 2016 年以来对设备的支持实验性如果某些东西不起作用，请查看日志。

## Changelog
### 0.5.1 (2022-03-25)
* (Apollon77) General updates
* (Apollon77) Add Sentry for Crash reporting

### 0.5.0
* New api Type for H and J Series (2014 + 2015)

### 0.4.0
* New api Type, removed node 4 check

### 0.2.9
* Update utils.js and usage, CI Testing and deps (Apollon77)",

## License
The MIT License (MIT)

Copyright (c) 2015-2017 soef <soef@gmx.net>, 2018-2022 ioBroker Community