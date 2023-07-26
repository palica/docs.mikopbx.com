# Системные настройки

В данном разделе производится настройка основных параметров системы. Данные параметры рекомендуется настраивать сразу после установки АТС.

<figure><img src="../../.gitbook/assets/1 (48).png" alt=""><figcaption></figcaption></figure>

## Основные <a href="#osnovnye" id="osnovnye"></a>

* **Название PBX системы** - будет отображаться на главной странице MikoPBX
* **Дополнительное описание** - будут видеть только администраторы системы.
* **Язык звуковых сообщений** - укажите язык оповещений
* **Длина внутреннего номера** - **максимальная** длина внутреннего номера (для сотрудников)
* **Максимальный таймаут между цифрами при вводе добавочного**
* **Перезапускать АТС каждую ночь** - рестарт asterisk каждую ночь
* **Отправлять разработчикам информацию о сбоях** - при возникновении ошибки, ее описание будет выслано разработчикам (требуется доступ в интернет)

<figure><img src="../../.gitbook/assets/2 (5).png" alt=""><figcaption></figcaption></figure>

## Запись разговоров <a href="#zapis_razgovorov" id="zapis_razgovorov"></a>

* **Запись разговоров** - позволяет включить / отключить запись
* Запись внутренних разговоров - позволяет включить / отключить запись внутренних разговоров
* **Сохранять записи разговоров в стерео режиме** изменяет режим записи с **mono** на **stereo**. Поток записи будет разделен на входящий и исходящий и объединен в стерео файл.

Имеется слайдер, с помощью которого можно выбрать сколько будут храниться записи разговоров.

Так же можно выбрать звуковой файл для предупреждения о записи разговоров.

<figure><img src="../../.gitbook/assets/5 (28).png" alt=""><figcaption></figcaption></figure>

Телефонные звонки сохраняются в формате **mp3**. Пример информации об итоговом файле записи разговора:

```
Input File     : 'mikopbx-1554098285.0_M1gEr1pgrt.mp3'
Channels       : 1
Sample Rate    : 8000
Precision      : 16-bit
Duration       : 00:00:17.64 = 141120 samples ~ 1323 CDDA sectors
File Size      : 70.6k
Bit Rate       : 32.0k
Sample Encoding: MPEG audio (layer I, II or III)
```

{% hint style="info" %}
Ориентировочно, **1 час** разговора занимает **14Мб** места на диске.
{% endhint %}

## Переводы вызовов <a href="#perevody_vyzovov" id="perevody_vyzovov"></a>

<figure><img src="../../.gitbook/assets/4 (30).png" alt=""><figcaption></figcaption></figure>

#### Парковка (Удержание) <a href="#parkovka_uderzhanie" id="parkovka_uderzhanie"></a>

**Парковка** - это вариант «**удержания**» клиента на линии. Полезно использовать в том случае, когда необходимо временно разъединиться с клиентом для уточнения некоторой информации. Клиенту во время парковки будет проигрываться мелодия.

В MikoPBX возможно два варианта парковки вызова от клиента:

1. Если вам необходимо запарковать вызов клиента, введите **\*2**. Вызов клиента MikoPBX поставит на удержание, а Вам сообщит номер слота припаркованного вызова. Любой сотрудник может забрать вызов, набрав с телефона номер слота припаркованного вызова.
2. В разделе **Переводы вызовов** задайте **номер для парковки**. При **переадресации** вызова клиента на номер парковки, MikoPBX поставит такой вызов на удержание, а Вам сообщит номер слота припаркованного вызова. Любой сотрудник может забрать вызов, набрав с телефона номер слота припаркованного вызова.

Диапазон номеров слота припаркованного вызова можно задать в разделе **Переводы вызовов**: **Начальный парковочный слот** и **Конечный парковочный слот**.

#### Переводы вызовов <a href="#perevody_vyzovov1" id="perevody_vyzovov1"></a>

MikoPBX предлагает два вида переводов: **Условный** и **Безусловный** (слепой).

* При использовании **условного перевода** Вы можете поговорить с человеком прежде, чем переадресовать вызов. Вызывающий абонент находится в это время на удержании. После того как человек, который переадресовывает вызов, вешает трубку, переадресация успешно завершается.
* Если вы переведете вызов, не поговорив предварительно с коллегой, то этот перевод **Безусловный**. Например, если вам поступает второй входящий звонок, а Вы уже разговариваете по телефону. Чтобы не прерывать текущий вызов, Вы переводите новый вызов на свободного коллегу.

