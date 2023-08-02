# Table of contents

* [Руководство по MikoPBX](README.md)
  * [Быстрый старт](master/quick-start.md)
  * [Знакомство с MikoPBX](master/znakomstvo-s-mikopbx.md)
  * [Системные требования](master/sistemnye-trebovaniya.md)

## Установка <a href="#setup" id="setup"></a>

* [Отдельный компьютер](setup/bare-metal.md)
* [Виртуальная машина](setup/hypervisor/README.md)
  * [VMware ESXi](setup/hypervisor/vmware-esxi.md)
  * [VMware Fusion](setup/hypervisor/vmware-fusion.md)
  * [VirtualBOX](setup/hypervisor/virtualbox.md)
  * [VMware Workstation Pro](setup/hypervisor/vmware-workstation-pro.md)
  * [Hyper-V](setup/hypervisor/hyper-v.md)
* [Облако](setup/cloud/README.md)
  * [Hetzner cloud](setup/cloud/hetzner-cloud.md)
  * [Google Cloud](setup/cloud/google-cloud.md)
  * [Microsoft Azure](setup/cloud/microsoft-azure.md)
  * [VK Cloud Solutions](setup/cloud/vk-cloud-solutions.md)
  * [Yandex Cloud](setup/cloud/yandex-cloud.md)
* [Докер контейнер](setup/docker.md)

## Руководство пользователя <a href="#manual" id="manual"></a>

* [Телефония](manual/telefoniya/README.md)
  * [Сотрудники](manual/telefoniya/extensions.md)
  * [Очереди вызовов](manual/telefoniya/call-queues.md)
  * [IVR меню](manual/telefoniya/ivr-menu.md)
  * [Конференции](manual/telefoniya/conference-rooms.md)
  * [Звуковые файлы](manual/telefoniya/sound-files.md)
  * [История вызовов](manual/telefoniya/call-detail-records.md)
* [Маршрутизация](manual/routing/README.md)
  * [Провайдеры телефонии](manual/routing/providers.md)
  * [Входящие маршруты](manual/routing/incoming-routes.md)
  * [Нерабочее время](manual/routing/out-off-work-time.md)
  * [Исходящие маршруты](manual/routing/outbound-routes.md)
* [Модули](manual/modules/README.md)
  * [Управление модулями](manual/modules/upravlenie-modulyami/README.md)
    * [Регистрация в marketplace](manual/modules/upravlenie-modulyami/licensing.md)
  * [Приложения диалпланов](manual/modules/dialplan-applications.md)
* [Обслуживание](manual/maintenance/README.md)
  * [Обновление системы](manual/maintenance/update.md)
  * [Диагностика системы](manual/maintenance/system-diagnostic.md)
  * [Перезагрузка и выключение системы](manual/maintenance/restart.md)
  * [Модуль резервного копирования](manual/maintenance/modul-rezervnogo-kopirovaniya.md)
* [Сеть и Firewall](manual/connectivity/README.md)
  * [Сетевые интерфейсы](manual/connectivity/network.md)
  * [Сетевой экран](manual/connectivity/firewall.md)
  * [Защита от взлома](manual/connectivity/fail2-ban.md)
* [Система](manual/system/README.md)
  * [Системные настройки](manual/system/general-settings.md)
  * [Дата и время](manual/system/time-settings.md)
  * [Почта и уведомления](manual/system/mail-settings/README.md)
    * [Настройка E-mail уведомлений для почтового сервиса Gmail](manual/system/mail-settings/nastroika-e-mail-uvedomlenii-dlya-pochtovogo-servisa-gmail.md)
    * [Настройка E-mail уведомлений для почтового сервиса Yandex](manual/system/mail-settings/nastroika-e-mail-uvedomlenii-dlya-pochtovogo-servisa-yandex.md)
    * [Настройка E-mail уведомлений для почтового сервиса Mail](manual/system/mail-settings/nastroika-e-mail-uvedomlenii-dlya-pochtovogo-servisa-mail.md)
  * [Доступ к AMI](manual/system/asterisk-managers.md)
  * [Кастомизация системных файлов](manual/system/custom-files.md)

