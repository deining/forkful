---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:55:10.607242-07:00
description: "\u5982\u4F55\u64CD\u4F5C\uFF1A Dart \u901A\u8FC7 `dart:developer` \u5E93\
  \u5305\u542B\u4E86\u4E00\u4E2A\u7B80\u5355\u7684\u65E5\u5FD7\u8BB0\u5F55\u673A\u5236\
  \u3002\u5BF9\u4E8E\u66F4\u590D\u6742\u7684\u65E5\u5FD7\u9700\u6C42\uFF0C\u7A0B\u5E8F\
  \u5458\u901A\u5E38\u4F1A\u8F6C\u5411\u7B2C\u4E09\u65B9\u5E93\uFF0C\u5982 `logger`\
  \ \u548C `log4dart`\u3002"
lastmod: '2024-04-05T22:38:46.589235-06:00'
model: gpt-4-0125-preview
summary: "developer` \u5E93\u5305\u542B\u4E86\u4E00\u4E2A\u7B80\u5355\u7684\u65E5\u5FD7\
  \u8BB0\u5F55\u673A\u5236\u3002\u5BF9\u4E8E\u66F4\u590D\u6742\u7684\u65E5\u5FD7\u9700\
  \u6C42\uFF0C\u7A0B\u5E8F\u5458\u901A\u5E38\u4F1A\u8F6C\u5411\u7B2C\u4E09\u65B9\u5E93\
  \uFF0C\u5982 `logger` \u548C `log4dart`\u3002"
title: "\u65E5\u5FD7\u8BB0\u5F55"
weight: 17
---

## 如何操作：
Dart 通过 `dart:developer` 库包含了一个简单的日志记录机制。对于更复杂的日志需求，程序员通常会转向第三方库，如 `logger` 和 `log4dart`。

### 使用 `dart:developer`
这适合基本的日志记录，特别是在开发期间：

```dart
import 'dart:developer';

void main() {
  log('这是一条调试日志消息。');
}
```

输出：
```
这是一条调试日志消息。
```

### 使用 `logger` 包
对于更全面的解决方案，`logger` 包提供了各种级别的日志记录（例如，信息、警告、错误）并且可以以更易读的方式格式化。

首先，在你的 `pubspec.yaml` 文件中添加 `logger` 依赖：

```yaml
dependencies:
  logger: ^1.0.0
```

然后，按以下方式使用它：

```dart
import 'package:logger/logger.dart';

var logger = Logger();

void main() {
  logger.d("这是一条调试消息");
  logger.w("这是一条警告消息");
  logger.e("这是一条错误消息");
}
```

示例输出可能如下，每种消息类型都以不同的方式格式化，以便于识别：

```
💬 这是一条调试消息
⚠️ 这是一条警告消息
❗️ 这是一条错误消息
```

### 使用 `log4dart` 包
对于需要基于配置的日志记录的应用程序（类似于 Log4j），`log4dart` 提供了一种熟悉的方法。它特别适用于大型应用程序。

确保你在 `pubspec.yaml` 中包含 `log4dart`：

```yaml
dependencies:
  log4dart: ^2.0.0
```

一个简单的使用示例：

```dart
import 'package:log4dart/log4dart.dart';

void main() {
  final logger = LoggerFactory.getLogger("MyApp");
  logger.debug("调试 MyApp");
  logger.info("信息性消息");
}
```

输出：

```
DEBUG: 调试 MyApp
INFO: 信息性消息
```

这些方法中的每一种都提供了不同级别的灵活性和复杂性，从简单的调试消息到满足复杂应用程序需求的全面、可配置的日志记录。
