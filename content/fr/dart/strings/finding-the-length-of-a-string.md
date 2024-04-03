---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:54:27.048822-07:00
description: "Comment faire : Dart rend simple l'obtention de la longueur d'une cha\xEE\
  ne gr\xE2ce \xE0 la propri\xE9t\xE9 `length`. Voici un exemple de base ."
lastmod: '2024-03-13T22:44:57.373763-06:00'
model: gpt-4-0125-preview
summary: "Dart rend simple l'obtention de la longueur d'une cha\xEEne gr\xE2ce \xE0\
  \ la propri\xE9t\xE9 `length`."
title: "Trouver la longueur d'une cha\xEEne"
weight: 7
---

## Comment faire :
Dart rend simple l'obtention de la longueur d'une chaîne grâce à la propriété `length`. Voici un exemple de base :

```dart
void main() {
  String myString = "Hello, Dart!";
  print("La longueur de '\(myString)' est : \(myString.length)");
  // Sortie : La longueur de 'Hello, Dart!' est : 12
}
```
Cette propriété compte le nombre d'unités de code UTF-16 dans la chaîne, ce qui correspond à la longueur de la chaîne pour la plupart des cas d'utilisation courants.

Pour un traitement du texte plus nuancé, notamment avec des caractères Unicode situés hors du Plan Multilingue de Base (BMP), envisagez d'utiliser le package `characters` pour compter les grappes de graphèmes, ce qui représente plus fidèlement les caractères perçus par l'utilisateur.

D'abord, ajoutez `characters` à votre fichier `pubspec.yaml` :

```yaml
dependencies:
  characters: ^1.2.0
```

Ensuite, utilisez-le comme ceci :

```dart
import 'package:characters/characters.dart';

void main() {
  String myEmojiString = "👨‍👩‍👧‍👦 famille";
  print("La longueur de '\(myEmojiString)' est : \(myEmojiString.characters.length)");
  // Sortie : La longueur de '👨‍👩‍👧‍👦 famille' est : 8
}
```

Dans cet exemple, `myEmojiString.characters.length` nous donne la longueur en termes de grappes de graphèmes Unicode, ce qui est une représentation plus précise pour les chaînes contenant des caractères complexes, comme les émojis ou les marques de caractères combinés.