## Часто задаваемые вопросы <a href="#faq" id="faq"></a>

* [Интеграция с 1С](faq/integraciya-s-1s/README.md)
  * [Перехват на ответственного](faq/integraciya-s-1s/interception/README.md)
    * [Перехват на ответственного в панели телефонии 4.0 как в панели 1.0](faq/integraciya-s-1s/interception/perekhvat-na-otvetstvennogo-v-paneli-telefonii-4.0-kak-v-paneli-1.0.md)
    * [Отменить перехват на ответственного для конкретного провайдера](faq/integraciya-s-1s/interception/otmenit-perekhvat-na-otvetstvennogo-dlya-konkretnogo-provaidera.md)
* [Исходящая маршрутизация](faq/iskhodyashaya-marshrutizaciya/README.md)
  * [Добавить P-Preferred-Identity и Remote-Party-ID заголовок](faq/iskhodyashaya-marshrutizaciya/dobavit-p-preferred-identity-i-remote-party-id-zagolovok.md)
  * [Конференция с постоянным внешним абонентом](faq/iskhodyashaya-marshrutizaciya/konferenciya-s-postoyannym-vneshnim-abonentom.md)
  * [Исходящий с набором внутреннего номера](faq/iskhodyashaya-marshrutizaciya/iskhodyashii-s-naborom-vnutrennego-nomera.md)
  * [Убрать все спецсимволы из набираемого номера](faq/iskhodyashaya-marshrutizaciya/ubrat-vse-specsimvoly-iz-nabiraemogo-nomera.md)
  * [Запрет звонка через резервный маршрут](faq/iskhodyashaya-marshrutizaciya/zapret-zvonka-cherez-rezervnyi-marshrut.md)
  * [Звонки на экстренные номера](faq/iskhodyashaya-marshrutizaciya/zvonki-na-ekstrennye-nomera.md)
  * [Звонок через определенного провайдера](faq/iskhodyashaya-marshrutizaciya/zvonok-cherez-opredelennogo-provaidera.md)
  * [Шаблоны номеров](faq/iskhodyashaya-marshrutizaciya/shablony-nomerov/README.md)
    * [Равномерное распределение исходящих](faq/iskhodyashaya-marshrutizaciya/shablony-nomerov/ravnomernoe-raspredelenie-iskhodyashikh.md)
    * [Удаление кода города из номера](faq/iskhodyashaya-marshrutizaciya/shablony-nomerov/udalenie-koda-goroda-iz-nomera.md)
    * [Добавление префикса "8" к номеру](faq/iskhodyashaya-marshrutizaciya/shablony-nomerov/dobavlenie-prefiksa-8-k-nomeru.md)
    * [Замена префикса номера с "8, 7" на "+7"](faq/iskhodyashaya-marshrutizaciya/shablony-nomerov/zamena-prefiksa-nomera-s-8-7-na-+7.md)
    * [Замена префикса номера с "+7" на "8"](faq/iskhodyashaya-marshrutizaciya/shablony-nomerov/zamena-prefiksa-nomera-s-+7-na-8.md)
    * [Пример шаблона: звонки в другую страну (Укарина, Беларусь, Латвия)](faq/iskhodyashaya-marshrutizaciya/shablony-nomerov/primer-shablona-zvonki-v-druguyu-stranu-ukarina-belarus-latviya.md)
    * [Как запретить замену "+" на "00"](faq/iskhodyashaya-marshrutizaciya/shablony-nomerov/kak-zapretit-zamenu-+-na-00.md)
  * [Настройка исходящего АОН для сотрудника](faq/iskhodyashaya-marshrutizaciya/nastroika-iskhodyashego-aon-dlya-sotrudnika.md)
