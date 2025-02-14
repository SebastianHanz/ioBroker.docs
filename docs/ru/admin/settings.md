---
title: системные настройки
lastChanged: 27.03.2019
translatedFrom: de
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/admin/settings.md
hash: EWCPIroHVv8aZWVTS96ljn+F7vclaiYghLknECzG9Fw=
---
# Системные настройки
Доступ к системным настройкам можно получить из любого пункта меню администратора через значок гаечного ключа в строке заголовка экрана.

![Системные настройки](../../de/admin/media/ADMIN_Settings_main.png)

Системные настройки разделены на несколько подстраниц:

## Основные параметры
В основных настройках задаются базовые параметры для ioBroker, которые также используются адаптерами в ioBroker.

Некоторые параметры уже взяты из настроек хоста.

**Язык системы**

вы можете выбирать между различными системными языками. Возможно, не все языки полностью поддерживаются.

**Единица измерения температуры**

это значение используется некоторыми адаптерами. Возможно °C или °F.

**Валюта**

На данный момент он не использует адаптер

**Формат даты**

выберите способ отображения даты в admin и vis.

**Десятичный разделитель**

Запятая или точка для значений с плавающей запятой

**Экземпляр истории по умолчанию**

По умолчанию данные записываются в этот экземпляр и используются в картах флота и рикши.

Если установлен только один адаптер истории (SQL/History/InfluxDB), то будет использоваться он, если их несколько, то можно выбрать один.

**Активный репозиторий**

Здесь нужный репозиторий, из которого должна быть установлена версия адаптера, выбирается в раскрывающемся меню. Репозитории, перечисленные в разделе «Репозитории», доступны в раскрывающемся меню.

## Репозиторий
![Депозитарии](../../de/admin/media/ADMIN_Settings_repos.png)

ioBroker может получить список адаптеров из разных источников. При установке вводятся следующие источники:

* по умолчанию (=стабильно): http://download.iobroker.net/sources-dist.json
* последняя (=бета): http://download.iobroker.net/sources-dist-latest.json

Если здесь указаны другие репозитории из более старой установки, их следует удалить, поскольку они больше не поддерживаются.

## Сертификаты
![сертификаты](../../de/admin/media/ADMIN_Settings_certificates.png)

Здесь находится центральное расположение сертификатов, используемых для связи SSL/HTTPS. Сертификаты используются admin, web, simple-api, socketio. Стандартные сертификаты устанавливаются по умолчанию. С этим ничего не проверишь. Они используются только для связи SSL. Поскольку сертификаты открыты, вам следует использовать собственные (самозаверяющие) сертификаты, покупать настоящие сертификаты или перейти на Let's Encrypt. Связь с сертификатами по умолчанию небезопасна, и если кто-то хочет прочитать трафик, это можно сделать. Обязательно установите собственные сертификаты.
Например. под линуксом.

Сертификаты можно указать в виде пути или полностью загрузить с помощью перетаскивания.

--- title: System Settings lastChanged: 27.03.2019 ---

# Системные настройки
Доступ к системным настройкам можно получить из любого пункта меню администратора через значок гаечного ключа в строке заголовка экрана.

![Системные настройки](../../de/admin/media/ADMIN_Settings_main.png)

Системные настройки разделены на несколько подстраниц:

## Основные параметры
В основных настройках задаются базовые параметры для ioBroker, которые также используются адаптерами в ioBroker.

Некоторые параметры уже взяты из настроек хоста.

**Язык системы**

вы можете выбирать между различными системными языками. Возможно, не все языки полностью поддерживаются.

**Единица измерения температуры**

это значение используется некоторыми адаптерами. Возможно °C или °F.

**Валюта**

На данный момент он не использует адаптер

**Формат даты**

выберите способ отображения даты в admin и vis.

**Десятичный разделитель**

Запятая или точка для значений с плавающей запятой

**Экземпляр истории по умолчанию**

По умолчанию данные записываются в этот экземпляр и используются в картах флота и рикши.

Если установлен только один адаптер истории (SQL/History/InfluxDB), то будет использоваться он, если их несколько, то можно выбрать один.

**Активный репозиторий**

Здесь нужный репозиторий, из которого должна быть установлена версия адаптера, выбирается в раскрывающемся меню. Репозитории, перечисленные в разделе «Репозитории», доступны в раскрывающемся меню.

## Репозиторий
![Депозитарии](../../de/admin/media/ADMIN_Settings_repos.png)

ioBroker может получить список адаптеров из разных источников. При установке вводятся следующие источники:

* по умолчанию (=стабильно): http://download.iobroker.net/sources-dist.json
* последняя (=бета): http://download.iobroker.net/sources-dist-latest.json

