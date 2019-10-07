---
id: 587d7fb2367417b2b2512bf6
title: Get Query Parameter Input from the Client
challengeType: 2
forumTopicId: 301512
localeTitle: Получить ввод параметров запроса от клиента
---

## Description
<section id='description'>
Другим распространенным способом получения ввода от клиента является кодирование данных после пути маршрута с использованием строки запроса. Строка запроса ограничена знаком вопроса (?) И включает пары поле = значение. Каждая пара отделяется амперсандом (&amp;). Express может анализировать данные из строки запроса и заполнять объект <code>req.query</code> . Некоторые символы не могут быть в URL, они должны быть закодированы в <a href='https://en.wikipedia.org/wiki/Percent-encoding' target='_blank'>другом формате,</a> прежде чем вы сможете отправить их. Если вы используете API из JavaScript, вы можете использовать специальные методы для кодирования / декодирования этих символов. 
<blockquote>route_path: '/library'<br>actual_request_URL: '/library?userId=546&bookId=6754' <br>req.query: {userId: '546', bookId: '6754'}</blockquote> 
Создайте конечную точку API, смонтированную в <code>GET /name</code> . Ответить с JSON-документом, взяв структуру <code>{ name: 'firstname lastname'}</code> . Параметры имени и фамилии должны быть закодированы в строке запроса, например <code>?first=firstname&amp;last=lastname</code> . 
СОВЕТ: В следующем упражнении мы собираемся получить данные из запроса POST по тому же пути <code>/name</code> маршрута. Если вы хотите, вы можете использовать метод <code>app.route(path).get(handler).post(handler)</code> . Этот синтаксис позволяет связывать разные обработчики глаголов на одном и том же пути маршрута. Вы можете сэкономить немного времени на ввод текста и получить более чистый код.
</section>

## Инструкции
<section id='instructions'>
Создайте конечную точку API, смонтированную в <code>GET /name</code>. Ответьте документом JSON, взяв структуру <code>{ name: 'firstname lastname'}</code>. Имя и фамилия параметры должны быть закодированы в строке запроса, например <code>?first=firstname&last=lastname</code>.
<strong>Примечание:</strong> Примечание: в следующем упражнении вы будете получать данные из запроса POST, по тому же пути маршрута <code>/name</code>. Если вы хотите, вы можете использовать метод <code>app.route(path).get(handler).post(handler)</code>. Этот синтаксис позволяет связывать разные обработчики глаголов на одном и том же пути. Вы можете сэкономить немного времени на ввод текста и получить более чистый код.
</section>

## Tests
<section id='tests'>

```yml
tests:
  - text: 'Test 1 : Your API endpoint should respond with the correct name'
    testString: 'getUserInput => $.get(getUserInput(''url'') + ''/name?first=Mick&last=Jagger'').then(data => { assert.equal(data.name, ''Mick Jagger'', ''Test 1: "GET /name" route does not behave as expected'') }, xhr => { throw new Error(xhr.responseText); })'
  - text: 'Test 2 : Your APi endpoint should respond with the correct name'
    testString: 'getUserInput => $.get(getUserInput(''url'') + ''/name?last=Richards&first=Keith'').then(data => { assert.equal(data.name, ''Keith Richards'', ''Test 2: "GET /name" route does not behave as expected'') }, xhr => { throw new Error(xhr.responseText); })'

```

</section>