* [Входящая маршрутизация](faq/vkhodyashaya-marshrutizaciya/README.md)
  * [Выбор провайдера при переадресации на мобильный](faq/vkhodyashaya-marshrutizaciya/vybor-provaidera-pri-pereadresacii-na-mobilnyi.md)
  * [Уведомление о занятости, Call Waiting](faq/vkhodyashaya-marshrutizaciya/uvedomlenie-o-zanyatosti-call-waiting.md)
  * [Маршрутизация по DID номеру](faq/vkhodyashaya-marshrutizaciya/marshrutizaciya-po-did-nomeru.md)
  * [Черные и белые списки](faq/vkhodyashaya-marshrutizaciya/chernye-i-belye-spiski.md)
  * [Разрешить донабор внутреннего номера в очереди](faq/vkhodyashaya-marshrutizaciya/razreshit-donabor-vnutrennego-nomera-v-ocheredi.md)
  * [Нормализация входящего номера телефона](faq/vkhodyashaya-marshrutizaciya/normalizaciya-vkhodyashego-nomera-telefona.md)
  * [Настройка индивидуального нерабочего времени для учетной записи провайдера](faq/vkhodyashaya-marshrutizaciya/nastroika-individualnogo-nerabochego-vremeni-dlya-uchetnoi-zapisi-provaidera.md)
  * [Вывод информации о did-номере](faq/vkhodyashaya-marshrutizaciya/vyvod-informacii-o-did-nomere.md)
  * [Настройка "черного" списка](faq/vkhodyashaya-marshrutizaciya/nastroika-chernogo-spiska.md)
  * [Пример реализации типового маршрута входящих вызовов](faq/vkhodyashaya-marshrutizaciya/primer-realizacii-tipovogo-marshruta-vkhodyashikh-vyzovov.md)
  * [Базовый пример IVR](faq/vkhodyashaya-marshrutizaciya/bazovyi-primer-ivr.md)
* [Установка](faq/setup/README.md)
  * [Конвертация истории звонков FreePBX в MikoPBX](faq/setup/konvertaciya-istorii-zvonkov-freepbx-v-mikopbx.md)
  * [Переход со старых релизов на MikoPBX](faq/setup/perekhod-so-starykh-relizov-na-mikopbx/README.md)
    * [Перенос записей разговоров из Askozia 5 в MikoPBX](faq/setup/perekhod-so-starykh-relizov-na-mikopbx/perenos-zapisei-razgovorov-iz-askozia-5-v-mikopbx.md)
    * [Обновление Askozia 4, 5 до версии MikoPBX](faq/setup/perekhod-so-starykh-relizov-na-mikopbx/obnovlenie-askozia-4-5-do-versii-mikopbx.md)
    * [Конвертация истории звонков Askozia 5 в MikoPBX](faq/setup/perekhod-so-starykh-relizov-na-mikopbx/konvertaciya-istorii-zvonkov-askozia-5-v-mikopbx.md)
  * [Установка на MDADM RAID1](faq/setup/ustanovka-na-mdadm-raid1.md)
  * [Тонкая настройка firewall](faq/setup/tonkaya-nastroika-firewall.md)
  * [Перенос MikoPBX на другой сервер](faq/setup/change-host.md)
  * [Сброс к заводским настройкам](faq/setup/factory-reset.md)
  * [Настройка Zabbix агента (v.5)](faq/setup/nastroika-zabbix-agenta-v.5.md)
  * [Мониторинг провайдеров на MikoPBX](faq/setup/monitoring-provaiderov-na-mikopbx.md)
* [Обслуживание](faq/management/README.md)
  * [Изменить имя для авторизации](faq/management/izmenit-imya-dlya-avtorizacii.md)
  * [Закончилось место на доп. диске, увеличение размера диска](faq/management/extension-of-storage-disk.md)
  * [Порядок обновления до актуальной версии](faq/management/poryadok-obnovleniya-do-aktualnoi-versii.md)
  * [Закончилось место на доп. диске, перенос данных на новый диск](faq/management/move-data-from-storage-to-another-disk.md)
  * [Хранение записей в общей папке windows](faq/management/khranenie-zapisei-v-obshei-papke-windows.md)