Если здесь указаны другие репозитории из более старой установки, их следует удалить, поскольку они больше не поддерживаются.

## Сертификаты
![сертификаты](../../de/admin/media/ADMIN_Settings_certificates.png)

Здесь находится центральное расположение сертификатов, используемых для связи SSL/HTTPS. Сертификаты используются admin, web, simple-api, socketio. Стандартные сертификаты устанавливаются по умолчанию. С этим ничего не проверишь. Они используются только для связи SSL. Поскольку сертификаты открыты, вам следует использовать собственные (самозаверяющие) сертификаты, покупать настоящие сертификаты или перейти на Let's Encrypt. Связь с сертификатами по умолчанию небезопасна, и если кто-то хочет прочитать трафик, это можно сделать. Обязательно установите собственные сертификаты.
Например. под линуксом.

Сертификаты можно указать в виде пути или полностью загрузить с помощью перетаскивания.

<span style="color:red">Как правило, рекомендуется тестировать новые сертификаты с помощью веб-адаптера, а не напрямую с адаптером администратора, чтобы не заблокировать себя в системе.</span>

При указании пути должны присутствовать правильные разрешения для пользователя iobroker.

Для самого файла 644, для родительских каталогов 755.

Если права неверны, появляется сообщение об ошибке вида:

``web.0 (24704) Cannot create webserver: Error: error:0909006C:PEM routines:get_name:no start line``

Вы можете проверить доступ, войдя на сервер как пользователь root, затем переключившись на пользователя iobroker и указав файл сертификата:

``su iobroker``

``ls -l /Pfad/zum/Zertifikat``

Вы должны увидеть **-rw-r--r--** в начале строки.

Если фактический сертификат связан, необходимо проверить права цели ссылки.

Вот приходит сообщение типа

``ls: Zugriff auf '/Pfad/zum/Zertifikat' nicht möglich: Keine Berechtigung``

Права надо настроить.

Как пользователь root для файла:

``chmod 644 /Pfad/zum/Zertifikat``

Для родительских каталогов:

``chmod 755 /Pfad/zum``

## Давайте зашифруем
![Давайте зашифруем](../../de/admin/media/ADMIN_Settings_letsencrypt.png)

Let’s Encrypt — это бесплатный автоматизированный центр сертификации с открытым исходным кодом от независимой исследовательской группы по безопасности в Интернете (ISRG).

Для получения дополнительной информации о Let's Encrypt см. [здесь](https://letsencrypt.org/).

Некоторые установки используют динамический DNS или аналогичный для доступа к собственному домену через назначенный оттуда адрес. ioBroker поддерживает автоматический запрос и обновление сертификатов организации Let's Encrypt.

Возможность использования бесплатных сертификатов Let's Encrypt существует почти в каждом адаптере, который может запускать веб-сервер и поддерживает HTTPS.

Если вы активируете опцию использования сертификатов, но не автоматическое обновление, соответствующий экземпляр пытается работать с сохраненными сертификатами.

Если автоматическое обновление включено, экземпляр пытается запросить сертификаты у Let's Encrypt и автоматически их обновляет.

Сертификаты запрашиваются в первый раз, когда соответствующий адрес вызывается в первый раз. Это означает, что если вы настроите, например, «sub.domain.com» в качестве адреса, а затем вызовете https://sub.domain.com, сертификаты будут запрошены в первый раз, что может занять некоторое время, прежде чем придет ответ.

Выдача сертификатов — сложная процедура, но, следуя приведенным ниже объяснениям, получить бесплатные сертификаты будет легко.

**Метод:**

Должна быть создана новая учетная запись с введенным адресом электронной почты (настройка для этого в настройках системы)

В качестве пароля для учетной записи генерируется случайный ключ.

Когда учетная запись создана, система открывает небольшой веб-сайт на порту 80 для проверки адреса.

Let's encrypt всегда использует порт 80 для проверки адреса.

Если порт 80 уже используется другой службой, применяется пункт 4 — т. е. назначьте другой порт другой службе!

При запуске малого веб-сервера запрос сертификатов для адресов, указанных в настройках системы, отправляется на сервер Let's encrypt.

Сервер Let's Encrypt отправляет обратно контрольную фразу в ответ на запрос и через некоторое время пытается прочитать эту контрольную фразу по адресу «http://yourdomain:80/.well-known/acme-challenge/».

Когда сервер получает эту контрольную фразу с нашей стороны, сервер Let's Encrypt отправляет сертификаты. Они сохраняются в каталоге, указанном в системных настройках.

Это звучит сложно, но все, что вам нужно сделать, это установить несколько флажков и ввести адрес электронной почты и веб-адрес в настройках системы.

