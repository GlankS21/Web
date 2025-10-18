---
title: "Отчет по работе с HTTP"
date: 2025-10-17
author: "glankS21"
draft: false
tags: ["HTTP", "Reports"]
---

# Работа с HTTP и API

**Студент:** Хоанг Ван Куан

---

## Задачи

1. Отправьте GET и POST запросы на любой веб-ресурс в CLI с помощью Telnet или netcat.
2. Отправьте запросы с помощью cURL.
3. Отправьте с его помощью GET-запрос для получения курса одной выбранной валюты за выбранный период. Используйте API Банка России: https://www.cbr.ru/development/sxml/

---
### 1. Отправьте GET и POST запросы на любой веб-ресурс в CLI с помощью Telnet или netcat.
#### Подключить с API
Эта команда используется для открытия TCP-соединения с сервером API

```bash
telnet jsonplaceholder.typicode.com 80
```
#### GET-запроса через Telnet
```bash
GET /posts/1 HTTP/1.0
Host: jsonplaceholder.typicode.com
```

Сервер получает запрос, ищет публикацию с идентификатором 1 и отправляет ответ HTTP, который включает статус (например, HTTP/1.1 200 OK) и содержимое данных (обычно JSON) этой публикации

![Скриншот выполнения команд в CLI](/image/telnet_get.png)
#### POST-запроса через Telnet
```bash
POST /posts HTTP/1.0
Host: jsonplaceholder.typicode.com
Content-Type: application/json
Content-Length: 42

{"title":"Test","body":"ok","userId":1}
```
Сервер получает запрос, обрабатывает JSON-данные в теле запроса, создает новый ресурс и возвращает HTTP-ответ

![Скриншот выполнения команд в CLI](/image/telnet_post.png)
### 2. Отправьте запросы с помощью cURL
#### GET-запроса через cURL:
GET — один из основных HTTP-методов (существуют также POST, PUT, DELETE и т. д.). Он используется для запроса данных с сервера

Базовый запрос GET с помощью cURL 
```bash
echo -e "cURL -v [https://httppbin.org/get](https://httppbin.org/get)
```
Здесь, cURL отправляет GET-запрос на конечную точку: https://httpbin.org/get

-v включает режим "verbose" для отображения подробностей запроса/ответа

![Скриншот выполнения команд в CLI](/image/cURL_1.png)

#### POST-запроса через cURL:
POST — это HTTP-метод, используемый для отправки данных на сервер

```bash
echo -e "cURL -v -X POST https://httppbin.org/post -d "{\"book\":\"Чапаев и Пустота\","price\":100,\"author\":\"Виктор Пелевин\"}"
```
Здесь 

-X POST указывает метод POST

-d: тело запроса

Кроме того, можно добавить 

-H "Content-Type: application/json" - сообщить серверу, что данные имеют формат JSON

![Скриншот выполнения команд в CLI](/image/curl_post_1.png)
![Скриншот выполнения команд в CLI](/image/curl_post_2.png)

В результате, сервер ответит JSON, содержащим информацию запроса

### 3. API Банка России: https://www.cbr.ru/development/sxml/
1. Открыть Postman и выбрать метод **GET**
2. Вставить URL API Банка России с нужными параметрами
#### GET-запроса
Например, чтобы получить стоимость доллара США с 10/10/2025 по 18/10/2025

![Скриншот выполнения](/image/postman_1.png)
#### Параметры

Ниже вы можете увидеть соответствующие ключи и значения

![Скриншот выполнения](/image/postman_2.png)
#### Результат
После нажатия **Send** Postman отправляет GET-запрос на сервер и получает XML-файл с курсами валют

![Скриншот выполнения](/image/postman_3.png)