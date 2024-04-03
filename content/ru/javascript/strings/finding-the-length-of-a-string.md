---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 23:57:55.152210-07:00
description: "\u041A\u0430\u043A: JavaScript \u0434\u0435\u043B\u0430\u0435\u0442\
  \ \u044D\u0442\u043E \u043F\u0440\u043E\u0441\u0442\u043E \u0441 \u043F\u043E\u043C\
  \u043E\u0449\u044C\u044E \u0441\u0432\u043E\u0439\u0441\u0442\u0432\u0430 `.length`."
lastmod: '2024-03-13T22:44:45.743799-06:00'
model: gpt-4-0125-preview
summary: "JavaScript \u0434\u0435\u043B\u0430\u0435\u0442 \u044D\u0442\u043E \u043F\
  \u0440\u043E\u0441\u0442\u043E \u0441 \u043F\u043E\u043C\u043E\u0449\u044C\u044E\
  \ \u0441\u0432\u043E\u0439\u0441\u0442\u0432\u0430 `.length`."
title: "\u041F\u043E\u0438\u0441\u043A \u0434\u043B\u0438\u043D\u044B \u0441\u0442\
  \u0440\u043E\u043A\u0438"
weight: 7
---

## Как:
JavaScript делает это просто с помощью свойства `.length`.

```javascript
let greeting = 'Привет, мир!';
console.log(greeting.length); // Вывод: 13
```

Пустая строка равна нулю:

```javascript
let empty = '';
console.log(empty.length); // Вывод: 0
```

Даже пробелы считаются:

```javascript
let spaces = '   ';
console.log(spaces.length); // Вывод: 3
```

## Углубляемся
Свойство `.length` существует с самых ранних дней JS. Это быстро, так как это не функция, а свойство экземпляра, которое хранится вместе с объектом строки.

Существуют альтернативы, такие как ручной подсчет каждого символа, но это как пользоваться лестницей вместо лифта – используйте только когда необходимо.

JavaScript рассматривает строки как неизменяемые, что означает, что `.length` не изменится, если вы не присвоите переменной новую строку. Длина вычисляется при создании строки.

Что касается реализации, помните про Unicode. Некоторые символы (например, эмодзи или алфавиты некоторых языков) могут быть представлены двумя или более кодовыми единицами в кодировке UTF-16 JavaScript:

```javascript
let smiley = '😊';
console.log(smiley.length); // Вывод: 2
```

Даже если это выглядит как один символ, некоторые могут считаться за две "длины" из-за того, как они закодированы. Просто что-то, что стоит помнить, если вы работаете с разнообразными наборами символов!

## Смотрите также
- [MDN Web Docs - String.length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
- [Unicode и строки JavaScript](https://mathiasbynens.be/notes/javascript-unicode)
- [Строки и кодировки символов JavaScript](https://flaviocopes.com/javascript-unicode/)
