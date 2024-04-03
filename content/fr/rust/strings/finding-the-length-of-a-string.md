---
date: 2024-01-20 17:48:06.421607-07:00
description: "How to: Rust utilise la m\xE9thode `.len()` pour obtenir la taille d'une\
  \ cha\xEEne de caract\xE8res en bytes. Voici comment \xE7a marche ."
lastmod: '2024-03-13T22:44:57.472689-06:00'
model: gpt-4-1106-preview
summary: "Rust utilise la m\xE9thode `.len()` pour obtenir la taille d'une cha\xEE\
  ne de caract\xE8res en bytes."
title: "Trouver la longueur d'une cha\xEEne de caract\xE8res"
weight: 7
---

## How to:
Rust utilise la méthode `.len()` pour obtenir la taille d'une chaîne de caractères en bytes. Voici comment ça marche :

```rust
fn main() {
    let hello = "Bonjour";
    println!("La longueur de '{}' est {}.", hello, hello.len());
    
    let emoji = "😊";
    println!("La longueur de '{}' est {}.", emoji, emoji.len());
}
```

Output:
```
La longueur de 'Bonjour' est 7.
La longueur de '😊' est 4.
```

## Deep Dive
Historiquement, mesurer la longueur d'une chaîne est simple avec du texte ASCII, car chaque caractère est représenté par un seul byte. Avec l'introduction d'UTF-8 et les caractères à plusieurs bytes, c'est devenu un peu plus compliqué. Rust gère les chaînes en UTF-8 par défaut, alors `.len()` renvoie le nombre de bytes, pas forcément de caractères visibles. Autres options incluent `.chars().count()` pour le nombre de caractères Unicode, et `.graphemes(true).count()` avec la crate `unicode-segmentation` pour les graphèmes affichés.

```rust
extern crate unicode_segmentation;
use unicode_segmentation::UnicodeSegmentation;

fn main() {
    let hello = "Bonjour";
    let emoji = "😊";

    println!("Nombre de caractères Unicode dans '{}' : {}", hello, hello.chars().count());
    println!("Nombre de caractères Unicode dans '{}' : {}", emoji, emoji.chars().count());
    
    println!("Nombre de graphèmes dans '{}' : {}", emoji, emoji.graphemes(true).count());
}
```

Output:
```
Nombre de caractères Unicode dans 'Bonjour' : 7
Nombre de caractères Unicode dans '😊' : 1
Nombre de graphèmes dans '😊' : 1
```

## See Also
Pour plus d'informations, vous pouvez consulter la documentation sur les chaînes en Rust :
- Rust String Docs : [https://doc.rust-lang.org/std/string/](https://doc.rust-lang.org/std/string/)
- UTF-8 et traitement de texte : [https://unicode.org/](https://unicode.org/)