Полученные сертификаты действительны в течение примерно 90 дней. После того, как эти сертификаты выданы в первый раз, запускается другая задача, которая автоматически продлевает срок действия.

Эта тема довольно сложна, и тысячи вещей могут пойти не так. Если это не сработает, мы рекомендуем использовать адаптер IoT для доступа, когда вы в пути.

Let’s Encrypt работает только с версией node.js >=4.5.

## Права доступа
![права доступа](../../de/admin/media/ADMIN_Settings_zugriffsrechte.png)

На этой подстранице права доступа к различным областям могут быть определены для всех пользователей/групп.

## Статистика
![статистика](../../de/admin/media/ADMIN_Settings_statistics.png)

Так что у нас есть небольшой обзор установок (используемых адаптеров) и географического распределения, мы были бы очень рады, если бы получили эту информацию.

Вы можете отправлять разное количество информации. Этот диапазон можно выбрать слева.

Затем правая сторона показывает точную форму, в которой эти данные отправляются.
Эти данные оцениваются абсолютно анонимно.

## Давайте зашифруем
![Давайте зашифруем](../../de/admin/media/ADMIN_Settings_letsencrypt.png)

Let’s Encrypt — это бесплатный автоматизированный центр сертификации с открытым исходным кодом от независимой исследовательской группы по безопасности в Интернете (ISRG).

Для получения дополнительной информации о Let's Encrypt см. [здесь](https://letsencrypt.org/).

Некоторые установки используют динамический DNS или аналогичный для доступа к собственному домену через назначенный оттуда адрес. ioBroker поддерживает автоматический запрос и обновление сертификатов организации Let's Encrypt.

Возможность использования бесплатных сертификатов Let's Encrypt существует почти в каждом адаптере, который может запускать веб-сервер и поддерживает HTTPS.

Если вы активируете опцию использования сертификатов, но не автоматическое обновление, соответствующий экземпляр пытается работать с сохраненными сертификатами.

Если автоматическое обновление включено, экземпляр пытается запросить сертификаты у Let's Encrypt и автоматически их обновляет.

Сертификаты запрашиваются в первый раз, когда соответствующий адрес вызывается в первый раз. Это означает, что если вы настроите, например, «sub.domain.com» в качестве адреса, а затем вызовете https://sub.domain.com, сертификаты будут запрошены в первый раз, что может занять некоторое время, прежде чем придет ответ.

Выдача сертификатов — сложная процедура, но, следуя приведенным ниже объяснениям, получить бесплатные сертификаты будет легко.

**Метод:**

Должна быть создана новая учетная запись с введенным адресом электронной почты (настройка для этого в настройках системы)

В качестве пароля для учетной записи генерируется случайный ключ.

Когда учетная запись создана, система открывает небольшой веб-сайт на порту 80 для проверки адреса.

Let's encrypt всегда использует порт 80 для проверки адреса.

Если порт 80 уже используется другой службой, применяется пункт 4 — т. е. назначьте другой порт другой службе!

При запуске малого веб-сервера запрос сертификатов для адресов, указанных в настройках системы, отправляется на сервер Let's encrypt.

Сервер Let's Encrypt отправляет обратно контрольную фразу в ответ на запрос и через некоторое время пытается прочитать эту контрольную фразу по адресу «http://yourdomain:80/.well-known/acme-challenge/».

Когда сервер получает эту контрольную фразу с нашей стороны, сервер Let's Encrypt отправляет сертификаты. Они сохраняются в каталоге, указанном в системных настройках.

Это звучит сложно, но все, что вам нужно сделать, это установить несколько флажков и ввести адрес электронной почты и веб-адрес в настройках системы.

Полученные сертификаты действительны в течение примерно 90 дней. После того, как эти сертификаты выданы в первый раз, запускается другая задача, которая автоматически продлевает срок действия.

Эта тема довольно сложна, и тысячи вещей могут пойти не так. Если это не сработает, мы рекомендуем использовать адаптер IoT для доступа, когда вы в пути.

Let’s Encrypt работает только с версией node.js >=4.5.

## Права доступа
![права доступа](../../de/admin/media/ADMIN_Settings_zugriffsrechte.png)

На этой подстранице права доступа к различным областям могут быть определены для всех пользователей/групп.

## Статистика
![статистика](../../de/admin/media/ADMIN_Settings_statistics.png)

Так что у нас есть небольшой обзор установок (используемых адаптеров) и географического распределения, мы были бы очень рады, если бы получили эту информацию.

Вы можете отправлять разное количество информации. Этот диапазон можно выбрать слева.

Затем правая сторона показывает точную форму, в которой эти данные отправляются.
Эти данные оцениваются абсолютно анонимно.