* [Соединение нескольких АТС](faq/interconnections/README.md)
  * [Объединение двух MikoPBX](faq/interconnections/mikopbx-2-mikopbx.md)
  * [Объединение MIKOPBX и Grandstream UCM6202](faq/interconnections/mikopbx-and-grandstream-ucm6202.md)
  * [Объединение MIKOPBX и FreePBX (PJSIP)](faq/interconnections/mikopbx-and-freepbx-pjsip.md)
  * [Объединение MIKOPBX и FreePBX (IAX2)](faq/interconnections/mikopbx-and-freepbx-iax2.md)
* [Даигностика проблем](faq/troubleshooting/README.md)
  * [Настройка громкости](faq/troubleshooting/nastroika-gromkosti.md)
  * [Подключение к АТС с помощью SSH-клиента](faq/troubleshooting/podklyuchenie-k-ats-s-pomoshyu-ssh-klienta.md)
  * [Подключение к АТС с помощью WinSCP](faq/troubleshooting/podklyuchenie-k-ats-s-pomoshyu-winscp.md)
  * [Получение логов с помощью приложения tcpdump](faq/troubleshooting/poluchenie-logov-s-pomoshyu-prilozheniya-tcpdump.md)
  * [Снятие лога в АТС с помощью Wireshark](faq/troubleshooting/snyatie-loga-v-ats-s-pomoshyu-wireshark.md)
  * [Анализ трафика средствами Sngrep](faq/troubleshooting/analiz-trafika-sredstvami-sngrep.md)
  * [Настройка Jitter](faq/troubleshooting/nastroika-jitter.md)
  * [Диагностика проблем с лицензированием](faq/troubleshooting/diagnostika-problem-s-licenzirovaniem.md)
* [Сценарии и кейсы](faq/cases/README.md)
  * [Уведомление в телеграмм о пропущенных](faq/cases/uvedomlenie-v-telegramm-o-propushennykh.md)
  * [Позвонить в компанию с мобильного и набрав добавочный позвонить сторонней компании](faq/cases/pozvonit-v-kompaniyu-s-mobilnogo-i-nabrav-dobavochnyi-pozvonit-storonnei-kompanii.md)
  * [Отправка входящего факса на email](faq/cases/otpravka-vkhodyashego-faksa-na-email.md)
  * [Оценка клиентом качества обслуживания](faq/cases/ocenka-klientom-kachestva-obsluzhivaniya.md)
  * [Имитация внешних звонков](faq/cases/imitaciya-vneshnikh-zvonkov.md)
  * [Настройка outboudproxy](faq/cases/nastroika-outboudproxy.md)
  * [Отключение "нерабочего времени" для VIP номеров](faq/cases/otklyuchenie-nerabochego-vremeni-dlya-vip-nomerov.md)
  * [Регистрация нескольких учетных записей от одного провайдера](faq/cases/registraciya-neskolkikh-uchetnykh-zapisei-ot-odnogo-provaidera.md)
  * [Настройка индивидуального нерабочего времени для нескольких провайдеров, зарегистрированных на одном](faq/cases/nastroika-individualnogo-nerabochego-vremeni-dlya-neskolkikh-provaiderov-zaregistrirovannykh-na-odno.md)
  * [Отключить переадресацию на мобильный для внутренних звонков](faq/cases/otklyuchit-pereadresaciyu-na-mobilnyi-dlya-vnutrennikh-zvonkov.md)
  * [Уникальная фоновая музыка для очереди](faq/cases/unikalnaya-fonovaya-muzyka-dlya-ocheredi.md)
  * [Пауза для агента очереди](faq/cases/pauza-dlya-agenta-ocheredi.md)
  * [Динамические агенты очередей](faq/cases/dinamicheskie-agenty-ocheredei.md)
  * [Настройка функции "Paging"](faq/cases/nastroika-funkcii-paging.md)
  * [Ограничить количество авторизаций на одном SIP аккаунте](faq/cases/ogranichit-kolichestvo-avtorizacii-na-odnom-sip-akkaunte.md)
  * [Как реализовать функцию суфлера](faq/cases/kak-realizovat-funkciyu-suflera.md)
  * [Голосовая почта](faq/cases/golosovaya-pochta.md)
