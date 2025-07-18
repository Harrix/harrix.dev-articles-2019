---
date: 2019-07-16
categories:
  - it
  - program
tags:
  - Установка
  - Android Studio
  - Android
  - Java
related-id: start-java
update: 2021-08-09
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2019/blob/main/install-android-studio/install-android-studio.md
permalink: https://harrix.dev/ru/articles/2019/install-android-studio/
lang: ru
attribution:
  - author: Google Inc.
    author-site: https://developer.android.com/license
    license: CC BY 2.5
    license-url: https://creativecommons.org/licenses/by/2.5/
    permalink: https://commons.wikimedia.org/wiki/File:Android_Studio_icon.svg
    permalink-date: 2019-06-07
    name: Android Studio icon.svg
  - author: Microsoft
    author-site: https://www.microsoft.com/
    license: Public domain
    license-url: https://en.wikipedia.org/wiki/Public_domain
    permalink: https://commons.wikimedia.org/wiki/File:Windows_10_Logo.svg
    permalink-date: 2019-06-22
    name: Windows 10 Logo.svg
---

# Установка Android Studio в Windows

![Featured image](featured-image.svg)

В статье рассказывается, как установить Android Studio в Windows 10.

<details>
<summary>📖 Содержание ⬇️</summary>

## Содержание

