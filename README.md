# docs-as-code
Хранение документации

# Заголовок - Sequence Diagram 

* код
* рисунок диаграммы
  
```mermaid
sequenceDiagram
actor Организатор
participant Система
participant Database
participant SmsApi
actor Администратор
actor Волонтёр

Организатор ->+Система : Нажимает на кнопку\n"Отправить новое объявление\nна проект"
Система ->+Database : Создает запись новго объявления
Database ->+Система : Сформировать данные\nдля рассылки
Система ->+Database : Данные отправки для Сервиса записываются\nв таблицу "sms"
Система ->+API_СМС : Отправить рассылку группе контактов\nhttps://email:api_key@gate.smsaero.ru/v2/sms/send?\nnumbers[]=79990000000&numbers[]=79990000001\n&text=your+text&sign=SMS Aero\n&callbackUrl=https://your.site
```

### Отправка SMS-сообщений sms/send

| Параметр	        | Формат	|    Применение	|   Описание            |
|-------------------|---------|---------------| ----------------------|
|number	            | string  | 	Обязательно |	Номер телефона.       |
|numbers	          | array	  | Обязательно   |	Номера телефонов.     |
|sign	string	      |         | Обязательно   |	Имя отправителя.      |
|text	string        |         |	Обязательно   |	Текст сообщения.      |
