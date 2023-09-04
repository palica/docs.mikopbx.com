# Закончилось место на доп. диске, перенос данных на новый диск

## Постановка задачи <a href="#postanovka_zadachi" id="postanovka_zadachi"></a>

MikoPBX установлена на отдельно выделенный сервер по [инструкции](https://wiki.mikopbx.ru/setup#live\_cd). В качестве **дополнительного диска** для хранения записей разговоров (диск **storage**) подключен **4-ый раздел основного диска** (/dev/sda4), где установлена MikoPBX. Свободное место на 4-ом разделе диска закончилось. Необходимо подключить к MikoPBX в качестве диска storage отдельный диск (/dev/sdb) и перенести на него все записи разговоров, которые ранее хранились на 4-ом разделе основного диска.

## Решение <a href="#reshenie" id="reshenie"></a>

1. Подключитесь к MikoPBX через SSH-клиент по [инструкции](../troubleshooting/podklyuchenie-k-ats-s-pomoshyu-ssh-klienta.md)
2. Отключаем **storage** диск «sda4»:

```php
/etc/rc/freestorage;
```