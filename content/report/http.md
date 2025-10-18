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

### 2. Отправьте запросы с помощью cURL
#### GET-запроса через cURL:
```bash
echo -e "cURL -v [https://httppbin.org/get](https://httppbin.org/get)
```

![Скриншот выполнения команд в CLI](/static/image/cURL_1.png)

#### POST-запроса через cURL:
![Скриншот выполнения команд в CLI](/static/image/curl_post_1.png)
![Скриншот выполнения команд в CLI](/static/image/curl_post_2.png)

### 3. API Банка России: https://www.cbr.ru/development/sxml/
#### GET-запроса
![Скриншот выполнения](/static/image/postman_1.png)
#### Параметры
![Скриншот выполнения](/static/image/postman_2.png)
#### Результат
![Скриншот выполнения](/static/image/postman_3.png)