* [Настройка провайдеров](faq/providers/README.md)
  * [Ростелеком](faq/providers/rostelekom.md)
  * [MTT](faq/providers/mtt.md)
  * [Zadarma (Novofon)](faq/providers/zadarma-novofon.md)
  * [Мегафон](faq/providers/megafon.md)
  * [Билайн](faq/providers/beeline.md)
  * [МТС](faq/providers/mts.md)
  * [UIS (uiscom.ru)](faq/providers/uis.md)
  * [MANGO OFFICE](faq/providers/mango-office.md)
  * [dom.ru](faq/providers/dom.ru.md)
  * [Яндекс телефония](faq/providers/yandex.md)
  * [NEW-TEL](faq/providers/new-tel.md)
  * [sip.tg](faq/providers/sip.tg.md)
  * [Lifecell](faq/providers/lifecell.md)
  * [SIP Коннектор Bitrix24](faq/providers/sip-connector-bitrix24.md)
  * [ID Phone(Казахтелеком)](faq/providers/id-phone-kazakhtelekom.md)
  * [Имитация внешних входящих и исходящих звонков](faq/providers/imitaciya-vneshnikh-vkhodyashikh-i-iskhodyashikh-zvonkov.md)
* [Настройка софтфонов](faq/softphones/README.md)
  * [Sessiontalk](faq/softphones/sessiontalk.md)
  * [Groundwire](faq/softphones/groundwire.md)
  * [MicroSIP](faq/softphones/microsip.md)
  * [Zoiper](faq/softphones/zoiper.md)
  * [Jitsi](faq/softphones/jitsi.md)
  * [PhonerLite](faq/softphones/phonerlite.md)
  * [Linphone (MacOS)](faq/softphones/linphone-macos.md)
  * [Telephone(MacOS)](faq/softphones/telephone-macos.md)
* [Voip шлюзы](faq/voip-gateways/README.md)
  * [GoIP4](faq/voip-gateways/goip4.md)
  * [Yeastar NeoGate TG 400](faq/voip-gateways/yeastar-neogate-tg-400.md)
  * [Grandstream HT503](faq/voip-gateways/grandstream-ht503.md)
  * [Звонки через 3G модем Huawei E173 (chan\_dongle)](faq/voip-gateways/zvonki-cherez-3g-modem-huawei-e173-chan\_dongle.md)
* [IP-Телефоны](faq/ip-telefones/README.md)
  * [Snom D120](faq/ip-telefones/snom-d120.md)
  * [Yealink T19](faq/ip-telefones/yealink-t19.md)
  * [Yealink T21](faq/ip-telefones/yealink-t21.md)
  * [Yealink T28](faq/ip-telefones/yealink-t28.md)
  * [Fanvil X3SP](faq/ip-telefones/fanvil-x3sp.md)

## Модули <a href="#modules" id="modules"></a>

* [Модули МИКО](modules/miko/README.md)
  * [Интеграция с 1С](modules/miko/integraciya-s-1s/README.md)
    * [Панель телефонии 1.0 для 1С](modules/miko/integraciya-s-1s/module-pt1c-core.md)
    * [Панель телефонии 4.0 для 1С](https://docs.telefon1c.ru)
    * [Модуль умной маршрутизации](https://docs.telefon1c.ru/user-guides/routing/smart-ivr-miko/)
  * [Группы пользователей](modules/miko/module-users-groups.md)
  * [Интеграция с CRM Bitrix24](modules/miko/module-bitrix24-integration.md)
  * [Резервное копирование](modules/miko/module-backup.md)
  * [Провижининг телефонов](modules/miko/module-autoprovision.md)
  * [Автообработка пропущенных](modules/miko/module-callback-queues.md)
  * [Let's Encrypt](modules/miko/module-get-ssl-lets-encrypt.md)
  * [Управление доступом в систему](modules/miko/module-users-u-i.md)
  * [Модуль автообзвона](modules/miko/module-auto-dialer.md)

## Прочее

* [Версии и пакеты Linux](prochee/versii-i-pakety-linux.md)