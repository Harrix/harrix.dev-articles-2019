---
date: 2019-07-23
categories: [it, programming]
tags: [Android Studio, Android, Java, Сложение двух чисел]
related-id: start-java
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2019/blob/main/add-2-num-android/add-2-num-android.md
---

# Сложение двух чисел в Android Studio на Java (Android приложение)

В статье рассказывается как создать приложения сложения двух чисел в Android Studio для Android.

## Приготовления

В статье [Установка Android Studio в Windows](https://github.com/Harrix/harrix.dev-blog-2019/blob/main/install-android-studio/install-android-studio.md) узнаете, как установить и настроить Android Studio.

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

![Выбор типа главной активности](img/new-project_02.png)

![Выбор настроек проекта](img/new-project_03.png)

![Готовый проект в Android Studio](img/new-project_04.png)

Перейдем вначале к файлу `activity_main.xml`, который отвечает за разметку внешнего вида приложения:

![Переход к activity_main.xml](img/xml_01.png)

## Размещение компонентов

По умолчанию в Android Studio в качестве разметки используется контейнер `ConstraintLayout`. Для новичков он не совсем простой. Поменяем на обычный `LinearLayout`.

Перейдем в текстовой режим разметки XML файла. Там мы внутри контейнера `ConstraintLayout` видим элемент `TextView` с фразой `Hello, World!`:

![Переход к текстовому отображению activity_main.xml](img/xml_02.png)

И заменим содержимое всего файла на следующий код:

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingLeft="16dp"
    android:paddingRight="16dp"
    android:orientation="vertical" >

</LinearLayout>
```

Перейдем обратно в режим дизайна:

![Возвращение к визуальному редактированию activity_main.xml](img/xml_03.png)

Перетащим текстовое поле:

![Перетащенное текстовое поле](img/edit-text_01.png)

Включим отображение атрибутов компонентов, если оно отключено:

![Отображение атрибутов компонентов](img/edit-text_02.png)

Поменяем значение поля `id` (имя компонента) на `editText`:

![Идентификатор текстового поля](img/edit-text_03.png)

Поменяем начальный текст в поле ввода на какое-нибудь число:

![Изменение параметра text](img/edit-text_04.png)

Перетащим еще одно текстовое поле, которое будет иметь имя `editText2`:

![Второе текстовое поле](img/edit-text_05.png)

Также поменяем начальный текст в поле ввода на какое-нибудь число:

![Изменение параметра text](img/edit-text_06.png)

Перетащим кнопку:

![Кнопка](img/button_01.png)

Поменяем текст на кнопки, например, на `Сложить`:

![Кнопка](img/button_02.png)

Перетащим поле с текстом для вывода:

![Текстовое поле для вывода](img/text-view_01.png)

Начальный текст поменяем, например, на `=`:

![Текстовое поле для вывода](img/text-view_02.png)

Начальный размер шрифта в TextView маленький, так что увеличим его. За это отвечает свойство `textSize`, которое можно найти либо в списке всех атрибутов, либо через поиск:

![Текстовое поле для вывода](img/text-view_03.png)

Поменяем на `36sp`:

![Текстовое поле для вывода](img/text-view_04.png)

В текстовом варианте получившаяся разметка будет такой:

![Переход в режим текстового редактирования activity_main.xml](img/xml_04.png)

![Переход в режим текстового редактирования activity_main.xml](img/xml_05.png)

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingLeft="16dp"
    android:paddingRight="16dp"
    android:orientation="vertical" >

    <EditText
        android:id="@+id/editText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="2" />

    <EditText
        android:id="@+id/editText2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="3" />

    <Button
        android:id="@+id/button"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Сложить" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="="
        android:textSize="36sp" />
</LinearLayout>
```

Да, можно было не перетаскивать компоненты в визуальном режиме, а вручную написать этот код в текстовом режиме.

## Соединение компонентов с Java кодом

Перейдите в окно редактирования кода главной активности:

![Переход в Java код активности](img/java_01.png)

Добавьте в класс три переменных, отвечающих за два текстовых поля ввода и одно текстовое поля вывода:

```java
private EditText editText;
private EditText editText2;
private TextView textView;
```

![Объявление переменных в коде](img/java_02.png)

Видите, что в этих строчках есть красные слова (что означает наличие ошибки). Это от того, что не подключены библиотеки для этих типов данных. Курсор (каретку) щелкните по слову `EditText`, и нажмите `Alt` + `Enter`. И там выберите `Import class`:

![Предложение решить проблему через Alt + Enter](img/java_03.png)

![Импорт класса EditText](img/java_04.png)

Также сделайте с `TextView`:

![Импорт класса TextView](img/java_05.png)

Краснота уйдет:

![Отсутствие ошибок после импорта классов](img/java_06.png)

В методе `onCreate` соедините созданные переменные с теми полями, что объявлены в разметке.

**Внимание!** Добавлять эти строчки нужно после **setContentView**:

```java
editText = findViewById(R.id.editText);
editText2 = findViewById(R.id.editText2);
textView = findViewById(R.id.textView);
```

![Место расположения кода с findViewById](img/java_07.png)

Обратите внимание, что значение `id` компонентов совпадают с `id` компонентов из XML файлов. То что названия Java переменных совпадают — это только для удобства:

![Указание на ID элементов из XML файла](img/java_08.png)

Теперь надо прописать код обработки клика кнопки, чтобы при её нажатии считывались числа, складывались и сумма выводилась в TextView. Будет рассмотрено два способа.

## Первый способ обработки клика кнопки

Добавим в класс активности новый метод, например, с названием `clickButton`:

```java
public void clickButton(View v) {
}
```

![Метод clickButton](img/first-way_01.png)

И через `Alt` + `Enter` убираем красноту:

![Метод clickButton без красноты](img/first-way_02.png)

В метод него добавим код обработки клика кнопки:

```java
// Объявим числовые переменные
double a, b, c;

// Считаем с editText и editText2 текстовые значения
String s1 = editText.getText().toString();
String s2 = editText2.getText().toString();

// Преобразуем текстовые переменные в числовые значения
a = Double.parseDouble(s1);
b = Double.parseDouble(s2);

// Проведем с числовыми переменными нужные действия
c = a + b;

// Преобразуем ответ в число
String s = Double.toString(c);

// Выведем текст в textView
textView.setText(s);
```

![Тело метода clickButton](img/first-way_03.png)

Полный код файла `MainActivity.java` у меня выглядит так:

```java
package com.example.add2num;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    private EditText editText;
    private EditText editText2;
    private TextView textView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText = findViewById(R.id.editText);
        editText2 = findViewById(R.id.editText2);
        textView = findViewById(R.id.textView);
    }

    public void clickButton(View v) {
        // Объявим числовые переменные
        double a, b, c;

        // Считаем с editText и editText2 текстовые значения
        String s1 = editText.getText().toString();
        String s2 = editText2.getText().toString();

        // Преобразуем текстовые переменные в числовые значения
        a = Double.parseDouble(s1);
        b = Double.parseDouble(s2);

        // Проведем с числовыми переменными нужные действия
        c = a + b;

        // Преобразуем ответ в число
        String s = Double.toString(c);

        // Выведем текст в textView
        textView.setText(s);
    }
}
```

Обратите внимание на то, что, если вы проект в самом начале назвали по-другому (у меня он называется `Add2num`), то первая строчка с `package` у вас будет другой. И если вы бездумно скопируете строчку `package com.example.add2num;` в ваш проект, который называется по-другому, то у вас программа не соберется и не запустится!

Мы почти закончили, но мы нигде не прописали, что метод `clickButton` должен срабатывать при клике на кнопку. Исправим это.

Перейдем в XML файл разметки, в котором мы уже работали. И в нем в компоненте `Button` добавим строчку:

```xml
android:onClick="clickButton"
```

![Изменения в XML файле](img/first-way_04.png)

Полный код файла `activity_main.xml`:

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingLeft="16dp"
    android:paddingRight="16dp"
    android:orientation="vertical" >

    <EditText
        android:id="@+id/editText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="2" />

    <EditText
        android:id="@+id/editText2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="3" />

    <Button
        android:id="@+id/button"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:onClick="clickButton"
        android:text="Сложить" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="="
        android:textSize="36sp" />
</LinearLayout>
```

## Запуск приложения

Если вы используете не физическое устройство, а эмулятор, то всегда рекомендую вначале запустить эмулятор, а потом уже запускать приложение:

![Запуск AVD Manager](img/run_01.png)

![Запуск эмулятора](img/run_02.png)

![Запущенный эмулятор](img/run_03.png)

Теперь можем запускать наш проект:

![Запуск компилирования проекта](img/run_04.png)

![Запущенное приложение](img/run_05.png)

Введем какие-нибудь числа и нажмем кнопку:

![Результат выполнения программы](img/run_06.png)

## Второй способ обработки клика кнопки

Теперь реализуем второй способ обработки клика, который я рекомендую использовать вместо первого. А чем плох первый? Мы в XML файле прописали, как называется метод из Java кода, который нужно запускать, то есть смешали код реализации и код разметки между собой. Это не очень хорошо. Попробуем не вносить изменения в XML файл (то есть строчку `android:onClick="clickButton"` добавлять не будем).

Добавим еще одну переменную для связки кнопки из XML файла с Java кодом. Красноту помните, как убирать:

```java
private Button button;
```

![Объявление переменной button](img/second-way_01.png)

Также пропишите этот код:

```java
button = findViewById(R.id.button);
```

![Код нахождения кнопки через findViewById](img/second-way_02.png)

А теперь напишем обработчик клика кнопки через `OnClickListener`. Пропишите такой код:

```java
button.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {

    }
});
```

**Внимание!** Обратите внимание, что в первом способе код обработки кнопки `clickButton` мы писали **вне** метода `onCreate`, а сейчас пишем **внутри** метода `onCreate`:

![Обработчик клика кнопки](img/second-way_03.png)

Пропишем реализацию метода:

```java
// Объявим числовые переменные
double a,b,c;

