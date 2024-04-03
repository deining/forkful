---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 23:58:30.252931-07:00
description: "\u041A\u0430\u043A \u044D\u0442\u043E \u0441\u0434\u0435\u043B\u0430\
  \u0442\u044C: \u0412 TypeScript \u0434\u043B\u0438\u043D\u0443 \u0441\u0442\u0440\
  \u043E\u043A\u0438 \u043C\u043E\u0436\u043D\u043E \u0443\u0437\u043D\u0430\u0442\
  \u044C, \u0438\u0441\u043F\u043E\u043B\u044C\u0437\u0443\u044F \u0441\u0432\u043E\
  \u0439\u0441\u0442\u0432\u043E `.length`. \u0412\u043E\u0442 \u0431\u044B\u0441\u0442\
  \u0440\u044B\u0439 \u043F\u0440\u0438\u043C\u0435\u0440."
lastmod: '2024-03-13T22:44:44.572739-06:00'
model: gpt-4-0125-preview
summary: "\u0412 TypeScript \u0434\u043B\u0438\u043D\u0443 \u0441\u0442\u0440\u043E\
  \u043A\u0438 \u043C\u043E\u0436\u043D\u043E \u0443\u0437\u043D\u0430\u0442\u044C\
  , \u0438\u0441\u043F\u043E\u043B\u044C\u0437\u0443\u044F \u0441\u0432\u043E\u0439\
  \u0441\u0442\u0432\u043E `.length`."
title: "\u041F\u043E\u0438\u0441\u043A \u0434\u043B\u0438\u043D\u044B \u0441\u0442\
  \u0440\u043E\u043A\u0438"
weight: 7
---

## Как это сделать:
В TypeScript длину строки можно узнать, используя свойство `.length`. Вот быстрый пример:

```typescript
let greeting: string = "Привет, TypeScript!";
console.log(greeting.length); // Вывод: 18
```

Этот код объявляет строковую переменную с именем `greeting` и затем выводит её длину в консоль.

## Глубокое погружение
Свойство `.length` унаследовано от JavaScript, предшественника TypeScript. Это простой и универсально поддерживаемый способ получения размера строки.

Существуют альтернативы, но они обычно усложняют задачу. Например, можно преобразовать строку в массив и подсчитать элементы:

```typescript
let greetingArray: string[] = Array.from(greeting);
console.log(greetingArray.length); // Вывод: 18
```

Но зачем идти длинным путем? Свойство `.length` эффективно, потому что строки хранятся в виде массивов символов под капотом, так что информация о длине немедленно доступна.

Теперь, допустим, вы работаете со строками на разных языках. Вы можете столкнуться с проблемами со специальными символами. Базовый подход с `.length` подсчитывает единицы кода UTF-16, что может быть проблематично для символов, требующих две единицы кода, известных как суррогатные пары. В таких случаях свойство `.length` может не дать вам подсчета фактических символов, также известных как кодовые точки.

Вот как вы можете обрабатывать строки с суррогатными парами:

```typescript
function countCodePoints(str: string): number {
    return Array.from(str).length;
}

let fancyGreeting: string = "Привет, 🌍!";
console.log(countCodePoints(fancyGreeting)); // Вывод: 9
```

Эта функция занимается тонкостями кодирования строк, чтобы обеспечить, чтобы каждый символ, независимо от того, состоит он из одной или двух единиц кода, был правильно подсчитан.

## Смотрите также
- Руководство по TypeScript о строках: [Руководство по TypeScript](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#strings)
- MDN Web Docs о свойстве длины строки: [String.prototype.length](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/String/length)
- Unicode и JavaScript: [У JavaScript есть проблема с Unicode - Матиас Биненс](https://mathiasbynens.be/notes/javascript-unicode)
