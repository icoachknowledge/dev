---
title: Вёрстка лендинга
category: Общее
order: 
---

## Приёмка

### Загрузка

* Ссылка на готовый лендинг есть
* Ссылка открывается
* Видео воспроизводится
* Фото качественные
* Размер каждого из изображений не превышает 150кб
* Отсутствуют не загружающиеся скрипты
* Скорость загрузки лендинга не более 5 секунд
* Ссылки в подвале работают

### Текст лендинга соответствует ТЗ

* Дескриптор
* Правая часть шапки
* Первый экран
* Текст кнопки
* Текст фона
* Остальные экраны
* Контактные данные в подвале
* Для схемы запуска с мастер-классом — адрес мастер-класса на странице «Спасибо»

### Отзывы

* В каждом отзыве есть фото
* В каждом отзыве есть заголовок
* В каждом отзыве есть имя автора
* В каждом отзыве есть ссылка на профиль его автора
* Текст ссылки и адрес ссылки каждого отзыва ведёт на страницу автора отзыва

### Типографика

### Адаптивность

* Максимальная ширина контейнера на экране с разрешением 1280px и выше — 1020pх
* Корректно отображается на мобильном
* Отсутствует горизонтальная прокрутка на мобильном

### Кнопки и Формы

* Кнопки с призывом к действию крупные и контрастные, с крупными полями
* Все кнопки работают
* В форме присутствуют указанные в ТЗ поля
* Если собираем емейлы — подключены формы activecampaign, если нет — обычные

### Скрипты

* Метрика подключена
* Facebook Pixel работает (Facebook Pixel Helper)

### Оставил заявку

* При заполнении заявки она попадает в Trello и телеграм
* Заявка в Trello содержит все поля формы
* В поле offer — имя автора и первый шаг, например «Иван Иванович — вебинар по переговорам»
* Домен в CNAME правильный
* Домен в README правильный
* Домен в deploy правильный
* Есть social photo

### Если формы activecampaign

* Отобразилась страница /ok с просьбой подтвердить подписку
* Обращение ты/вы на странице «Подтвердите подписку» соответствует принятому в тексте лендинга
* На емейл пришло письмо с просьбой подтвердить подписку
* Обращение ты/вы на в письме соответствует принятому в тексте лендинга
* Отправитель емейла — Имя Автора
* Адрес отправителя — имяавторалатиницей@[icoach.io](http://icoach.io)
* В тексте письма правильно указано имя автора
* В тексте письма правильно указана причина подписки и призыв к действию
* После нажатия на кнопку «Подтвердить» открывается страница «Спасибо» /confirmed

### Страница «Спасибо»

* Содержит подтверждение регистрации
* Предлагает подписаться на группу в соцсети
* Понятно, что будет дальше, когда, и кто это делает — «я вам позвоню в течение минуты», «приходите по адресу Красная 15 в 15:15»
* Обращение ты/вы на странице «Спасибо» соответствует принятому в тексте лендинга

## Текст лендинга

Текст лендинга должен соответствовать ТЗ

## Кнопки

Кнопки с призывом к действию крупные и контрастные, с крупными полями.

Размер шрифта кнопки не меньше, чем основной текст (лучше больше).

Поля 1em по вертикали и 2em по горизонтали

![](/images/general/landing/button.png)

## Подключение форм

Если в форме требуется упомянуть скайп, а не телефон, должно быть: <input id="input-phone" required="required" name="skype" type="text" class="form-control" placeholder="">

Если используется форма activecampaign, то должны быть файлы ok.html (пожалуйста подтвердите подписку) и confirmed.html (спасибо)

Если используется вариант с FB messenger, то необходимо получить ссылку на мессенджер. Ссылка должна быть подобного вида - [https://m.me/788686404656375?ref=](https://m.me/788686404656375?ref=)

## Страница "ok.html"

В зависимости от информации, указанной в ТЗ, формируется страница "ok.html". В случае, если используется вариант с FB messenger, страница "ok.html" должна содержать только кнопку перехода в чат

## Страница "Pay"

Страница, которая содержит в себе данные для оплаты курса. Обычно, мы размещаем виджет для Яндекс.Кошелька, предварительно получив номер от автора

## Страница "Paid"

Открывается после того, как лид внес оплату.

paid – это «спасибо за покупку», указывается тут: {% include yandex-pay.html name="Как создать мощное предложение" amount="67" redirect="http://icoach.io/tw-paid/" %} в поле redirect

## Facebook Pixel

В "config" в графе pixel_id должен стоять идентификатор пикселя: facebook_pixel_id: 1733822553334542

"Ok" должен содержать строку facebook_event: Lead

После этого, работоспособность пикселя нужно поверить. Сделать это можно в GoogleChrome с помощью расширения Facebook Pixel Helper

![](/images/general/landing/pixel.jpg)

Цифра 3 и строка Lead появятся только на странице "Ок". На главной странице лендинга строки Lead не будет, если открыть Helper

Страница "Pay" должна содержать facebook_event: InitiateCheckout

Страница "Рaid" должна содержать facebook_event: Purchase

## Deploy

Сервер должен быть: 

![](/images/general/landing/server.jpg)

## Сохранение исходных текстов на сервер git

Папку с проектом заливаем на битбакет

## Развёртывание готового лендинга на вебсервере

Папку _site заливаешь на наш вебсервер по SFTP (можно использовать любой FTP клиент, или из командной строки засылать командой)

Логинишься, в домашней папке есть www, туда кладёшь site внутрь, только переименовываешь в имя автора, то есть будет www/aleksandrzakharov, а внутри — содержимое папки _site

Проверяешь, что открывается сайт клиента