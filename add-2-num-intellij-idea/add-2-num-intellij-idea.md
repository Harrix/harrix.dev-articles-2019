---
date: 2019-07-15
categories: [it, programming]
tags: [IntelliJ IDEA, JetBrains, Java, Сложение двух чисел]
related-id: start-java
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2019/blob/main/add-2-num-intellij-idea/add-2-num-intellij-idea.md
url: https://harrix.dev/ru/blog/2019/add-2-num-intellij-idea/
---

# Сложение двух чисел в IntelliJ IDEA на Java (консольное приложение)

В статье рассказывается как создать консольного приложения сложения двух чисел под Java в IntelliJ IDEA.

## Приготовления

В статье [Установка IntelliJ IDEA в Windows](https://github.com/Harrix/harrix.dev-blog-2019/blob/main/install-intellij-idea/install-intellij-idea.md) узнаете, как всё установить и настроить.

## Создание проекта

Итак, открываем IntelliJ IDEA:

![Создание нового проект](img/new-project_01.png)

Убеждаемся, что тут стоит не `No SDK`:

![Выбор типа проекта](img/new-project_02.png)

Выбираем шаблон консольного приложения:

![Выбор шаблона для проекта](img/new-project_03.png)

Выбираем имя приложения (без русских букв и пробелов) и папку размещения. Можете указать и свой домен, если таковой имеется, но для тестовых приложений это не важно:

![Выбор названия проекта, папки и домена](img/new-project_04.png)

Если вы указали несуществующую папку, то он спросит у вас: создавать ее или нет:

![Диалоговое окно по запросу создания новой папки](img/new-project_05.png)

Потом предложит в том же окне открыть, что и предыдущий проект или в новом (если перед этим был открыт другой проект). Решайте сами: нужен ли вам открытый первый проект или нет.

И проект создан:

![Созданный проект в редакторе](img/new-project_06.png)

## Болванка приложения Java

Пропишем создание экземпляра класса `Scanner` для считывания данных с консоли в функции `main`:

```java
Scanner sc = new Scanner(System.in);
```

`Scanner` подсветится красным. Это означает, что соответствующие пакеты, в которых прописан данный класс не подключены:

![Ошибка, возникающая при отсутствии импорта классов](img/import_01.png)

Поставим курсор на данном слове и нажмем `Alt` + `Enter`, чтобы подключить нужные библиотеки:

![Выбор команды Import class](img/import_02.png)

![Ошибка исчезла](img/import_03.png)

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

Нажмите `Ctrl` + `S` для сохранения изменений.

## Запуск программы

![Запуск проекта](img/run_01.png)

Если вы видите вопросы вместо `Введите первое число`, то под спойлером решение:

---

**Изменение кодировки** <!-- !details -->

Проблема касается старых версий IntelliJ IDEA:

![Вопросы вместо русского текста](img/error-encoding_01.png)

Дело в том, что старая IntelliJ IDEA по умолчанию создаваемые файлы кодирует не в UTF-8, а в windows-1251:

![Кодировка windows-1251](img/error-encoding_02.png)

Исправим кодировку файла:

![Выбор пункта меню по изменению кодировки](img/error-encoding_03.png)

![Выбор UTF-8 кодировки](img/error-encoding_04.png)

![Выбор варианта Convert](img/error-encoding_05.png)

Теперь завершим принудительно предыдущий запуск приложения:

![Завершение работы программы](img/error-encoding_06.png)

И повторно запустим наше приложение любым способом.

---

Получаем наше приложение:

![Русские буквы в консоли](img/run_02.png)

Тестируем приложение:

![Вывод приложения](img/run_03.png)

Наше приложение написано.
