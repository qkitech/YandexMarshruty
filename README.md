# <a name="up" />Проект Яндекс Маршруты

Яндекс.Маршруты - это онлайн-сервис от компании Яндекс, предоставляющий пользователям возможность быстро и удобно планировать путешествия и маршруты. Сервис предлагает подробную информацию о дорожной ситуации, различные варианты маршрутов для пешеходов, велосипедистов и водителей, а также прокладывает оптимальные маршруты с учетом текущего движения, пробок и других факторов.

## Содержание

- [Задачи тестировщика](#задачи-тестировщика)
- [Требования по проекту](#требования-по-проекту)
- [Инструменты](#инструменты)
- [Процесс работы](#процесс-работы)
  - [1 спринт](#1-спринт)
  - [2 спринт](#2-спринт)

## Задачи тестировщика

<details>
<summary> 1-спринт </summary>

#### Задачи для 1 спринта

1. Проанализировать требования к сервису Яндекс.Маршруты
2. Выделить классы эквивалентности и граничные значения для полей ввода (часы, минуты, откуда и куда)
3. Создать набор тест-кейсов на проверку валидации полей формы Яндекс Маршрутов
4. Протестировать валидацию полей и завести баг-репорты

---

</details>

<details>
<summary> 2-спринт </summary>

#### Задачи для 2 спринта

1. Проанализировать требования к функциональности "Каршеринг" и "Аэротакси"
2. Подготовить тестовую документацию, чтобы проверить вёрстку формы бронирования
3. Подготовить тестовую документацию, чтобы проверить логику окон "Способ оплаты", "Добавление карты" и кнопки "Забронировать"
4. Протестировать новый вид транспорта "Аэротакси" по готовому чек-листу. Добавь аэротакси в интерфейс с помощью инструмента "Charles"
5. Протестировать приложение и завести баг-репорты

---

</details>

## Требования по проекту

<details>
<summary>Требования к сервису Яндекс Маршруты </summary>

### Общее описание

Яндекс.Маршруты — сервис, который строит маршруты для транспорта разных видов. Рассчитывает время и стоимость поездки.  
В этом сервисе доступны несколько режимов: «Оптимальный», «Быстрый», «Свой».  
В режиме «Свой» панель видов транспорта активна, можно выбрать тип транспорта. Система построит маршрут.  
Если выбрать режим «Оптимальный» или «Быстрый», система автоматически определит вид транспорта и построит маршрут. Панель видов транспорта станет неактивна.

### Макеты

![Макет1](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/997cac9c-8cd3-411a-bc75-8c2b4e434f73)
![Макет2](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/2ecdd524-c9ed-42d6-ad72-cda16f8f3c45)
![iScreen Shoter - Safari - 231020150252](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/7c922c18-2bf7-432c-9ae6-7aaa34ebd089)

### Интерфейс

В интерфейсе есть поля «Время начала поездки», «Откуда», «Куда». Переключатели режимов маршрута: «Оптимальный», «Быстрый» и «Свой», а также переключатели видов транспорта: свой автомобиль, каршеринг, такси, самокат, велосипед и пешком.  
Пользователь вводит время отправления. Чтобы построить маршрут, нужно ввести улицу и номер дома в поля «Откуда» и «Куда». В начале и конце адреса могут быть пробелы: они допустимы, но при снятии фокуса система удалит их.

#### Описание работы интерфейса

В стартовом состоянии поля «Время начала поездки», «Откуда» и «Куда» пустые. Режимы маршрутов «Оптимальный», «Быстрый и «Свой» не выбраны; панель переключения видов транспорта неактивна.

#### Логика работы полей «Откуда» и «Куда»

Если поля адреса заполнены корректно, на карте отображаются точки А и В. Если поле «Откуда» заполнено некорректно, точка А не отображается. Если поле «Куда» заполнено некорректно, точка В не отображается. При некорректном значении поле подсвечивается красным; появляется сообщение об ошибке.  
Примеры тестовых адресов есть в таблице.

#### Режим «Оптимальный» и «Быстрый»

Если выбрать режим «Оптимальный» или «Быстрый», система автоматически назначит вид транспорта; построится маршрут; отобразится время и стоимость поездки. Выбрать транспорт в этих режимах нельзя — панель видов транспорта неактивна.

#### Режим «Свой»

Если выбрать режим «Свой», панель видов транспорта активна — можно переключать. Под каждый вид транспорта строится маршрут; рассчитывается время и стоимость поездки.  
Если сменить вид транспорта или поменять значение в любом поле, маршрут перестроится; время и стоимость поездки пересчитается.

#### Ограничения

![iScreen Shoter - Safari - 231020150335](https://github.com/SofiiaSleptsova/Yandex_Marshruty/assets/147629405/a179dc40-b00d-4509-a965-2089272bd58f)

---

</details>

<details>
<summary>Требования к функциональности «Каршеринг»</summary>

![image](https://github.com/qkitech/YandexMarshruty/assets/157276532/e2f2ea21-9fc5-4bac-988d-367d2a7672c2)

---

</details>

<details>
<summary>Требования к фиче: аэротакси</summary>
  
![image](https://github.com/qkitech/YandexMarshruty/assets/157276532/fb91b9cf-d6d8-4e4c-bf41-4a09e1e7b7eb)

---

</details>

## Инструменты

<p align="left"> 
  <a href="https://docs.google.com/" target="_blank" rel="noreferrer"><img src="https://w7.pngwing.com/pngs/240/1015/png-transparent-g-suite-google-docs-google-angle-rectangle-logo.png" width="36" height="36" alt="Google Sheets" /></a>
  <a href="https://app.diagrams.net" target="_blank" rel="noreferrer"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Diagrams.net_Logo.svg/2048px-Diagrams.net_Logo.svg.png" width="36" height="36" alt="draw.io" /></a>
  <a href="https://www.figma.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/figma-colored.svg" width="36" height="36" alt="Figma" /></a>
  <a><img src="https://d33wubrfki0l68.cloudfront.net/38b5c953a4667366685d55db55d057c86db1fc54/a0fdc/static/acae6b24d940347661ca901ea07f47c1/chrome-dev-logo-icon.png" width="36" height="36" alt="Devtools" /></a>
  <a href="https://www.jetbrains.com/youtrack/" target="_blank" rel="noreferrer"><img src="https://upload.wikimedia.org/wikipedia/commons/9/95/YouTrack_Icon.png" width="36" height="36" alt="Youtrack" /></a>
  <a href="https://www.charlesproxy.com/" target="_blank" rel="noreferrer"><img src="https://davidwalsh.name/demo/charlesproxyicon.svg" width="36" height="36" alt="Charles" /></a>
</p>

## Процесс работы

### 1 спринт

#### Задача 1 (планирование тестирования)

**Техники-тест дизайна**  
На данном этапе были использованы техники тест дизайна: классы эквивалентности и граничные значения для полей ввода (откуда, куда, часы и минуты)

[Выделить классы эквивалентности и граничные значения](https://docs.google.com/spreadsheets/d/1a7xCH-hiDg5gof1DFXGyqF38v6SESWFj-uxrdOIuhQE/edit#gid=1304990855)

#### Задача 2 (проектирование тестовой документации)

[Создать набор тест-кейсов на проверку валидации полей формы Яндекс Маршрутов](https://docs.google.com/spreadsheets/d/1a7xCH-hiDg5gof1DFXGyqF38v6SESWFj-uxrdOIuhQE/edit#gid=1524919368)

### 2 спринт

#### Задача 1 Проанализировать требования к функциональности "Каршеринг" и "Аэротакси"

#### Задача 2 (проектирование тестовой документации)

[Чек лист верстки](https://docs.google.com/spreadsheets/d/1eHAuLfuoe1CdHAw81Dk8FOAvniHXrqaqUDuRDCwSj5I/edit#gid=528790199)

#### Задача 3 (проектирование тестовой документации)

[Чек-лист «Способ оплаты» и «Добавление карты»](https://docs.google.com/spreadsheets/d/1eHAuLfuoe1CdHAw81Dk8FOAvniHXrqaqUDuRDCwSj5I/edit#gid=1540435533)

[Тест-кейсы на кнопку «Забронировать»](https://docs.google.com/spreadsheets/d/1eHAuLfuoe1CdHAw81Dk8FOAvniHXrqaqUDuRDCwSj5I/edit#gid=1567345705)

#### Задача 4 

[Чек-лист на аэротакси](https://docs.google.com/spreadsheets/d/1S4wbEp-A4GOz2zPZErLpfbiijYtsmvR8DTCOM3-fVY0/edit?usp=sharing)

[Использовать программу Charles для тестирования приложения в момент,когда бэкэнд еще не готов(скрины)]([https://docs.google.com/spreadsheets/d/1S4wbEp-A4GOz2zPZErLpfbiijYtsmvR8DTCOM3-fVY0/edit?usp=sharing](https://drive.google.com/drive/u/0/folders/10x1a3NHcmvAMzLSbbJu0RODYpdPKEKrK))

<details>
 <summary> Баг-репорты </summary>
	
#### Баг-репорты

[1-Спринт](https://docs.google.com/spreadsheets/d/1a7xCH-hiDg5gof1DFXGyqF38v6SESWFj-uxrdOIuhQE/edit#gid=454479584)

[2-Спринт](https://kiropurr.youtrack.cloud/issues?q=tag:%20%7BPractice%7D)

---

</details>

<details>
 <summary>  Выводы </summary>
	
Платформа “Яндекс.Маршруты” предлагает разные функции. Такие как расчет поездки, выбор разных типов поездок. Были проведены тесты на основные функции: вертску формы “Выбора тарифа”, логику работы окон «Способ оплаты», «Добавление карты» и  «Забронировать» 
Мне удалось протестировать верстку приложения и логику работы формы
бронирования заказа.Использовать программу Charles для тестирования приложения в момент,когда бэкэнд еще не готов
Найдены критические баги, например удаления адреса ломает верстку,пропадает форма бронирования заказа,сам заказ нельзя отменить,при этом автомобиль может быть уже забронирован и за него могут списываться денежные
средства.Также некорректно работает навигационная карта,которая может вводить в заблуждение клиентов.
Вывод о готовности к выпуску: В настоящее время сервис Яндекс.Маршруты обладает хорошей функциональностью, но для обеспечения оптимального опыта пользователя необходимо провести дополнительное тестирование и внести исправления выявленных проблем перед окончательным выпуском.


---

</details>