{% hint style="info" %}
* По умолчанию комбинация для условного перевода - две решетки
* По умолчанию комбинация для безусловного перевода - две звездочки
{% endhint %}

#### Таймауты <a href="#tajmauty" id="tajmauty"></a>

Время возврата вызова если нет ответа после безусловного (слепого) перевода - **45 сек**.

#### Перехват (Pickup) <a href="#perexvat_pickup" id="perexvat_pickup"></a>

Если звонит телефон коллеги, то есть возможность перехватить вызов набрав **\*8<НомерКоллеги>**.\
Если номер коллеги не известен, то можно просто набрать **\*8**.

## SIP <a href="#sip" id="sip"></a>

<figure><img src="../../.gitbook/assets/5 (26).png" alt=""><figcaption></figcaption></figure>

**Session Initiation Protocol (SIP)** является сигнальным протоколом, используемым большинством телефонов VoIP. Вы можете изменить SIP-порт(по умолчанию порт 5060) для повышения безопасности. Кроме того, некоторым SIP провайдерам необходимы дополнительные параметры, такие как **Периоды регистрации** (Время через которое регистрация будет сброшена). Некоторые брандмауэры закрывают порты после периода неактивности. Такое поведение может потребовать сократить время ожидания регистрации SIP провайдеров. Другой причиной может быть необходимость в различных **тайм-аутах при регистрации** некоторых SIP-провайдеров. Значения по умолчанию:

* **SIPMiniExpiry** - минимальная продолжительность регистрации в секундах, по умолчанию **60 секунд**;
* **SIPMaxExpiry** - максимальная продолжительность регистрации в секундах, по умолчанию **3600 секунд**.\


В режиме реального времени **Transport Protocol (RTP)** определяет стандартный формат для передачи аудио и видео по IP-сетям. **По умолчанию**, RTP использует диапазон портов между **10000 и 10200**. Для некоторых маршрутизаторов и брандмауэров, возможно, потребуется настроить диапазон портов. Еще одна причина для настройки диапазона портов - большое количество параллельных звонков. Каждый вызов использует два RTP порта. Это означает,что если есть 200 портов, то возможно только 100 параллельных звонков. Если ваша телефонная система должна обрабатывать больше звонков в одно и то же время, необходимо расширить диапазон портов.

* «**Адрес STUN сервера**» - в ряде случаев, к примеру при использовании WebRTC помогает при работе АТС за NAT.
* «**Использовать WebRTC**» - будут произведены дополнительные настройки для работы с WebRTC соедиением. К примеру для внутреннего номера 201 будет создан дополнительный endpoint, подключиться к которому будет возможно по протоколу WebRTC с использованием URL\
  **`sip:201-WS@IP_PBX`**

## Аудио/видео кодеки <a href="#audio_video_kodeki" id="audio_video_kodeki"></a>

Настройка разрешенных кодеков для АТС в целом.

<figure><img src="../../.gitbook/assets/6 (12).png" alt=""><figcaption></figcaption></figure>

## AMI\&AJAM <a href="#ami_ajam" id="ami_ajam"></a>

<figure><img src="../../.gitbook/assets/7 (13).png" alt=""><figcaption></figcaption></figure>

**Asterisk Manger Interface (AMI)** — мощный и удобный программный интерфейс (API) Asterisk для управления системой из внешних программ. Благодаря AMI внешние программы могут осуществлять соединения с Asterisk посредством TCP протокола, инициировать выполнение команд, считывать результат их выполнения, а так же получать уведомления о происходящих событиях в реальном времени. AMI часто используют для интеграции с бизнес-процессами и системами, программным обеспечением CRM (Customer Relationship Managment — управление взаимодействия с клиентами). AMI принимает подключения, устанавливаемые на сетевой порт (по умолчанию - **TCP порт 5038**). Клиентская программа подключается к AMI через этот порт и аутентифицируется, после этого Asterisk будет отвечать на запросы, а также отправлять извещения о изменениях состояния заданных подсистем.\
\
**Asynchronous Javascript Asterisk Manager (AJAM)** - это новая технология, которая позволяет веб-браузерам или другим приложениям с поддержкой HTTP и веб-страницам напрямую обращаться к интерфейсу Asterisk Manager (AMI) через HTTP/HTTPS. По умолчанию используется порт **8088**.

