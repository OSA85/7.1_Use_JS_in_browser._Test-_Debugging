# 7.1_Use_JS_in_browser._Test-_Debugging

# Домашнее задание к занятию "7.1. Использование JS в браузере. Тестирование, дебаггинг."



---

## Задание 1. Установка Visual Studio code (VS Code) и настройка debugger'а

### Шаг 1. Установка VS Code

- установить [VS Code](https://code.visualstudio.com/download) ([статья](https://habr.com/ru/post/490754/) про VS Code на русском языке)
- выбрать версию, которая соответствует вашей операционной системе (windows, linux, macOs)
- загрузить и установить VS Code

### Шаг 2. Настройка debugger'a

В рамках задания необходимо сконфигурировать настройки debugger'a и протестировать его на веб-странице, пример кода которой приведен ниже. Подробности о настройке debugger'a по [ссылке на документацию](https://code.visualstudio.com/docs/editor/debugging)

- создайте репозиторий (все следующие шаги необходимо выполнять внутри репозитория)
- создайте файл index.html в корневом каталоге вашего репозитория и скопируйте в него следующий код

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <title>Document</title>
    </head>

    <body>
      <h1>hello world</h1>
    </body>
  </html>
  ```

  - создайте папку `.vscode`
  - в папке `.vscode` создайте файл `launch.json`
  - в файл `launch.json` добавьте код

  ```javascript
  {
    "version": "0.2.0",
    "configurations": [
      {
        "name": "Launch index.html", // название конфигурации(конфигураций может быть много, сделано для удобства запуска из debug-панели в VS Code)
        "type": "chrome", // название браузера(который должен быть установлен) в котором будет открыт тестируемый файл
        "request": "launch", // команда, которую необходимо выполнить дебагеру
        "file": "index.html" // название файла, к которому применить команду из пункта "request"
      }
    ]
  }
  ```

  - Нажмите кнопку `F5` на клавиатуре либо откройте дебаг панель VS Code, выебрите конфигурацию и запустите нажав на play
    ![пример](https://code.visualstudio.com/assets/docs/editor/debugging/debugging_hero.png)

### Шаг 3. Ожидаемый результат:

- открылся браузер хром
- в адресной строке браузера виден путь к index.html внутри файловой системы вашего компьютера
- на экране браузера отображается текст hello world

### Шаг 4. Отправка работы на проверку:

Мы с вами уже имеем высокий уровень профессионализма и можем самостоятельно разбираться с проблемами, возникающими на проектах.

Если вы не получаете ожидаемый результат - нужно это исправить:

Доведите дебаггер до рабочего состояния, убедитесь, что получаете ожидаемый результат из п. 3. В случае необходимости, установите нужные расширения и проверьте правильность путей доступа  к файлу, который запускается дебаггером.

В качестве результата домашнего задания присылайте на проверку ссылку на репозиторий с верной конфигурацией дебагера для VS Code.
Прикрепите ссылку на репозиторий в форму с домашним заданием

## Задание 2. Точки останова в VS Code

### Шаг 1. Подготовка репозитория

- Создайте новую ветку в репозитории из предыдущей задачи
- Обновите код в вашем index.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Document</title>
  </head>

  <body>
    <h1>hello world</h1>
  </body>
  <script>
    const x = "hello world";
    debugger;
    console.log(x);
  </script>
</html>
```

### Шаг 2. Остановка на явно прописанном `debugger`

- После того, как запустите отладку (с помощью нажатия кнопки F5) ваш код остановится, выполняя скрипт на строке с командой `debugger`
- Сделайте скриншот с точкой останова

Кроме явного указания `debugger` в коде, точки останова можно ставить прямо в VS code.

### Шаг 3. Остановка на точке установленной в VS code

- Для этого необходимо нажать на строку слева от номера строки.
- Появится красный кружок.
- Запустить отладку (кнопка F5)
- Выполнение остановилось на той строке, где была установлена точка останова
- Сделайте скриншот с точкой останова

### Шаг 4. Отправка работы на проверку:

В качестве результата домашнего задания присылайте на проверку ссылку на Pull request вашей новой ветки и скриншоты, которые нужно поместить в раздел issue репозитория
