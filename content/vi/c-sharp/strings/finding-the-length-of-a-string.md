---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:00:46.937119-07:00
description: "C\xE1ch th\u1EF1c hi\u1EC7n: Trong C#, thu\u1ED9c t\xEDnh `string.Length`\
  \ cung c\u1EA5p s\u1ED1 l\u01B0\u1EE3ng k\xFD t\u1EF1 c\xF3 trong m\u1ED9t chu\u1ED7\
  i. D\u01B0\u1EDBi \u0111\xE2y l\xE0 c\xE1ch s\u1EED d\u1EE5ng n\xF3."
lastmod: '2024-03-13T22:44:36.645344-06:00'
model: gpt-4-0125-preview
summary: "Trong C#, thu\u1ED9c t\xEDnh `string.Length` cung c\u1EA5p s\u1ED1 l\u01B0\
  \u1EE3ng k\xFD t\u1EF1 c\xF3 trong m\u1ED9t chu\u1ED7i."
title: "T\xECm chi\u1EC1u d\xE0i c\u1EE7a m\u1ED9t chu\u1ED7i k\xFD t\u1EF1"
weight: 7
---

## Cách thực hiện:
Trong C#, thuộc tính `string.Length` cung cấp số lượng ký tự có trong một chuỗi. Dưới đây là cách sử dụng nó:

```C#
using System;

class Program
{
    static void Main()
    {
        string example = "Hello, World!";
        Console.WriteLine(example.Length); // Output: 13
    }
}
```

Dễ dàng, phải không? Nhưng hãy nhớ, nó đếm *ký tự*, không phải byte. Với các emoji hoặc ký tự đặc biệt, mọi thứ có thể trở nên phức tạp hơn. Chúng ta sẽ nói thêm về điều này sau.

## Sâu hơn nữa
Theo lịch sử, việc tìm độ dài của một chuỗi đã gắn liền với quản lý và thao tác bộ nhớ trong lập trình. Do C# là một ngôn ngữ cấp cao, nó đã trừu tượng hóa công việc cấp thấp đó đi. Tuy nhiên, biết được điều gì đang diễn ra bên dưới cũng rất tốt.

Có phương pháp khác không? Chắc chắn rồi! Bạn có thể thấy `example.ToCharArray().Length` được sử dụng ngoài kia, nhưng nó chỉ thực hiện công việc nặng nhọc để đạt được kết quả giống nhau.

Giờ đây, về những ký tự phức tạp đó. Thuộc tính `Length` của C# đếm số lượng đối tượng `char` trong chuỗi, mỗi đối tượng đại diện cho một đơn vị mã UTF-16. Điều đó ổn cho đến khi bạn gặp *cặp thay thế* – những ký tự như emoji cần hai đối tượng `char`. Dưới đây là vấn đề: `Length` đếm chúng như là hai. Đúng vậy.

Để có số lượng chính xác của *ký tự trực quan* hay *nhóm grapheme*, bạn sẽ cần lớp `StringInfo` từ System.Globalization:

```C#
using System;
using System.Globalization;

class Program
{
    static void Main()
    {
        string example = "👍"; // Emoji cử chỉ ok

        Console.WriteLine(example.Length); // Output: 2 <- Do cặp thay thế!
        Console.WriteLine(new StringInfo(example).LengthInTextElements); // Output: 1
    }
}
```

Bạn đã hiểu sự khác biệt chưa? Đây không chỉ là lý thuyết; nó có thể ảnh hưởng đến xử lý văn bản một cách có ý nghĩa.

## Xem thêm
Khám phá thêm với các nguồn này:

- [Tài liệu chính thức của Microsoft về chuỗi](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/)
- [Hiểu biết về Unicode và UTF-16](https://unicodebook.readthedocs.io/unicode_encodings.html)
- [Tài liệu về lớp StringInfo](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.stringinfo?view=net-6.0)

Hiểu biết về chuỗi, xử lý chúng một cách khôn ngoan, và viết mã đếm - theo mọi nghĩa.
