---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:55:11.838681-07:00
description: "L\xE0m th\u1EBF n\xE0o: Dart bao g\u1ED3m m\u1ED9t c\u01A1 ch\u1EBF\
  \ ghi nh\u1EADt k\xFD \u0111\u01A1n gi\u1EA3n th\xF4ng qua th\u01B0 vi\u1EC7n `dart:developer`.\
  \ \u0110\u1ED1i v\u1EDBi nhu c\u1EA7u ghi nh\u1EADt k\xFD ph\u1EE9c t\u1EA1p h\u01A1\
  n, l\u1EADp tr\xECnh vi\xEAn\u2026"
lastmod: '2024-03-13T22:44:36.271722-06:00'
model: gpt-4-0125-preview
summary: "Dart bao g\u1ED3m m\u1ED9t c\u01A1 ch\u1EBF ghi nh\u1EADt k\xFD \u0111\u01A1\
  n gi\u1EA3n th\xF4ng qua th\u01B0 vi\u1EC7n `dart:developer`."
title: "Ghi L\u1EA1i"
weight: 17
---

## Làm thế nào:
Dart bao gồm một cơ chế ghi nhật ký đơn giản thông qua thư viện `dart:developer`. Đối với nhu cầu ghi nhật ký phức tạp hơn, lập trình viên thường chuyển sang sử dụng các thư viện của bên thứ ba như `logger` và `log4dart`.

### Sử dụng `dart:developer`
Phù hợp cho việc ghi nhật ký cơ bản, đặc biệt là trong quá trình phát triển:

```dart
import 'dart:developer';

void main() {
  log('Đây là một thông điệp ghi nhật ký để gỡ lỗi.');
}
```

Kết quả:
```
Đây là một thông điệp ghi nhật ký để gỡ lỗi.
```

### Sử dụng gói `logger`
Để có một giải pháp toàn diện hơn, gói `logger` cung cấp các mức độ ghi nhật ký khác nhau (ví dụ, thông tin, cảnh báo, lỗi) và có thể được định dạng một cách dễ đọc hơn.

Đầu tiên, thêm sự phụ thuộc `logger` vào tệp `pubspec.yaml` của bạn:

```yaml
dependencies:
  logger: ^1.0.0
```

Sau đó, sử dụng như sau:

```dart
import 'package:logger/logger.dart';

var logger = Logger();

void main() {
  logger.d("Đây là một thông điệp gỡ lỗi");
  logger.w("Đây là một thông điệp cảnh báo");
  logger.e("Đây là một thông điệp lỗi");
}
```

Một mẫu kết quả có thể trông như sau, với mỗi kiểu thông điệp được định dạng khác nhau để dễ nhận biết:

```
💬 Đây là một thông điệp gỡ lỗi
⚠️ Đây là một thông điệp cảnh báo
❗️ Đây là một thông điệp lỗi
```

### Sử dụng gói `log4dart`
Đối với các ứng dụng yêu cầu ghi nhật ký dựa trên cấu hình (tương tự như Log4j), `log4dart` cung cấp một phương pháp quen thuộc. Nó đặc biệt hữu ích cho các ứng dụng quy mô lớn.

Hãy đảm bảo bạn đã bao gồm `log4dart` trong `pubspec.yaml` của mình:

```yaml
dependencies:
  log4dart: ^2.0.0
```

Một ví dụ sử dụng đơn giản:

```dart
import 'package:log4dart/log4dart.dart';

void main() {
  final logger = LoggerFactory.getLogger("MyApp");
  logger.debug("Gỡ lỗi MyApp");
  logger.info("Thông điệp thông tin");
}
```

Kết quả:

```
DEBUG: Gỡ lỗi MyApp
INFO: Thông điệp thông tin
```

Mỗi phương pháp này cung cấp một mức độ linh hoạt và phức tạp khác nhau, từ thông điệp gỡ lỗi đơn giản đến ghi nhật ký toàn diện, có thể cấu hình đáp ứng nhu cầu của các ứng dụng phức tạp.
