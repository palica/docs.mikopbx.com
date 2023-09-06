# Объединение двух MikoPBX

#### Содержание

### Объединение двух MikoPBX <a href="#obedinenie_dvux_mikopbx" id="obedinenie_dvux_mikopbx"></a>

Компания call-центра имеет два офиса в **Москве** и **Санкт-Петербурге**.\
В каждом офисе используется **MikoPBX**:

* **АТС Москва** - _172.16.32.226_ - все внутренние номера сотрудников назначены по шаблону **2ХХ**
* **АТС Петербург** - _172.16.32.227_ - все внутренние номера сотрудников назначены по шаблону **3ХХ**

Необходимо объединить эти две АТС, реализовать единый внутренний план номеров: абоненты Москвы должны иметь возможность по короткому номеру набрать абонентов Петербурга и наоборот.

Схематично маршрутизация вызовов представлена на рисунке.

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption><p>Схема маршрутизации</p></figcaption></figure>

### Провайдеры телефонии <a href="#provajdery_telefonii" id="provajdery_telefonii"></a>

Для каждой АТС необходимо добавить учетную запись провайдера. Для её создания необходимо перейти в **Маршрутизация** → **Провайдеры телефонии**.

<figure><img src="../../.gitbook/assets/providers.png" alt=""><figcaption><p>Раздел "Провайдеры телефонии"</p></figcaption></figure>

Создайте провайдеров и заполните параметры подключения как на скриншоте ниже:&#x20;

**Идентификатор провайдера появится в адресной строке только после записи провайдера**. Временно в поле «**Логин**» укажите производное значение. После записи провайдера можно его скорректировать.

В «**Расширенные настройки**» - «**Переопределение SIP заголовка «From»**» - установите влаг «Отключить использование поля **fromuser**»

В «**Расширенные настройки**» - «**Дополнительные параметры**» следует прописать:

```
[endpoint]
set_var=IGNORE_TIME=1 
```

Эта опция отключит функционал «**Нерабочее время**» для всех входящих через этого провайдера.&#x20;

**IGNORE\_TIME** - опция будет доступна в 2022.02.103+

### Исходящая маршрутизация <a href="#isxodjaschaja_marshrutizacija" id="isxodjaschaja_marshrutizacija"></a>

Необходимо перейти в **Маршрутизация** → **Исходящие маршруты**. Опишите исходящие маршруты как в скриншоте ниже:&#x20;

### Входящая маршрутизация <a href="#vxodjaschaja_marshrutizacija" id="vxodjaschaja_marshrutizacija"></a>

Добавим **для каждой АТС одинаковое приложение диалплана**, которое будет переадресовывать звонки на внутренние номера . В разделе **Модули - Приложения диалпланов** добавим новое приложение:



**Номер для вызова приложения** укажем произвольный уникальный номер, **Тип кода** выберем **Диалплан Asterisk**. Перейдем на закладку **Программный код** и добавим код обработки звонка:

```
1, GoTo(internal,${FROM_DID},1)
n, Hangup()
```

Создадим входящий маршрут для каждой АТС. Перейдем в раздел **Маршрутизация - Входящие маршруты**, добавим новое правило:



### Переадресация <a href="#pereadresacija" id="pereadresacija"></a>

В целях безопасности, переадресация на «**Внешние**» номера телефонов запрещена!

Чтобы снять ограничение, добавьте через раздел Кастомизация системных файлов в конец файла **extensions.conf** следующий текст:

```
[internal-transfer](+)
exten => _2XX,1,Set(__ISTRANSFER=transfer_)
     same => n,Goto(outgoing,${EXTEN},1) 
```

Это разрешит переадресацию на 2XX номера.

На второй АТС, чтобы разрешить переадресацию на 3XX номера добавьте через раздел Кастомизация системных файлов в конец файла **extensions.conf** следующий текст

```
[internal-transfer](+)
exten => _3XX,1,Set(__ISTRANSFER=transfer_)
     same => n,Goto(outgoing,${EXTEN},1) 
```

### Статусы абонентов <a href="#statusy_abonentov" id="statusy_abonentov"></a>

В некоторых случаях, абонентам одной АТС потребуется знать статусы абонентов другой станции.

К примеру при использовании:

* **BLF** на телефонных аппаратах
* «Панель телефонии для 1С»

Для настройки статусов потребуется:

1.  Добавьте **на первой АТС** через раздел Кастомизация системных файлов в конец файла **extensions.conf** следующий текст:

    ```
    [internal-hints]
    exten => 301,hint,PJSIP/301
    exten => 303,hint,PJSIP/303
    exten => 302,hint,PJSIP/302
    ```
2.  Для **каждой АТС** добавьте через раздел Кастомизация системных файлов в конец файла **pjsip.conf**

    ```
    [<ID-Провайдера-Текщуей-АТС>-devicestate]
    type=outbound-publish
    server_uri=sip:<ID-Провайдера-Текщуей-АТС>@<ID-Провайдера-Другой-АТС>:<SIP-Порт-Другой-АТС>
    event=asterisk-devicestate
     
    [<ID-Провайдера-Текщуей-АТС>]
    type=asterisk-publication
    devicestate_publish=<ID-Провайдера-Текщуей-АТС>-devicestate
    device_state=yes

    [<ID-Провайдера-Текщуей-АТС>]
    type=inbound-publication
    event_asterisk-devicestate=<ID-Провайдера-Текщуей-АТС>
    ```

Замените теги **\<ID-Провайдера-Текщуей-АТС>**, **\<ID-Провайдера-Другой-АТС>**, **\<SIP-Порт-Другой-АТС>** на свои значения

1.  Добавьте **на второй АТС** через раздел Кастомизация системных файлов в конец файла **extensions.conf** следующий текст:

    ```
    [internal-hints]
    exten => 201,hint,PJSIP/201
    exten => 203,hint,PJSIP/203
    exten => 202,hint,PJSIP/202
    ```

### Одинаковые номера на АТС <a href="#odinakovye_nomera_na_ats" id="odinakovye_nomera_na_ats"></a>

В идеале, на каждой АТС должен быть свой диапазон номеров SIP и они не должны пересекаться. Но на практике, возможно и наложение. В этом случае можно столкнуться с проблемой звонка с одной АТС на другую, вызов может обрываться.

Проблему можно обойти, **на каждой АТС** следует добавить через раздел Кастомизация системных файлов в конец файла **extensions.conf** следующую логику:

```
[ID_PROVIDER-outgoing-custom]
; При исходящем в caller ID добавляем префикс "_" (нижнее подчеркивание)
exten => _X!,1,Set(CALLERID(num)=_${CALLERID(num)})
	same => n,return

[ID_PROVIDER-incoming-custom]
; При входящем удаляем префикс, для корректного отображения callerid
exten => _[0-9*#+]!,1,Set(CALLERID(num)=${CALLERID(num)=:1})
	same => n,return
```

**ID\_PROVIDER** - это идентификатор провайдера текущей АТС, подсмотреть можно в адресной строке браузера.

### Итоги <a href="#itogi" id="itogi"></a>

Таким образом мы соединили две АТС! Подтверждением успешного подключения двух станций служит зеленый индикатор напротив учетной записи провайдера.

Для **АТС Москва**(_172.16.32.226_):\
\
Для **АТС Петербург**(_172.16.32.227_):\


Аналогичным образом можно подключить **три** и даже **четыре** станции! Нужно понимать, что в случае соединения трех АТС каждая АТС должна иметь не один, а уже два провайдера. Схематично это изобразить можно так:\


Обратно к перечню инструкций