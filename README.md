# lr1

Ваше предприятие занимается занимается обслуживанием и внедрением 1с услуг. Ваша организация разработала LandingPage (рекламный сайт) со списком ваших услуг. Фронтенд разработчик реализовал фронтенд часть вашего сайта, вам теперь необходимо реализовать бекенд часть.
Реализоват сервер на AspNetCore, работающий на порте 8007, принимающий следующие запросы. ( В файле документация). Инструкция по развертываню фронтенд части лежит в файле инструкция.
Рабочий прототип бэкенда лежит в файле funny
 

## Инструкция
1) Открыть CMD от имени  администратора в папке с Лабораторной в папке frontend
2) start nginx.exe
3) localhost:8086
4) Написать бэкенд для апи фронта, который описан в файле документация
5) Сделайте бэкенд на порте 8007, что-бы он жил на нем. (настройки AppSettings и AppSettings.Development -> "Urls": "http://*:8007")
Совет, добавьте swagger в проект, для этого нужно установить пакеты nuget Swashbuckle.AspNetCore.Swagger Swashbuckle.AspNetCore.SwaggerGen Swashbuckle.AspNetCore.SwaggerUI
И подключить их в programm.cs (можно посмотреть в проекте funny)

```
builder.Services.AddSwaggerGen();

app.UseSwagger();
app.UseSwaggerUI();
```

## Документация

### (Реализовать заказ колы)
```
/localhost:8007/strangeData/SendCola
export type TConnectDialogCola = {
    tasty: string | null,
    volume: string | null,
    name: string | null,
    phone: string | null
}
```
Вывод: Необходимо что-бы данные обработались и сохранились в логи
Дополнительно: Нужно что-бы данные обработались и сохранились в базу (дать возможность производить операции CRUD через swagger)



### (Реализовать вывоз полиции для пользователей хрома, смотреть по userAgent)
```
/localhost:8007/strangeData/HelpPolice
export type TConnectDialogPolice = {
    address: string | null,
}
```
Вывод: Необходимо прочитать header запроса и исходя из браузера, его типа, решить помогать или нет


### (Реализовать заказ пиццы)
```
/localhost:8007/strangeData/SendPizza
export type TConnectDialogPizza = {
    size: string | null,
    options: string[] | null,
    thickness: string | null
}
```
Вывод: Необходимо что-бы данные обработались и сохранились в логи
Дополнительно: Нужно что-бы данные обработались и сохранились в базу (дать возможность производить операции CRUD через swagger)


### (Реализовать вывод динамически формируемого списка услуг)
```
/localhost:8007/strangeData/GetDigitalList
export type TDigitalList = {
    filter: string | null,
    sorted: string | null,
}
```
Вывод: Необходимо что-бы данные по списку услуг генерировались на бэкенде и возвращались в виде html списка с услугами (список услуг придумать самому)
Дополнительно: Генерировать список через сваггер (добавление, удаление, редактирование) хранить в базе. (дать возможность производить операции CRUD через swagger)

### (Сохранить данные обратной связи)
```
/localhost:8007/mail/Send
export type TConnectDialog = {
    requiredTask: string[] | null,
    phone: string | null,
    name: string | null
}
```
Вывод: Необходимо что-бы данные обработались и сохранились в логи
Дополнительно: Нужно что-бы данные обработались и сохранились в базу (дать возможность производить операции CRUD через swagger)
