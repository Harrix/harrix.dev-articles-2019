---
date: 2019-07-07
categories: [it, program]
tags: [Установка, Java, Android]
related-id: start-java
update: 2020-08-19
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2019/blob/main/install-jdk-on-windows/install-jdk-on-windows.md
permalink: https://harrix.dev/ru/blog/2019/install-jdk-on-windows/
lang: ru
---

# Установка JDK в Windows

![Featured image](featured-image.svg)

Для программирования под Java и, в частности, при создании приложений под Android на компе требуется установка JDK (Java Development Kit). В статье рассказывается как это сделать.

В статье рассматривается способ установки под Widows 10, но никакой разницы для других версий Windows не должно быть. Если вам нужна JDK более младшей версии или у вас, например, 32-битная Windows, то посмотрите [статью](https://github.com/Harrix/harrix.dev-blog-2014/blob/main/install-jdk-8-on-windows/install-jdk-8-on-windows.md) <!-- https://harrix.dev/ru/blog/2014/install-jdk-8-on-windows/ --> про установку JDK 8.

Скачиваем и устанавливаем с официального сайта:

<http://www.oracle.com/technetwork/java/javase/downloads/index.html>

![Выбор Oracle JDK](img/download_01.png)

_Рисунок 1 — Выбор Oracle JDK_

![Прокрутка вниз](img/download_02.png)

_Рисунок 2 — Прокрутка вниз_

Если у вас 32-битная операционная система, то скачивайте пакет под Windows x86. Для тех, кто не знает: версии программ для 64-битных операционных систем обозначаются **x64**, а для 32-битных обозначаются **x86**. Версии программ x86 можно устанавливать на 64-битные операционные системы, но лучше (за рядом некоторых исключений) устанавливать x64 версии. А версии программ x64 не получится установить на 32-битные операционные системы. В общем, выбираем:

![Выбор версии установщика](img/download_03.png)

_Рисунок 3 — Выбор версии установщика_

![Соглашение с условиями и скачивание](img/download_04.png)

_Рисунок 4 — Соглашение с условиями и скачивание_

Обратите внимание, что не всегда самая последняя версия Java подходит под ваши нужды. Например, на август 2020 года Android Studio не поддерживает Java 14 (Вылетает ошибка `Cause: invalid type code: 1C`). Поэтому в этом случае рекомендую установить предпоследнюю версию или более ранною:

![Скачивание более ранней версии Java](img/download_05.png)

_Рисунок 5 — Скачивание более ранней версии Java_

При этом вам нужно будет иметь учетную запись на Oracle:

![Требуется регистрация](img/download_06.png)

_Рисунок 6 — Требуется регистрация_

Процесс установки обычный и не представляет никаких трудностей:

![Установка](img/install_01.png)

_Рисунок 7 — Установка_

![Установка](img/install_02.png)

_Рисунок 8 — Установка_

![Процесс установки](img/install_03.png)

_Рисунок 9 — Процесс установки_

![Окончание установки](img/install_04.png)

_Рисунок 10 — Окончание установки_
