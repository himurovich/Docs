---
title: "Сниппеты"
sortorder: "4"
translation: "building-sites/elements/snippets"
---

[Сниппеты](extending-modx/snippets "Сниппеты") - это способ, с помощью которого MODX позволяет вам запускать динамический код PHP на любой из ваших страниц. Они могут предоставлять такой контент как меню, списки блогов или новостей, поиск и любые другие функциональные возможности на основе форм и все остальное, что ваш сайт должен генерировать по требованию.

## Использование сниппетов

После того, как у вас установлен Сниппет, вы можете использовать его, просто поместив его теги в шаблон, блок или TV или содержимое документа, где бы вы ни хотели, чтобы вывод Сниппета отображался.

``` php
[[MySnippet]]
```

Если вы ожидаете, что код сниппета будет динамическим для разных пользователей, вы также можете вызвать сниппет без кэширования:

``` php
[[!MySnippet]]
```

## Свойства сниппета

Сниппеты могут иметь [Свойства](building-sites/properties-and-property-sets "Свойства и наборы свойств"), которые могут быть передана в вызове Сниппета, например так:

``` php
[[!Wayfinder? &startId=`0` &level=`1`]]
```

Вы также можете объединить эти свойства в [Наборы свойств](building-sites/properties-and-property-sets "Свойства и наборы свойств"), которые представляет собой динамический набор свойств, которые могут быть присоединены к любому сниппету (или элементу в этом отношении). Это позволяет вам совместно использовать общие конфиги свойств в вызове сниппета в одном месте.

Скажем, у вас есть набор свойств под названием 'Menu' с `startId` установленным в 0 и `level` установленным в 1:

``` php
[[!Wayfinder@Menu]]
```

Сниппет автоматически загрузит эти свойства в сниппет. И даже эти свойства могут быть переопределены:

``` php
[[!Wayfinder@Menu? &level=`2`]]
```

который переопределит установленное значение `level` на 1, установив вместо этого 2.

## Установка Сниппетов

Вы также можете скачать и установить сниппеты через [Управление пакетами](extending-modx/transport-packages "Управление пакетами"). Смотрите руководство по [установке пакетов](building-sites/extras "Установка пакетов") для получения дополнительной информации.

## Смотрите также

- [Установка пакетов](building-sites/extras "Установка пакетов")
