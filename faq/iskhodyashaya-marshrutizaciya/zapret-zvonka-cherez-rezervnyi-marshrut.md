# Запрет звонка через резервный маршрут

При описании [исходящих маршрутов](../../manual/routing/outbound-routes.md) допускается использовать одинаковый шаблон номера телефона.

В случае, если с одним шаблоном используется несколько маршрутов, то АТС будет пытаться совершить вызов по каждому из маршрутов, пока вызов не будет принят.

Не всегда этот функционал необходим и может возникнуть потребность его отключить.

На текущий момент это возможно сделать только через кастомизацию АТС.&#x20;

1. Перейдите в настройки провайдера и скопируйте его ID в адресной строке браузера:

<figure><img src="../../.gitbook/assets/1 (2).png" alt=""><figcaption></figcaption></figure>

2. Переходим в раздел «[Кастомизация системных файлов](../../manual/system/custom-files.md)»

<figure><img src="../../.gitbook/assets/2 (2).png" alt=""><figcaption></figcaption></figure>

3. Переходим в раздел редактирования файла **extensions.conf**.&#x20;

<figure><img src="../../.gitbook/assets/3 (1).png" alt=""><figcaption></figcaption></figure>

4. Добавьте в конец файла следующий контекст:

```php
[SIP-1688041950-outgoing-after-dial-custom]
exten => _X!,1,Hangup()
	same => n,return
```

<figure><img src="../../.gitbook/assets/4 (1).png" alt=""><figcaption></figcaption></figure>

Сохраните изменения. Теперь все звонки через маршруты, связанные с провайдером будут происходить без учета резервного провайдера. Будет отрабатывать только первый из исходящих маршрутов.