- [Предварительные напутствия](#предварительные-напутствия)
- [JDK](#jdk)
- [Скачивание Android Studio](#скачивание-android-studio)
- [Установка 64-битной Android Studio](#установка-64-битной-android-studio)
- [Установка предварительной сборки](#установка-предварительной-сборки)
- [Первоначальная настройка Android Studio](#первоначальная-настройка-android-studio)
- [Создание нового приложения](#создание-нового-приложения)
- [Для тех, у кого пользователь назван русскими буквами](#для-тех-у-кого-пользователь-назван-русскими-буквами)
- [Настройка SDK](#настройка-sdk)
- [Создание виртуального устройства](#создание-виртуального-устройства)
- [Другие эмуляторы](#другие-эмуляторы)
- [Запуск приложения](#запуск-приложения)
- [Ошибки при запуске](#ошибки-при-запуске)
- [Как запустить на реальном физическом устройстве](#как-запустить-на-реальном-физическом-устройстве)
- [Дополнительные настройки](#дополнительные-настройки)
- [Пример приложения](#пример-приложения)

</details>

## Предварительные напутствия

Настоятельно рекомендую устанавливать Android Studio на 64-битную Windows. На сайте Android Studio даже нет полноценного установщика на 32-битную версию. Раньше можно было архив скачать на 32-битную, но теперь и это не найти.

В идеале лучше использовать Windows 10 x64, но на Windows 8.1, 8, 7 тоже должно пойти.

Помните, что для Android Studio нужно минимум 8 Гб оперативной памяти (раньше было 2 Гб, а потом 4 Гб) и выше. Программа очень прожорливая. А на жестком диске нужно приличное количество места: после установки с эмулятором всё будет занимать от 15 Гб, а потом в процессе работы после установки библиотек и остального занимаемое место будет быстро расти.

Желательно иметь процессор от Intel, так как на процессорах AMD будут проблемы с эмуляторами Android. Но они решаемы.

И желательно, чтобы процессор имел поддержку виртуализации: сильно ускорит работу эмуляторов.

Если есть возможность и если пользователь на вашем компьютере называется по-русски, то поменяйте его на английское написание. Проблем с русскими именами будет много, причем не только в Android Studio. Очень много программ зарубежного производства рассчитаны на работу с файлами, в пути которых только латиница. Но если возможности нет для смены имени, то в статье будут описаны решения некоторых ваших проблем.

## JDK

Если раньше нужно было самостоятельно устанавливать JDK, то теперь он устанавливается самостоятельно при установке Android Studio:

![Установленный JDK](img/android-studio-jdk.png)

_Рисунок 1 — Установленный JDK_

Но если всё таки что-то пошло не так, то подробно об установке JDK можно узнать в статьях: [Установка JDK в Windows](https://github.com/Harrix/harrix.dev-articles-2019/blob/main/install-jdk-on-windows/install-jdk-on-windows.md) | [↗️](https://harrix.dev/ru/articles/2019/install-jdk-on-windows/) или [Установка OpenJDK в Windows](https://github.com/Harrix/harrix.dev-articles-2021/blob/main/install-open-jdk-on-windows/install-open-jdk-on-windows.md) | [↗️](https://harrix.dev/ru/articles/2021/install-open-jdk-on-windows/).

## Скачивание Android Studio

Переходим по ссылке: <https://developer.android.com/studio/>.

Нажимаем на кнопку скачивания:

![Кнопка скачивания Android Studio](img/download_01.png)

_Рисунок 2 — Кнопка скачивания Android Studio_

Соглашаемся с лицензией, прокручивая её, и скачиваем:

![Скачивание установщика](img/download_02.png)

_Рисунок 3 — Скачивание установщика_

## Установка 64-битной Android Studio

Запускаем скаченный файл:

![Первое окно установки](img/install_01.png)

_Рисунок 4 — Первое окно установки_

![Выбор компонентов для установки](img/install_02.png)

_Рисунок 5 — Выбор компонентов для установки_

Раньше рекомендовал менять пути установки Android Studio, но теперь же, наоборот, рекомендую устанавливать всё туда, куда хочет Android Studio, так как на большинстве машин теперь всё работает по умолчанию хорошо. И в следующем окне установщика можем оставить всё, как есть:

![Изменение пути установки](img/install_03.png)

_Рисунок 6 — Изменение пути установки_

Далее по умолчанию, или выберете, где в меню `Пуск` будет находиться Android Studio:

![Выбор папки в меню Пуск](img/install_04.png)

_Рисунок 7 — Выбор папки в меню Пуск_

И пошел процесс установки, в конце которой вы увидите окно окончания установки:

![Окончание установки](img/install_05.png)

_Рисунок 8 — Окончание установки_

![Последнее окно программы установки](img/install_06.png)

_Рисунок 9 — Последнее окно программы установки_

## Установка предварительной сборки

Если хотите получить самую последнюю версию Android Studio с самыми последними нововведениями, то можно установить предварительную версию.

На сайте <https://developer.android.com/studio/preview/> скачиваем превью версию программы:

![Страница с предварительными версиями программы](img/preview_01.png)

_Рисунок 10 — Страница с предварительными версиями программы_

![Соглашение с условиями](img/preview_02.png)

_Рисунок 11 — Соглашение с условиями_

Скачается не установщик, а архив, который мы распаковываем. И в папке `bin\` находится файл `studio64.exe`, который и запускаем:

![Файл Android Studio](img/preview_03.png)

_Рисунок 12 — Файл Android Studio_

## Первоначальная настройка Android Studio

При первом запуске Android Studio нас попросят выставить некоторые настройки. Сперва появится это окно:

![Запрос на импорт настроек](img/config_01.png)

_Рисунок 13 — Запрос на импорт настроек_

Спросят об отправке статистики в Google (я обычно соглашаюсь):

![Запрос об отправке статистики](img/config-send-statistics.png)

_Рисунок 14 — Запрос об отправке статистики_

![Приветственное окно](img/config_02.png)

_Рисунок 15 — Приветственное окно_

Выбираем стандартную настройку параметров:

![Выбор типа настроек](img/config_03.png)

_Рисунок 16 — Выбор типа настроек_

Выбор светлой или темной темы:

![Выбор темы редактора](img/config_04.png)

_Рисунок 17 — Выбор темы редактора_

Если Android Studio не смог найти сам JDK, то нужно ему помочь его найти:

![Кнопка выбора пути к JDK](img/config-jdk_01.png)

_Рисунок 18 — Кнопка выбора пути к JDK_

![Выбор пути к JDK](img/config-jdk_02.png)

_Рисунок 19 — Выбор пути к JDK_

![Выбранный путь к JDK](img/config-jdk_03.png)

_Рисунок 20 — Выбранный путь к JDK_

Список того, что будет установлено:

![Окно перед установкой компонентов](img/config_05.png)

_Рисунок 21 — Окно перед установкой компонентов_

Сама установка:

![Процесс установки](img/config_06.png)

_Рисунок 22 — Процесс установки_

Хорошо, если в окне окончания установки не будет красного текста, который свидетельствует о том, что что-то не установилось. Например, обладатели AMD процессоров, возможно, увидят сообщение, что не установился HAXM. Это будет означать, что стандартный эмулятор вы скорее всего нормально не запустите, но Android Studio будет работать полноценно. Если у вас появились другие сообщения об ошибках, то это плохо (гуглите).

Окончание установки:

![Окончание установки](img/config_07.png)

_Рисунок 23 — Окончание установки_

## Создание нового приложения

Теперь создадим новое приложение:

![Создание нового приложения](img/new-project_01.png)

_Рисунок 24 — Создание нового приложения_

Выбираем болванку нашего приложения `Empty Activity`:

![Выбор типа активности проекта](img/new-project_02.png)

_Рисунок 25 — Выбор типа активности проекта_

Выберем настройки проекта:

![Настройки проекта](img/new-project_03.png)

_Рисунок 26 — Настройки проекта_

**Внимание!** В пути к проекту, как и в его названии, не должно быть **русских букв** и **пробелов**! По умолчанию Android Studio сохраняет проекты в папке пользователя компьютера. И если у вас пользователь написан русскими буквами, то ничего не запустится!

Поэтому рекомендую создать какую-нибудь папку, где будете располагать свои проекты. Например, у меня это папка `C:\Users\sergi\OneDrive\Projects\Android`.

Когда выберите папку для ваших проектов (у меня `C:\Users\sergi\OneDrive\Projects\Android`), то придется вручную дописать название проекта в пути проекта, **убирая пробелы** из названия. Саму папку создавать не нужно: Android Studio создаст её сам. По итогу у меня получился путь `C:\Users\sergi\OneDrive\Projects\Android\MyApplication`. В последующие разы Android Studio будет создавать проекты по нормальному.

Также в этом окне выбираем язык Java как основной язык проекта (по умолчанию будет выбран Kotlin), минимальную версию Android, на котором будет запускаться приложение (версия 5.1 вполне сойдет).

И после кнопки `Finish` должно наконец-то появиться окно редактора Android Studio:

![Редактор Android Studio](img/new-project_04.png)

_Рисунок 27 — Редактор Android Studio_

Если надо, то закройте окно с подсказками:

![Окно с подсказками](img/new-project_tips.png)

_Рисунок 28 — Окно с подсказками_

В этот момент начнет работать Gradle, чтобы синхронизировать нужные библиотеки. И пока внизу не прекратиться крутиться кружок, то проект не готов к работе. Если у вас компьютер слабый, то крутиться кружок будет долго:

![Gradle синхронизирует проект](img/new-project_05.png)

_Рисунок 29 — Gradle синхронизирует проект_

Внизу пропала полоса загрузки, а кнопка запуска приложения стала зеленой. Это означает, что всё прогрузилось:

![Gradle закончил синхронизацию проекта](img/new-project_06.png)

_Рисунок 30 — Gradle закончил синхронизацию проекта_

Возможно (не обязательно) внизу появится сообщение об ошибке `Install Tools ... and sync project`:

![Ситуация, когда не хватает пакетов SDK](img/new-project_07.png)

_Рисунок 31 — Ситуация, когда не хватает пакетов SDK_

Эту ошибку вы будете встречать часто, когда будете открывать чьи-то проекты программ на Android Studio, сделанных не на вашем компьютере. Бояться её не нужно: просто щелкните по этой синей надписи `Install Tools ... and sync project`: Android Studio просто говорит, что ему нужны библиотеки SDK, которых нет у вас, и предлагает их скачать.

## Для тех, у кого пользователь назван русскими буквами

Если у вас пользователь назван русскими буквами, то в предыдущем разделе столкнетесь с тем, что Gradle не синхронизирует проект, и вообще он на всё ругается. Дело в том, что по умолчанию Gradle в новых версиях Android Studio ставит в отдельную папку, которая находится в папке пользователя, который у вас написан по-русски.

Вам нужно поменять папку на другую. Создадите, например, папку `C:\Android\gradle`. Потом идите в настройки Android Studio:

![Настройки Android Studio](img/settings.png)

_Рисунок 32 — Настройки Android Studio_

Там находим настройки Gradle. Видим, что Gradle сейчас находится в папке пользователя:

![Настройки Gradle](img/gradle_01.png)

_Рисунок 33 — Настройки Gradle_

Меняем его на путь к папке, которую мы создали, например, это `C:\Android\gradle`:

![Путь к Gradle](img/gradle_02.png)

_Рисунок 34 — Путь к Gradle_

Но после нажатия `OK` ничего не произойдет (иногда слетает светлая тема оформления). Нужно Gradle синхронизировать принудительно. Для этого наверху есть кнопка `Sync Project with Gradle Files`:

![Кнопка синхронизации проекта](img/gradle_03.png)

_Рисунок 35 — Кнопка синхронизации проекта_

И начнется небыстрый процесс скачивания и установки gradle в новую папку с последующей синхронизацией проекта:

![Кнопка синхронизации Gradle](img/gradle_04.png)

_Рисунок 36 — Кнопка синхронизации Gradle_

Чтобы убедиться, что всё прошло хорошо, то можно посмотреть папку `C:\Android\gradle`, где должны появиться следующие папки:

![Переустановка Gradle](img/gradle_05.png)

_Рисунок 37 — Переустановка Gradle_

Если слетит тема оформления, то нужно её вернуть (`File` → `Settings...`):

![Выбор темы оформления](img/color-scheme.png)

_Рисунок 38 — Выбор темы оформления_

## Настройка SDK

Надеялись, что всё установили? Нет, теперь нужно настроить SDK. Для этого из Android Studio нужно перейти в `SDK Manager`. Это можно сделать так:

![SDK Manager](img/sdk_01.png)

_Рисунок 39 — SDK Manager_

В разделе `SDK Platforms` вы выбираете те версии Android, которые вам потребуются. Можно, например, выбрать последнюю и минимальную версию, под которой всё должно работать, как показано на скриншоте ниже:

![Выбор версий Android в SDK](img/sdk_02.png)

_Рисунок 40 — Выбор версий Android в SDK_

В `SDK tools` выберете `Google USB Driver` (чтобы можно было подключать планшеты и смартфоны), `Google Web Driver`:

![Выбор инструментов SDK](img/sdk_03.png)

_Рисунок 41 — Выбор инструментов SDK_

Нажимаете на `OK` и начинается процесс установки:

![Информация, какие компоненты будут установлены](img/sdk_04.png)

_Рисунок 42 — Информация, какие компоненты будут установлены_

![Процесс установки](img/sdk_05.png)

_Рисунок 43 — Процесс установки_

![Окончание установки](img/sdk_06.png)

_Рисунок 44 — Окончание установки_

![Окончание установки](img/sdk_07.png)

_Рисунок 45 — Окончание установки_

## Создание виртуального устройства

Если у вас нет физического Android устройства, или же вы хотите своё приложение протестировать на конкретных устройствах с конкретной версией Android, то вам нужно будет виртуальное устройство.

Идем в `AVD Manager`:

![AVD Manager](img/avd_01.png)

_Рисунок 46 — AVD Manager_

Создаем новое виртуальное устройство:

![Создание нового виртуального устройства](img/avd_02.png)

_Рисунок 47 — Создание нового виртуального устройства_

Выбираем, какое устройство будем создавать. Допустим, мы хотим создать эмулятор `Pixel 2`:

![Выбор устройства](img/avd_03.png)

_Рисунок 48 — Выбор устройства_

**Внимание!** Важный шаг. Для эмулятора нужен образ версии Android, который будет устанавливаться на эмулятор. И вам нужно будет его скачать, нажав на `Download`. Например, нам нужен Android 10.0:

![Выбор версии Android](img/avd_04.png)

_Рисунок 49 — Выбор версии Android_

Рекомендую выбирать версию Android от 6 и выше. Например, выбирал однажды версию более низкой версии, но при попытке запуска приложений на эмуляторе возникала ошибка такого вида:

![Ошибка при запуске приложений](img/avd_error.png)

_Рисунок 50 — Ошибка при запуске приложений_

Обычно такая ошибка решается отключением `Instant Run` в настройках, но в тот раз не помогало. Так что еще раз рекомендую выбирать версию Android от 6 и выше (с ними у меня проблемы не возникли).

Если вы обладатель AMD процессора, то вполне вероятно, что образ Android x86 не заработает у вас, поэтому нужно выбирать (после неудачной попытки с образом x86) образ Android из другой вкладки под `armeabi-v7a`. Но сразу предупреждаю: если у вас эмулятор под `armeabi` заведется всё-таки, то работать он будет медленно, и было на практике много случаев, когда эмулятор потом так и не запускался:

![Выбор других образов для виртуального устройства](img/avd_05.png)

_Рисунок 51 — Выбор других образов для виртуального устройства_

После нажатия на кнопку `Download` начнется скачивание образа:

![Скачивание образа](img/avd_06.png)

_Рисунок 52 — Скачивание образа_

Возможно, что перед этим вас попросят согласиться с лицензией:

![Соглашение с лицензией](img/avd_license.png)

_Рисунок 53 — Соглашение с лицензией_

После этого образ Android будет доступен для выбора и можно продолжить создание виртуального устройства:

![Следующий шаг в создании эмулятора](img/avd_07.png)

_Рисунок 54 — Следующий шаг в создании эмулятора_

Здесь всё можно оставить по умолчанию:

![Выбор настроек эмулятора](img/avd_08.png)

_Рисунок 55 — Выбор настроек эмулятора_

Попробуем запустить эмулятор:

![Запуск эмулятора](img/avd_09.png)

_Рисунок 56 — Запуск эмулятора_

Если через какое-то время у вас в эмуляторе запустился полноценный Android, то всё замечательно:

![Запущенный эмулятор](img/avd_10.png)

_Рисунок 57 — Запущенный эмулятор_

Можно пока его не закрывать, так как будем его использовать для запуска нашего приложения. Но для будущего есть рекомендация: закрывать эмулятор лучше через крестик, а не через кнопку питания, которая находится чуть ниже: практика показывает, что при отключении питания потом эмулятор может не запуститься:

![Способ, как закрывать эмулятор](img/avd_11.png)

_Рисунок 58 — Способ, как закрывать эмулятор_

## Другие эмуляторы

Если родной эмулятор от Android Studio не запускается или тормозит так, что работать нельзя, то можно попробовать сторонние эмуляторы, благо их много.

[BlueStacks](https://github.com/Harrix/harrix.dev-articles-2018/blob/main/bluestacks-for-android-studio/bluestacks-for-android-studio.md) | [↗️](https://harrix.dev/ru/articles/2018/bluestacks-for-android-studio/) — известный эмулятор, предназначенный в первую очередь для запуска игр Android на ПК, но его можно использовать и для Android Studio.

[Genymotion](https://github.com/Harrix/harrix.dev-articles-2018/blob/main/genymotion-for-android-studio/genymotion-for-android-studio.md) | [↗️](https://harrix.dev/ru/articles/2018/genymotion-for-android-studio/) — по работе похож на родной эмулятор Android Studio. Можно устанавливать образы разных версий Android.

[Nox](https://github.com/Harrix/harrix.dev-articles-2018/blob/main/nox-for-android-studio/nox-for-android-studio.md) | [↗️](https://harrix.dev/ru/articles/2018/nox-for-android-studio/) — еще один популярный эмулятор от китайцев, которым лично много пользовался.

## Запуск приложения

Теперь у нас Android установлен и настроен. В процессе мы создали приложение до этого. Давайте его запустим. Для этого щелкаем по зеленому треугольнику в панели инструментов:

![Запуск приложения](img/run_01.png)

_Рисунок 59 — Запуск приложения_

Или из главного меню вызвать такую же команду:

![Запуск приложения](img/run_02.png)

_Рисунок 60 — Запуск приложения_

Обратите внимание на то, что раньше в Android Studio после нажатия на кнопку запуска предлагалось выбрать устройство, на котором будет происходить запуск, то сейчас вначале нужно выбрать устройство в выпадающем меню слева от кнопки запуска:

![Выбор устройства для запуска](img/run_03.png)

_Рисунок 61 — Выбор устройства для запуска_

Если вы выключили эмулятор, то можно либо его запустить через AVD Manager, либо тут выбрать эмулятор и по нему щелкнуть. Но если у вас устройство медленное, и эмулятор запускается долго, то лучше его запустить заранее.

Вас могут попросить что-нибудь дополнительно установить (привыкайте к этому):

![Запрос на установку нужных библиотек](img/run_04.png)

_Рисунок 62 — Запрос на установку нужных библиотек_

![Установка компонентов](img/run_05.png)

_Рисунок 63 — Установка компонентов_

Ждем, когда Gradle соберет проект, сформирует APK файл и загрузит его на устройство:

![Запуск приложения](img/run_06.png)

_Рисунок 64 — Запуск приложения_

## Ошибки при запуске

В реальности при установке Android Studio, при запуске приложений вас может ожидать букет ошибок. Причем они постоянно разные от версии к версии Android Studio. Могут быть проблемы в совместимости JDK и Android Studio, проблемы с операционной системой, учетными записями и так далее.

Всегда лучше загуглить текст ошибки, чтобы почитать, что говорят об этом люди.

На июль 2021 года, например, при создании пустого приложения и его запуске появляется ошибка:

![Ошибка при запуске](img/error_01.png)

_Рисунок 65 — Ошибка при запуске_

Для исправления этой ошибки, нужно внести изменения в файл `build.gradle` (обратите внимание, что таких файлов два: вам нужен второй). Нужно в трех местах число **31** поменять на **30**:

![Места, которые нужно поменять](img/error_02.png)

_Рисунок 66 — Места, которые нужно поменять_

А потом синхронизировать Gradle:

![Исправление ошибки](img/error_03.png)

_Рисунок 67 — Исправление ошибки_

Скорее всего, когда вы читаете эту статью, то именно этой ошибки не будет.

## Как запустить на реальном физическом устройстве

Вначале включим режим `Для разработчиков` на телефоне.

Зайдите в настройки телефона и в разделе `О телефоне` найдите пункт `Номер сборки`. Щелкните по нему **7 раз**. На скриншоте ниже мне пишут: «Не нужно, вы уже разработчик», — так как я уже нажимал 7 раз на этот пункт в прошлом:

![Включение режима разработчика](img/phone_01.png)

_Рисунок 68 — Включение режима разработчика_

Теперь в настройках телефона уровнем выше должен появиться пункт `Для разработчиков`:

![Режим «Для разработчиков»](img/phone_02.png)

_Рисунок 69 — Режим «Для разработчиков»_

В нем нужно включить пункт `Отладка по USB`:

![Пункт «Отладка по USB»](img/phone_03.png)

_Рисунок 70 — Пункт «Отладка по USB»_

Теперь, если вы включите свой смартфон через кабель к компьютеру, то устройство должно увидеться в списке устройств:

![Устройство видно в списке устройств](img/phone_04.png)

_Рисунок 71 — Устройство видно в списке устройств_

Но оно не получится запустить приложение на нем, так как устройство имеет подпись `Unknown Device`. Это возникает по причине того, что на самом устройстве мы не разрешили компьютеру подключение. Разрешите:

![Разрешение подключение на телефоне](img/phone_05.png)

_Рисунок 72 — Разрешение подключение на телефоне_

Если вы пропустили это окно, то вытащите кабель и вставьте его обратно.

После разрешения доступа устройство должно появиться полноценно:

![Устройство видно и доступно](img/phone_06.png)

_Рисунок 73 — Устройство видно и доступно_

Теперь его можно выбирать при запуске приложения на телефоне:

![Запущенное приложение](img/phone_07.png)

_Рисунок 74 — Запущенное приложение_

Сейчас я описал алгоритм подключения устройства в общем случае на примере Windows 10 и OnePlus 3t с Android 8.0. У вас подключение может отличаться. Лучше загуглить подключение вашего устройства к Android Studio. Пример запроса: `Galaxy A6 connect Android Studio Windows 7`.

Например, на Windows 7 нужно устанавливать драйвера телефона. Где взять для некоторых марок телефонов можно найти тут: <https://developer.android.com/studio/run/oem-usb>.

Для Samsung телефонов на Windows 7 драйвера автоматически ставятся при установке приложений [Samsung](https://www.samsung.com/ru/support/app/kies/) (устройства с версией Android до 4.2 включительно) и [Samsung Smart Switch](https://www.samsung.com/ru/support/app/smartswitch/) (устройства с версией Android выше 4.2).

Windows 10 обычно все драйвера находит автоматически.

## Дополнительные настройки

Настройки, описанные в данном разделе, опциональны, и можно их вообще не трогать.

Переходим в настройки приложения:

![Настройки приложения](img/config_12.png)

_Рисунок 75 — Настройки приложения_

![Настройки приложения](img/config_13.png)

_Рисунок 76 — Настройки приложения_

В разделе `General` я ставлю возможность увеличения шрифта колесиком мыши при нажатом `Ctrl`, а также устанавливаю правило, что при сохранении файла все лишние пробелы справа у всех строк будут удаляться.

## Пример приложения

В статье [Сложение двух чисел в Android Studio на Java (Android приложение)](https://github.com/Harrix/harrix.dev-articles-2019/blob/main/add-2-num-android/add-2-num-android.md) | [↗️](https://harrix.dev/ru/articles/2019/add-2-num-android/) написано как вы можете написать простое приложение по сложению двух чисел.
