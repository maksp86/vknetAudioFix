---
layout: default
title: Метод Audio.Edit
permalink: audio/edit/
comments: true
---
# Метод Audio.Edit
Редактирует данные аудиозаписи на странице пользователя или сообщества.

Страница документации ВКонтакте [audio.edit](https://vk.com/dev/audio.edit).
## Синтаксис
``` csharp
public long Edit(AudioEditParams @params)
```

## Параметры
Класс **`AudioEditParams`** содержит следующие свойства:

+ **OwnerId** - Идентификатор владельца аудиозаписи (пользователь или сообщество). ID сообщества должен быть отрицательным. 

owner_id=1 — пользователь; 
owner_id=-1 — сообщество.  целое число, обязательный параметр
+ **AudioId** - Идентификатор аудиозаписи. положительное число, обязательный параметр
+ **Artist** - Новое название исполнителя. строка
+ **Title** - Новое название композиции. строка
+ **Text** - Новый текст аудиозаписи. строка
+ **GenreId** - Идентификатор жанра из списка аудио жанров. положительное число
+ **NoSearch** - 1 — аудиозапись не будет доступна в поиске. По умолчанию — 0. флаг, может принимать значения 1 или 0

## Результат
После успешного выполнения возвращает id текста, введенного пользователем (lyrics_id), если текст не был введен, вернет 0.

## Пример
``` csharp
// Редактируем запись.
long lyricsId = vk.Audio.Edit(159207130, 4793858, "Test Artist", "Test Title", "Test Text");
```

## Версия Вконтакте API v.5.44
Дата обновления: 26.01.2016 19:20:10