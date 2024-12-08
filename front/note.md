# Lesson 2

## Горячие клавиши

### Редактор VS Code

`Ctrl + Shift + P` - открыть палитру команд
`Ctrl + P` - поиск файлов
`Ctrl + Shift + F` - поиск по файлам
`Alt + Click` - разделенный курсор
`Alt + DoubleClick` - выделить с разделенным курсором
`Ctrl + Tab` - переключение между открытыми вкладками (если держать, можно выбрать, если коротко нажимать - переключение между текущей и предыдущей)
`Alt + Z` - Вписать код в ширину экрана (Вид - Перенос по словам - галочка)
`Ctrl + D` - Выделить множественным курсором похожие участки кода (для последующей правки или вырезки)



Выходит, вы можете выделять текст в разных местах, копировать, а так же вставлять текст в разные места.

Делать множественные выделения через двойной клик и редактировать.

### Windows

`Ctrl + A` - выделить все
`Ctrl + S` - сохранить
`Ctrl + A` - выделить все
`Ctrl + C` - скопировать
`Ctrl + V` - вставить
`Ctrl + X` - вырезать
`Ctrl + Z` - отменить
`Ctrl + Shift + Z` - повтор (откат отмены)

## Стили CSS

#### Определение стилей прямо в теге

```html
<h1 style="color:  blue;">ФИО &#128526;</h1>
```

#### Определение стилей в теге style

Мы можем определить стили внутри документа. Для этого есть специальное место - `head`

Внутри тега `head` есть тег `style` - где мы можем определить стили.

```html
<style>
        h1 {
            color: lightcoral;
            text-align: center;
            font-family: monospace;
            font-size: 40px;
        }
</style>
```

### Виды селекторов CSS

1. Селектор по тегу
   Самый простой вариант - это выбрать тег. Стили будут воздействовать на все элементы с таким тегом.

```css
h1 {
  color: lightcoral;
}
```

2. Селектор по классу
   Класс - глобальный атрибут, который мы можем задать любому элементу.
   Делая селектор по классу, мы можем выбрать все элементы, у которых есть такой класс.

```html
<p class="text">Текст</p>
```

```css
.text {
    color: lightcoral;
    }
```

3. Селектор по id
   Id - это уникальный атрибут, который мы можем задать любому элементу.
   Делая селектор по id, мы можем выбрать только один элемент, у которого есть такой id. Т.е. он должен быть уникальным.

```html
<p id="text">Текст</p>
```

```css
#text {
    color: lightcoral;
}
```

Мы можем комбинировать селекторы. Например, определенный тег, с определенным классом. Или комбинация двух классов. **Делается это через пробел.**

Или воздействовать и на один вариант и на второй. **Делается это через запятую.**

### Цвета в CSS

1. Цвет по имени
   Например, `red`, `green`, `blue`, `yellow`, `black`, `white`

2. Цвет по коду
   Например, `#ff0000`, `#00ff00`, `#0000ff`, `#ffff00`, `#000000`, `#ffffff`

3. Цвет по процентам
   Например, `rgb(255, 0, 0)`, `rgb(0, 255, 0)`, `rgb(0, 0, 255)`, `rgb(255, 255, 0)`, `rgb(0, 0, 0)`, `rgb(255, 255, 255)`

4. Цвет по процентам и альфа каналу (прозрачность)
   Например, `rgba(255, 0, 0, 0.5)`, `rgba(0, 255, 0, 0.5)`, `rgba(0, 0, 255, 0.5)`, `rgba(255, 255, 0, 0.5)`, `rgba(0, 0, 0, 0.5)`, `rgba(255, 255, 255, 0.5)`