## SSH <a href="#ssh" id="ssh"></a>

<figure><img src="../../.gitbook/assets/8 (3).png" alt=""><figcaption></figcaption></figure>

**SSH** или **Secure Shell** — это зашифрованный протокол, который часто используется для взаимодействия и удаленного управления серверами. SSH сервер может выполнять аутентификацию пользователей с помощью различных алгоритмов. Самый популярный — это **аутентификация по паролю**. Он достаточно прост, но не очень безопасный. Пароли передаются по безопасному каналу, но они недостаточно сложны для противостояния попыткам перебора. Вычислительная мощность современных систем в сочетании со специальными скриптами делают перебор очень простым.

{% hint style="warning" %}
Авторизация через SSH-клиент по умолчанию в MikoPBX:

* Логин - **root**
* Пароль - **admin**, рекомендуем сразу изменить это значение
{% endhint %}

Существует более безопасный и надежный способ аутентификации — **ключи SSHа**. Каждая пара ключей состоит из открытого и закрытого ключа. Секретный ключ сохраняется на стороне клиента и не должен быть доступен кому-либо еще. Утечка ключа позволит злоумышленнику войти на сервер, если не была настроена дополнительная аутентификация по паролю.

{% hint style="danger" %}
Мы настоятельно рекомендуем отключить аутентификацию по паролю. Для этого активируйте опцию «**Отключить авторизацию по паролю**»
{% endhint %}

Открытый ключ используется для шифрования сообщений, которые можно расшифровать только закрытым ключом. Это свойство и используется для аутентификации с помощью пары ключей. Открытый ключ загружается на удаленный сервер, к которому необходимо получить доступ. Его нужно добавить в специальный файл \~/.ssh/authorized\_keys.

Когда клиент попытается выполнить проверку подлинности через этот ключ, сервер отправит сообщение, зашифрованное с помощью открытого ключа, если клиент сможет его расшифровать и вернуть правильный ответ — аутентификация пройдена.

{% hint style="warning" %}
Как создать ключ для авторизации по SSH и добавить его на сервер? Подробности читайте [здесь](https://firstvds.ru/technology/dobavit-ssh-klyuch).
{% endhint %}

**Публичный**(открытый) SSH-ключ можно сохранить на АТС в поле **SSH Authorized Keys**. Если у Вас несколько публичных ключей, то их можно скопировать подряд, разделитель - пустая строка.

## Web-интерфейс <a href="#web-interfejs" id="web-interfejs"></a>

<figure><img src="../../.gitbook/assets/10 (6).png" alt=""><figcaption></figcaption></figure>

В данном подразделе для повышения безопасности Вы можете изменить HTTP-порт (по умолчанию порт 80) или активировать режим HTTPS.\
\
**HTTPS (HyperText Transfer Protocol Secure)** — расширение протокола HTTP для поддержки шифрования в целях повышения безопасности. Данные в протоколе HTTPS передаются поверх криптографических протоколов SSL или TLS. В отличие от HTTP с TCP-портом 80, для HTTPS по умолчанию используется TCP-порт 443.\


* **Редирект на HTTPS** - при попытке открыть web интерфейс по протоколу http пользователь будет переадресован на HTTPS

При начале работы системы АТС сама генерирует сертификат для работы по https - это «самоподписанный» сертификат, то есть не заверенный публичным «регистратором», но тем не менее этот сертификат позволяет работать по https и шифровать трафик между АТС и браузером.

## Пароль web интерфейса <a href="#parol_administratora" id="parol_administratora"></a>

<figure><img src="../../.gitbook/assets/11 (15).png" alt=""><figcaption></figcaption></figure>

В данном подразделе необходимо изменить Логин WEB-интерфейса и Пароль WEB-интерфейса.

{% hint style="info" %}
Авторизация в MikoPBX по умолчанию:

* Логин - admin
* Пароль - admin
{% endhint %}

## Удаление настроек системы <a href="#udalenie_nastroek" id="udalenie_nastroek"></a>

<figure><img src="../../.gitbook/assets/12 (9).png" alt=""><figcaption></figcaption></figure>