// Считаем с editText и editText2 текстовые значения
String S1 = editText.getText().toString();
String S2 = editText2.getText().toString();

// Преобразуем текстовые переменные в числовые значения
a = Double.parseDouble(S1);
b = Double.parseDouble(S2);

// Проведем с числовыми переменными нужные действия
c = a + b;

// Преобразуем ответ в число
String s = Double.toString(c);

// Выведем текст в textView
textView.setText(s);
```

![Реализация клика кнопки](img/second-way_04.png)

Полный код файла `MainActivity.java`:

```java
package com.example.add2num;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    private EditText editText;
    private EditText editText2;
    private TextView textView;
    private Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText = findViewById(R.id.editText);
        editText2 = findViewById(R.id.editText2);
        textView = findViewById(R.id.textView);
        button = findViewById(R.id.button);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Объявим числовые переменные
                double a,b,c;

                // Считаем с editText и editText2 текстовые значения
                String S1 = editText.getText().toString();
                String S2 = editText2.getText().toString();

                // Преобразуем текстовые переменные в числовые значения
                a = Double.parseDouble(S1);
                b = Double.parseDouble(S2);

                // Проведем с числовыми переменными нужные действия
                c = a + b;

                // Преобразуем ответ в число
                String s = Double.toString(c);

                // Выведем текст в textView
                textView.setText(s);
            }
        });
    }
}
```

Файл Полный код файла `activity_main.xml` остался без изменений (строчки `android:onClick="clickButton"` тут нет):

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingLeft="16dp"
    android:paddingRight="16dp"
    android:orientation="vertical" >

    <EditText
        android:id="@+id/editText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="2" />

    <EditText
        android:id="@+id/editText2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="3" />

    <Button
        android:id="@+id/button"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Сложить" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="="
        android:textSize="36sp" />
</LinearLayout>
```

При запуске мы получим такое же по функциональности приложение, как и при первом способе:

![Запущенное приложение](img/run_07.png)