[Цвета в CSS](https://colorscheme.ru/html-colors.html)

Специфичность селекторов - это способность селектора быть более или менее специфичным, что можно описать как точность, или "силу" селектора.

Чем выше специфичность селектора, тем больший приоритет для браузера будет иметь этот селектор.

[Специфичность селекторов](https://developer.mozilla.org/ru/docs/Web/CSS/Specificity)

`!important` - это способность дать браузеру указание на то, что этот стиль должен быть применен, независимо от того, какие другие стили были определены.

### Каталоги HTML и CSS

1. [html5book](https://html5book.ru/osnovy-html/)
2. [htmlbook](https://htmlbook.ru/html)
3. [w3schools](https://www.w3schools.com/html/)

### Единицы измерения в CSS

1. `px` - Пиксели. Абсолютные единицы измерения
2. `%` - Проценты. Относительно размера родителя
3. `em` - размер шрифта родителя
4. `rem` - Относитльно размера шрифта корня (тег html)
5. `vh` - Относительно высоты экрана
6. `vw` - Относительно ширины экрана


### Как набрать HTML код в HTML коде?

Спецзнаки - это символы, которые нельзя набрать на клавиатуре. Например, символы, которые нельзя набрать на клавиатуре, но которые нужны для HTML кода.

[Каталог спецзнаков](https://htmlweb.ru/html/symbols.php)

# Lesson 5. Формы в HTML

## Конспект по HTML форме 📄

### Основные элементы формы

1. **Тег `<form>`**: 
   - Открывает форму для ввода данных.
   - Атрибут `action` указывает маршрут, куда будут отправлены данные.
   - Атрибут `method` определяет способ отправки данных:
     - **POST**: данные отправляются в теле запроса.
     - **GET**: данные передаются в строке запроса в формате `?ключ1=значение1&ключ2=значение2`.

2. **Тег `<input>`**:
   - Создает поле ввода.
   - Атрибут `name` задает имя поля, которое будет использоваться как ключ для отправляемых данных.
   - Атрибут `type` определяет тип поля ввода, например:
     - `text`: текстовое поле.
     - `password`: поле для ввода пароля.
     - `email`: поле для ввода электронной почты.
     - `submit`: кнопка для отправки формы.
   - Атрибут `placeholder` предоставляет подсказку пользователю о том, что нужно ввести.
   - Атрибут `value` задает значение по умолчанию.


### Пример формы

Форма включает два поля ввода:
- Поле для ввода имени пользователя с подсказкой и значением по умолчанию.
- Поле для ввода пароля без значения по умолчанию.

Кнопка "Отправить" предназначена для отправки данных формы.

```html
<form action="" method="POST">
    <div>
        <input type="text" name="username" placeholder="Введите юзернейм" value="Тут уже кто-то напечатал...">
    </div>
    <div>
        <input type="password" name="password" placeholder="Введите пароль">
    </div>
    <div>
        <button type="submit">Отправить</button>
    </div>
</form>
```

### Стилизация формы

Внутри тега `<style>` определены стили для отступов между элементами формы, что делает интерфейс более удобным для пользователя.

```css
form div {
    margin-top: 10px;
}
```

Таким образом, данная форма предоставляет пользователю возможность ввести имя и пароль, а также отправить эти данные на сервер.

## Таблица типов инпутов 📊

| Тип инпута         | Описание                                                                 |
|--------------------|--------------------------------------------------------------------------|
| `text`             | Текстовое поле для ввода обычного текста.                               |
| `email`            | Поле для ввода адреса электронной почты, проверяет формат.              |
| `password`         | Поле для ввода пароля, скрывает введенные символы.                      |
| `number`           | Поле для ввода чисел, может иметь ограничения по диапазону.             |
| `tel`              | Поле для ввода телефонного номера.                                      |
| `url`              | Поле для ввода веб-адреса, проверяет формат.                            |
| `date`             | Поле для выбора даты.                                                   |
| `time`             | Поле для выбора времени.                                                |
| `datetime-local`   | Поле для выбора даты и времени.                                         |
| `month`            | Поле для выбора месяца и года.                                         |
| `week`             | Поле для выбора недели и года.                                          |
| `color`            | Поле для выбора цвета.                                                  |
| `range`            | Ползунок для выбора значения в заданном диапазоне.                      |
| `search`           | Поле для ввода поискового запроса.                                      |
| `checkbox`         | Флажок, который можно отметить или снять.                               |
| `radio`            | Радиокнопка, позволяет выбрать только один вариант из группы.          |
| `file`             | Поле для загрузки файлов.                                               |
| `hidden`           | Скрытое поле, не отображается на странице.                              |
| `image`            | Кнопка отправки в виде изображения.                                     |
| `submit`           | Кнопка для отправки формы.                                             |
| `reset`            | Кнопка для сброса всех полей формы к значениям по умолчанию.           |
| `button`           | Обычная кнопка, может использоваться для выполнения JavaScript функций. |

### Различия между `submit` и `button` типами 🔘

1. **`submit`**:
   - Используется для отправки формы.
   - При нажатии на кнопку происходит отправка данных формы на сервер по указанному маршруту.
   - Если форма содержит обязательные поля, браузер проверяет их перед отправкой.

2. **`button`**:
   - Обычная кнопка, которая не отправляет форму по умолчанию.
   - Может использоваться для выполнения JavaScript функций или других действий на странице.
   - Не выполняет никаких действий без дополнительного кода.

Таким образом, выбор между `submit` и `button` зависит от того, требуется ли отправка формы или выполнение какого-либо действия на странице.

## Экшн и метод атрибуты в HTML формах 📝

Здравствуйте друзья!

Когда мы создаем формы на веб-страницах, два ключевых атрибута, которые мы обязательно должны знать, это `action` и `method`. Эти атрибуты определяют, как и куда будут отправляться данные, введенные пользователем.

### Атрибут `action` 🌍

Атрибут `action` указывает на URL, куда будут отправлены данные формы после нажатия кнопки "Отправить". Это своего рода адрес, на который мы отправляем письмо. Например, если вы заполняете форму регистрации, `action` указывает на серверный скрипт, который будет обрабатывать ваши данные.

Пример использования:
```html
<form action="https://example.com/submit" method="POST">
```

Если `action` не указан, данные будут отправлены на тот же URL, на котором находится форма.

### Атрибут `method` 🔄

Атрибут `method` определяет способ отправки данных. Существует два основных метода:

1. **GET**:
   - Данные отправляются в строке запроса URL.
   - Пример: `https://example.com/submit?username=user&password=pass`
   - Подходит для получения данных, например, при поиске.
   - Ограничение на размер данных (обычно до 2048 символов).
   - Не подходит для передачи конфиденциальной информации, так как данные видны в URL.

2. **POST**:
   - Данные отправляются в теле запроса.
   - Пример: данные не видны в URL.
   - Подходит для отправки больших объемов данных, например, при загрузке файлов.
   - Более безопасный метод для передачи конфиденциальной информации, так как данные не отображаются в адресной строке.

### Что лучше использовать? 🤔

Выбор между `GET` и `POST` зависит от контекста:

- Используйте **GET**, когда:
  - Данные не являются конфиденциальными.
  - Вы хотите, чтобы данные были видны в URL (например, для закладок).
  - Объем данных небольшой.

- Используйте **POST**, когда:
  - Данные конфиденциальные (например, пароли).
  - Объем данных большой.
  - Вы хотите избежать ограничения на длину URL.

### Как посмотреть запросы в инструментах разработчика 🔍

Чтобы увидеть, как отправляются данные формы, можно использовать инструменты разработчика в браузере. Вот как это сделать:

1. Откройте веб-страницу с формой.
2. Нажмите правую кнопку мыши и выберите "Просмотреть код" или "Инспектировать".
3. Перейдите на вкладку "Сеть" (Network).
4. Заполните форму и нажмите кнопку "Отправить".
5. В инструментах разработчика вы увидите запрос, который был отправлен. Вы можете кликнуть на него, чтобы увидеть детали, такие как метод, URL, заголовки и данные.

Таким образом, атрибуты `action` и `method` играют важную роль в отправке данных формы, и понимание их работы поможет вам создавать более эффективные и безопасные веб-приложения.

## Связывание `<label>` и `<input>` в HTML формах 🏷️

Здравствуйте друзья!
Когда мы создаем формы на веб-страницах, важно обеспечить удобство для пользователей. Одним из способов сделать это является связывание элементов `<label>` и `<input>`. Давайте разберемся, как это работает и какие дополнительные настройки могут улучшить взаимодействие с формой.
### Что такое `<label>`? 📜
Тег `<label>` используется для создания метки для элемента формы, такого как поле ввода. Это своего рода указатель, который говорит пользователю, что именно нужно ввести в соответствующее поле. Например, если у вас есть поле для ввода имени, метка может быть "Имя".
### Как связать `<label>` и `<input>`? 🔗
Связывание `<label>` и `<input>` происходит с помощью атрибута `for` в `<label>` и атрибута `id` в `<input>`. Когда метка связана с полем ввода, клик по метке автоматически активирует соответствующее поле. Это особенно полезно на мобильных устройствах, где клик по метке может значительно упростить ввод данных.
Пример связывания:
```html
<label for="username">Имя пользователя:</label>
<input type="text" id="username" name="username" placeholder="Введите ваше имя">
```
В этом примере, когда пользователь кликнет на текст "Имя пользователя:", курсор автоматически переместится в поле ввода.

### Дополнительные настройки для улучшения взаимодействия ⚙️
1. **Использование `placeholder`**:
- Атрибут `placeholder` предоставляет подсказку внутри поля ввода, что именно нужно ввести. Это может быть полезно, но не заменяет метку.
```html
<input type="text" id="username" name="username" placeholder="Введите ваше имя">
```
2. **Стилизация меток**:
- Вы можете стилизовать метки с помощью CSS, чтобы они выглядели более привлекательно и были заметнее.
```css
label {
    font-weight: bold;
    color: #333;
}
```
3. **Обязательные поля**:
- Если поле обязательно для заполнения, можно добавить звездочку рядом с меткой, чтобы указать на это.
```html
<label for="username">Имя пользователя: <span style="color:red">*</span></label>
```