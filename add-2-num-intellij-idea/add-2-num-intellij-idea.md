---
date: 2019-07-15
categories: [it, programming]
tags: [IntelliJ IDEA, JetBrains, Java, Сложение двух чисел]
related-id: start-java
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-blog-2019/blob/main/add-2-num-intellij-idea/add-2-num-intellij-idea.md
permalink: https://harrix.dev/ru/blog/2019/add-2-num-intellij-idea/
lang: ru
attribution:
- {author: JetBrains, author-site: 'https://www.jetbrains.com/', license: Public domain,
  license-url: 'https://en.wikipedia.org/wiki/Public_domain', permalink: 'https://commons.wikimedia.org/wiki/File:IntelliJ_IDEA_Logo.svg',
  permalink-date: 2019-06-10, name: IntelliJ IDEA Logo.svg}
---

# Сложение двух чисел в IntelliJ IDEA на Java (консольное приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать консольного приложения сложения двух чисел под Java в IntelliJ IDEA.

## Приготовления

В статье [Установка IntelliJ IDEA в Windows](https://github.com/Harrix/harrix.dev-blog-2019/blob/main/install-intellij-idea/install-intellij-idea.md) <!-- https://harrix.dev/ru/blog/2019/install-intellij-idea/ --> узнаете, как всё установить и настроить.

## Создание проекта

Итак, открываем IntelliJ IDEA:

![Создание нового проект](img/new-project_01.png)

_Рисунок 1 — Создание нового проект_

Убеждаемся, что тут стоит не `No SDK`:

![Выбор типа проекта](img/new-project_02.png)

_Рисунок 2 — Выбор типа проекта_

Выбираем шаблон консольного приложения:

![Выбор шаблона для проекта](img/new-project_03.png)

_Рисунок 3 — Выбор шаблона для проекта_

Выбираем имя приложения (без русских букв и пробелов) и папку размещения. Можете указать и свой домен, если таковой имеется, но для тестовых приложений это не важно:

![Выбор названия проекта, папки и домена](img/new-project_04.png)

_Рисунок 4 — Выбор названия проекта, папки и домена_

Если вы указали несуществующую папку, то он спросит у вас: создавать ее или нет:

![Диалоговое окно по запросу создания новой папки](img/new-project_05.png)

_Рисунок 5 — Диалоговое окно по запросу создания новой папки_

Потом предложит в том же окне открыть, что и предыдущий проект или в новом (если перед этим был открыт другой проект). Решайте сами: нужен ли вам открытый первый проект или нет.

И проект создан:

![Созданный проект в редакторе](img/new-project_06.png)

_Рисунок 6 — Созданный проект в редакторе_

## Болванка приложения Java

Пропишем создание экземпляра класса `Scanner` для считывания данных с консоли в функции `main`:

```java
Scanner sc = new Scanner(System.in);
```

`Scanner` подсветится красным. Это означает, что соответствующие пакеты, в которых прописан данный класс не подключены:

![Ошибка, возникающая при отсутствии импорта классов](img/import_01.png)

_Рисунок 7 — Ошибка, возникающая при отсутствии импорта классов_

Поставим курсор на данном слове и нажмем `Alt` + `Enter`, чтобы подключить нужные библиотеки:

![Выбор команды Import class](img/import_02.png)

_Рисунок 8 — Выбор команды Import class_

![Ошибка исчезла](img/import_03.png)

_Рисунок 9 — Ошибка исчезла_

В итоге получаем болванку программы на Java, которую потом удобно использовать для других приложений учебного толка:

```java
package com.company;

import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
  // write your code here

        Scanner sc = new Scanner(System.in);
    }
}
```

## Написание кода основной программы

А теперь пропишем основной код нашей программы:

```java
int a, b, c;

System.out.println("Введите первое число");
a = sc.nextInt();//Считываем первое число

System.out.println("Введите второе число");
b = sc.nextInt();//Считываем второе число

c = a + b;
System.out.println("c = " + c);
```

Полная программа будет выглядеть так:

```java
package com.company;

import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
  // write your code here

        Scanner sc = new Scanner(System.in);

        int a, b, c;

        System.out.println("Введите первое число");
        a = sc.nextInt();//Считываем первое число

        System.out.println("Введите второе число");
        b = sc.nextInt();//Считываем второе число

        c = a + b;

        System.out.println("c = " + c);
    }
}
```

![Код программы](img/java.png)

_Рисунок 10 — Код программы_

Нажмите `Ctrl` + `S` для сохранения изменений.

## Запуск программы

![Запуск проекта](img/run_01.png)

_Рисунок 11 — Запуск проекта_

Если вы видите вопросы вместо `Введите первое число`, то под спойлером решение:

---

**Изменение кодировки** <!-- !details -->

Проблема касается старых версий IntelliJ IDEA:

![Вопросы вместо русского текста](img/error-encoding_01.png)

_Рисунок 12 — Вопросы вместо русского текста_

Дело в том, что старая IntelliJ IDEA по умолчанию создаваемые файлы кодирует не в UTF-8, а в windows-1251:

![Кодировка windows-1251](img/error-encoding_02.png)

_Рисунок 13 — Кодировка windows-1251_

Исправим кодировку файла:

![Выбор пункта меню по изменению кодировки](img/error-encoding_03.png)

_Рисунок 14 — Выбор пункта меню по изменению кодировки_

![Выбор UTF-8 кодировки](img/error-encoding_04.png)

_Рисунок 15 — Выбор UTF-8 кодировки_

![Выбор варианта Convert](img/error-encoding_05.png)

_Рисунок 16 — Выбор варианта Convert_

Теперь завершим принудительно предыдущий запуск приложения:

![Завершение работы программы](img/error-encoding_06.png)

_Рисунок 17 — Завершение работы программы_

И повторно запустим наше приложение любым способом.

---

Получаем наше приложение:

![Русские буквы в консоли](img/run_02.png)

_Рисунок 18 — Русские буквы в консоли_

Тестируем приложение:

![Вывод приложения](img/run_03.png)

_Рисунок 19 — Вывод приложения_

Наше приложение написано.
