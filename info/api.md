---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 📌 API Pixel Battle

API - [**https://api.pixelbattle.fun/**](https://api.pixelbattle.fun/)

## УСТАРЕВШАЯ ИНФОРМАЦИЯ!

## Что необходимо для работы с API?

Вся подробная информация о требованиях к запросу предоставлена в интересующем вас EndPoint'е

## Endpoints



{% swagger method="get" path="/" baseUrl="https://api.pixelbattle.fun" summary="API root" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "error": false, 
    "reason": "PixelAPI v4 works! Good time for chill :D"
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/users/:id" baseUrl="https://api.pixelbattle.fun" summary="Get user" %}
{% swagger-description %}
Позволяет получить информацию о пользователе из базы данных
{% endswagger-description %}

{% swagger-parameter in="path" required="true" name="id" type="String" %}
Discord user ID
{% endswagger-parameter %}

{% swagger-response status="404: Not Found" description="Пользователь не найден в БД" %}
```json
{
    "error": true,
    "reason": "EntityNotFound",
    "message": "Entity is not found",
    "data": {
        "entity": "user"
    }
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Пользователь найден в БД (пример)" %}
```json
{
    "userID": "663378999103324180",
    "cooldown": 1701451495266,
    "tag": "Pixelate It! Team",
    "username": "mirdukkkkk",
    "banned": null,
    "role": 2,
    "badges": ["1"],
    "points": 0
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/game" baseUrl="https://api.pixelbattle.fun" summary="Get game state" %}
{% swagger-description %}
Позволяет получить информацию о текущем состоянии игры
{% endswagger-description %}

{% swagger-response status="200: OK" description="Пример информации" %}
```json
{
    "name": "December",
    "cooldown": 500,
    "ended": false,
    "canvas": {
        "height": 80,
        "width": 160
    },
    "online": 5
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/pixels.png" baseUrl="https://api.pixelbattle.fun" summary="Get canvas" %}
{% swagger-description %}
Позволяет получить холст в виде картинки формата .png
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
Resolution: canvas.width x canvas.height (here 160x80)

Example:
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/pixels/tag" baseUrl="https://api.pixelbattle.fun" summary="Get tags info" %}
{% swagger-description %}
Позволяет получить информацию о тегах на холсте
{% endswagger-description %}

{% swagger-response status="200: OK" description="Пример информации" %}
```json
{
    "pixels": {
        "all": 12800,
        "used": 11234,
        "unused": 1566
    },
    "tags": [
        ["Pixelate It! Team", 10000],
        ["ing sqd.", 1234]
    ]
}
```
{% endswagger-response %}
{% endswagger %}
