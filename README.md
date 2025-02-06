# docs-as-code
Хранение документации

# Заголовок - Sequence Diagram 

* код
* рисунок диаграммы
  
sequenceDiagram
actor Организатор as Foo
participant Система as Foo1
database    Database    as Foo2
participant API_СМС as Foo3
actor Администратор as Foo5
actor Волонтёр as Foo4

activate Foo
Foo -> Foo1 : Нажимает на кнопку\n"Отправить новое объявление\nна проект"
deactivate Foo
activate Foo1
Foo1 -> Foo2 : Создает запись новго объявления
activate Foo2
Foo2 -> Foo1 : Сформировать данные\nдля рассылки
Foo1 -> Foo2 : Данные отправки для Сервиса записываются\nв таблицу "sms"
activate Foo3
Foo1 -> Foo3 : Отправить рассылку группе контактов\nhttps://email:api_key@gate.smsaero.ru/v2/sms/send?\nnumbers[]=79990000000&numbers[]=79990000001\n&text=your+text&sign=SMS Aero\n&callbackUrl=https://your.site
