Auto grow and save area
===================

Поле ввода, высота которого автоматически подстраивается, чтобы вместить введенный текст. Помимо этого, по щелчку может превращаться в обычный текст и обрабатывать веденную информацию пользовательской функцией.

**Демонстрация**
http://tamtakoe.ru/autoGrowAndSaveArea/

**Парметры**
<pre>@editor boolean             - Поле ввода изначально показано (true) или скрыто (false)
@toggle boolean or function - Поле ввода статично (false) либо показывается/превращается в обычный текст
                              при получении/потере фокуса (true).
                              При потере фокуса может быть выполнена пользовательская функция,
                              которой передается идентификатор поля и его значение (function(event, value))</pre>

**Пример подключения в режиме автоподстраивания под текст**
<pre>$('textarea').autoGS()</pre>

**В режиме автоподстраивания и сохранения**
<pre>$('textarea').autoGS({
    'editor': false,
    'toggle': function(e, value) {
        $.ajax({
            'url': 'save.php',
            'data': {'id': e.target.id, 'title': value}
        })
    }
})</pre>

**Стили**

Ненавязчиво подсказать, что текст редактируется, можно таким стилем
<pre>.autogrow-textarea-mirror {
    cursor: text;
}</pre>
либо таким, где на поле делается больший акцент
<pre>.autogrow-textarea-mirror {
    cursor: pointer;
}
.autogrow-textarea-mirror:hover {
    background-color: rgba(0, 136, 204, 0.1);
    border-radius: 5px;
}</pre>
