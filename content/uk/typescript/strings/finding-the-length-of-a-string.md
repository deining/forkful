---
date: 2024-01-20 17:48:34.564337-07:00
description: "\u042F\u043A \u0446\u0435 \u0437\u0440\u043E\u0431\u0438\u0442\u0438\
  : \u0414\u043B\u044F \u043E\u0442\u0440\u0438\u043C\u0430\u043D\u043D\u044F \u0434\
  \u043E\u0432\u0436\u0438\u043D\u0438 \u0440\u044F\u0434\u043A\u0430 \u0432 TypeScript,\
  \ \u0432\u0438\u043A\u043E\u0440\u0438\u0441\u0442\u043E\u0432\u0443\u0439\u0442\
  \u0435 \u0432\u043B\u0430\u0441\u0442\u0438\u0432\u0456\u0441\u0442\u044C `length`."
lastmod: '2024-03-13T22:44:48.854473-06:00'
model: gpt-4-1106-preview
summary: "\u0414\u043B\u044F \u043E\u0442\u0440\u0438\u043C\u0430\u043D\u043D\u044F\
  \ \u0434\u043E\u0432\u0436\u0438\u043D\u0438 \u0440\u044F\u0434\u043A\u0430 \u0432\
  \ TypeScript, \u0432\u0438\u043A\u043E\u0440\u0438\u0441\u0442\u043E\u0432\u0443\
  \u0439\u0442\u0435 \u0432\u043B\u0430\u0441\u0442\u0438\u0432\u0456\u0441\u0442\u044C\
  \ `length`."
title: "\u0412\u0438\u0437\u043D\u0430\u0447\u0435\u043D\u043D\u044F \u0434\u043E\u0432\
  \u0436\u0438\u043D\u0438 \u0440\u044F\u0434\u043A\u0430"
weight: 7
---

## Як це зробити:
Для отримання довжини рядка в TypeScript, використовуйте властивість `length`.

```typescript
let message: string = "Вітаю";
console.log(message.length); // Виводить: 6
```

Якщо рядок порожній, `length` поверне 0.

```typescript
let emptyMessage: string = "";
console.log(emptyMessage.length); // Виводить: 0
```

## Поглиблено:
Довжина рядка широко використовується із часів створення перших мов програмування. У JavaScript та TypeScript, `length` є властивістю прототипу `String`, і вона моментально повертає кількість UTF-16 кодових одиниць у рядку, що не завжди співпадає з кількістю видимих символів у рядку з емоджі або іншими особливими символами.

Як альтернатива, для отримання довжини, що враховує Unicode, можна використовувати `Array.from()` або spread оператор:

```typescript
let emojiMessage: string = "Привіт 👋";
console.log(Array.from(emojiMessage).length); // Виводить: 8
```

Але зауважте, це може бути повільніше ніж просте використання `length`.

## Дивіться також:
- MDN документація про String.length: [MDN String.length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
- Стаття про роботу з Unicode у JavaScript: [Handling Unicode](https://flaviocopes.com/javascript-unicode/)
- Типізація рядків у TypeScript: [TypeScript String](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)
