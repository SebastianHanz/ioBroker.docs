---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.sureflap/README.md
title: ioBroker.sureflap
hash: GDlWBe+K/gW1jDuXCwhr5IS3zmwm4/5e8M9zQsoxL0U=
---
![версия NPM](http://img.shields.io/npm/v/iobroker.sureflap.svg)
![Загрузки](https://img.shields.io/npm/dm/iobroker.sureflap.svg)
![Количество установок (последние)](http://iobroker.live/badges/sureflap-installed.svg)
![Количество установок (стабильно)](http://iobroker.live/badges/sureflap-stable.svg)
![Статус зависимости](https://img.shields.io/david/Sickboy78/iobroker.sureflap.svg)
![Известные уязвимости](https://snyk.io/test/github/Sickboy78/ioBroker.sureflap/badge.svg)
![Трэвис-CI](http://img.shields.io/travis/Sickboy78/ioBroker.sureflap/master.svg)
![AppVeyor](https://ci.appveyor.com/api/projects/status/github/Sickboy78/ioBroker.sureflap?branch=master&svg=true)
![НПМ](https://nodei.co/npm/iobroker.sureflap.png?downloads=true)

<p align="center"> <img src="admin/sureflap.png" /> </p>

# IoBroker.sureflap
## Адаптер для умных устройств для домашних животных от Sure Petcare®
<p align="center"> <img src="/admin/SureFlap_Pet_Door_Connect_Hub_Phone.png" /> </p>

## Конфигурация
Добавьте имя пользователя и пароль из своей учетной записи Sure Petcare® на странице конфигурации адаптера.

## Описание
Адаптер предоставляет информацию о настройках и состоянии заслонки для домашних животных, кошачьей заслонки или кормушки.

Он также показывает местонахождение ваших питомцев и их потребление пищи (с кормушкой).

Это позволяет вам контролировать режим блокировки и комендантский час вашего щитка и устанавливать местоположение ваших питомцев.

### Изменяемые значения
Следующие состояния могут быть изменены и вступят в силу на вашем устройстве, соответственно, они будут отражены в вашем приложении Sure Petcare®.

| состояние | описание | допустимые значения |
|-------|-------------|----------------|
| house_name.hub_name.control.led_mode | устанавливает яркость светодиодов хаба | **0** - выкл.<br> **1** - высокий<br> **4** - затемненный |
| house_name.hub_name.flap_name.control.curfew | включает или отключает настроенный комендантский час<br> (комендантский час необходимо настроить через приложение) | **правда** или **ложь** |
| house_name.hub_name.flap_name.control.lockmode | устанавливает режим блокировки | **0** - открыто<br> **1** - заблокировать<br> **2** - блокировка<br> **3** - закрыто (блокировка входа и выхода) |
| домашнее_имя.hub_name.flap_name.assigned_pets.pet_name.control.type | устанавливает тип питомца для назначенного питомца и щитка | **2** - питомец на улице<br> **3** - домашний питомец |
| house_name.hub_name.feeder_name.control.close_delay | задает задержку закрытия крышки кормушки | **0** - быстро<br> **4** - нормальный<br> **20** - медленно |
| имя_домохозяйства.pets.имя_питомца.внутри | устанавливает, находится ли ваш питомец внутри | **правда** или **ложь** |

### Структура
Адаптер создает следующую иерархическую структуру:

адаптер<br> ├ имя_домохозяйства<br> │ ├ имя_хаба<br> │ │ ├ онлайн<br> │ │ ├ управление<br> │ │ │ └ led_mode<br> │ │ ├ имя_фидера<br> │ │ │ ├ аккумулятор<br> │ │ │ ├ battery_percentage<br> │ │ │ ├ онлайн<br> │ │ │ ├ назначенные_питомцы<br> │ │ │ │ └ pet_name<br> │ │ │ ├ чаши<br> │ │ │ │ └ 0..1<br> │ │ │ │ ├ food_type<br> │ │ │ │ ├ цель<br> │ │ │ │ └ вес<br> │ │ │ └ управление<br> │ │ │ └ close_delay<br> │ │ └ имя_клапана<br> │ │ ├ батарея<br> │ │ ├ батарея_процент<br> │ │ ├ комендантский час_активный<br> │ │ ├ онлайн<br> │ │ ├ управление<br> │ │ │ ├ комендантский час<br> │ │ │ └ режим блокировки<br> │ │ ├ комендантский час<br> │ │ │ └ 0..i<br> │ │ │ ├ включен<br> │ │ │ ├ время блокировки<br> │ │ │ └unlock_time<br> │ │ ├ last_curfew<br> │ │ │ └ 0..i<br> │ │ │ ├ включен<br> │ │ │ ├ время блокировки<br> │ │ │ └ время разблокировки<br> │ │ └ назначенные_питомцы<br> │ │ └ pet_name<br> │ │ └ управление<br> │ │ └ тип<br> │ ├ история<br> │ │ └ 0..24<br> │ │ └ ...<br> │ └ домашние животные<br> │ └ pet_name<br> │ ├ внутри<br> │ ├ имя<br> │ ├ так как<br> │ └ еда<br> │ ├ last_time_eaten<br> │ ├ затраченное время<br> │ ├ times_eaten<br> │ └ сухой..мокрый<br> │ └ вес<br> └ информация<br> ├ all_devices_online<br> ├ подключение<br> └ последнее_обновление<br>

## Примечания
SureFlap® и Sure Petcare® являются зарегистрированными товарными знаками [ООО «СюрФлап».](https://www.surepetcare.com/)

Изображение кошачьего щитка, концентратора и приложения для смартфона предоставляется бесплатно от [Конечно Petcare®](https://www.surepetcare.com/en-us/press).

## Changelog

### 1.1.2 (2022-03-06)
* (Sickboy78) improved error and timeout handling
* (Sickboy78) optimized subscribed states

### 1.1.1 (2022-02-20)
* (Sickboy78) removed pet type control from pet flap (is a cat flap exclusive feature)
* (Sickboy78) fixed wrong default value for info.last_update
* (Sickboy78) testing updates for js-controller 4
* (Sickboy78) security updates

### 1.1.0 (2022-01-17)
* (Sickboy78) bugfix and security updates

### 1.0.9 (2022-01-05)
* (Sickboy78) removed old encrypt/decrypt from index_m
* (Sickboy78) added adapter unloaded guard in case unload happens during data requests

### 1.0.8 (2021-11-22)
* (Sickboy78) added food type, target weight and remaining food in feeder
* (Sickboy78) added todays pet food consumption, times eaten and time spent

### 1.0.7 (2021-11-02)
* (Sickboy78) added history
* (Sickboy78) added last update time

### 1.0.6 (2021-09-12)
* (Sickboy78) added feeder support (closing delay of lid)
* (Sickboy78) added led control for hub
* (Sickboy78) added assigned pets for flap and feeder devices
* (Sickboy78) added pet type control (indoor or outdoor) for assigned pets for flap devices
* (Apollon77) update CI testing

### 1.0.5 (2021-04-25)
* (Sickboy78) fixed bug in case pets didn't have a position (e.g. no flaps, only feeder in use)

### 1.0.4 (2021-03-07)
* (Sickboy78) added state curfew_active for pet flap devices
* (Sickboy78) fixed normalization of device names
* (Sickboy78) fixed changeable values not resetting when change fails

### 1.0.3 (2021-02-28)
* (Sickboy78) code improvements from review
* (Sickboy78) fixed timezone bug

### 1.0.2 (2021-02-25)
* (Sickboy78) fixed bug setting lockmode and inside values

### 1.0.1 (2021-02-19)
* (Sickboy78) initial release

## License

MIT License

Copyright (c) 2022 Sickboy78 <asmoday_666@gmx.de>

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