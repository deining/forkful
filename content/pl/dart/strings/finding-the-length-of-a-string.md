---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:54:38.024526-07:00
description: "Jak to zrobi\u0107: Dart umo\u017Cliwia \u0142atwe uzyskanie d\u0142\
  ugo\u015Bci ci\u0105gu znak\xF3w, u\u017Cywaj\u0105c w\u0142a\u015Bciwo\u015Bci\
  \ `length`. Oto podstawowy przyk\u0142ad."
lastmod: '2024-03-13T22:44:35.080996-06:00'
model: gpt-4-0125-preview
summary: "Dart umo\u017Cliwia \u0142atwe uzyskanie d\u0142ugo\u015Bci ci\u0105gu znak\xF3\
  w, u\u017Cywaj\u0105c w\u0142a\u015Bciwo\u015Bci `length`."
title: "Znajdowanie d\u0142ugo\u015Bci \u0142a\u0144cucha znak\xF3w"
weight: 7
---

## Jak to zrobić:
Dart umożliwia łatwe uzyskanie długości ciągu znaków, używając właściwości `length`. Oto podstawowy przykład:

```dart
void main() {
  String myString = "Hello, Dart!";
  print("Długość '\(myString)' wynosi: \(myString.length)");
  // Wynik: Długość 'Hello, Dart!' wynosi: 12
}
```
Ta właściwość liczy liczbę jednostek kodu UTF-16 w ciągu znaków, co odpowiada długości ciągu znaków w większości typowych przypadków użycia.

Do bardziej zniuansowanego przetwarzania tekstu, zwłaszcza z udziałem znaków Unicode spoza Podstawowej Wielojęzycznej Płaszczyzny (BMP), rozważ użycie pakietu `characters` do liczenia klastrów grafemów, które dokładniej reprezentują znaki postrzegane przez użytkownika.

Najpierw dodaj `characters` do swojego `pubspec.yaml`:

```yaml
dependencies:
  characters: ^1.2.0
```

Następnie użyj go w ten sposób:

```dart
import 'package:characters/characters.dart';

void main() {
  String myEmojiString = "👨‍👩‍👧‍👦 family";
  print("Długość '\(myEmojiString)' wynosi: \(myEmojiString.characters.length)");
  // Wynik: Długość '👨‍👩‍👧‍👦 family' wynosi: 8
}
```

W tym przykładzie `myEmojiString.characters.length` podaje nam długość w terminach klastrów grafemów Unicode, co jest bardziej dokładnym odzwierciedleniem dla ciągów znaków zawierających złożone znaki, takie jak emotikony czy połączone znaki diakrytyczne.
