---
title:                "Fish Shell: 编写文本文件"
simple_title:         "编写文本文件"
programming_language: "Fish Shell"
category:             "Fish Shell"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/fish-shell/writing-a-text-file.md"
---

{{< edit_this_page >}}

## 为什么

你可能听说过 Fish Shell 编程，但你可能不太确定它为什么如此流行。简而言之，Fish Shell 是一种简单而强大的命令行工具，它允许用户以更有效和简洁的方式来操作计算机。在这篇博客文章中，我们将介绍如何使用 Fish Shell 编程来写入文本文件。

## 如何

首先，让我们创建一个新的文本文件。打开你喜欢的文本编辑器，并输入以下内容：

```Fish Shell
echo Hello, world! > hello.txt
```

在这个例子中，我们使用了 Fish Shell 的 `echo` 命令来输出 "Hello, world!" 这句话，并将其重定向到 `hello.txt` 这个文件中。现在，如果你查看 `hello.txt` 这个文件，你将会看到里面包含着我们刚刚输入的内容。

接下来，我们来看一下如何使用 Fish Shell 的 `cat` 命令来将多行文本写入文件：

```Fish Shell
cat > multi-line.txt
This is the first line.
This is the second line.
This is the third line.
```

上面的代码将会打开一个交互式会话，让你输入多行文本，并将其保存到 `multi-line.txt` 这个文件中。输入完成后，按下 `Ctrl-D` 键来结束会话。现在，打开 `multi-line.txt` 这个文件，你将会看到三行文本分别对应着我们刚刚输入的内容。

## 深入了解

当我们使用 Fish Shell 来写入文本文件时，它将会使用默认的文本编辑器来打开文件。你可以通过设置 `EDITOR` 环境变量来更改默认的文本编辑器。例如，如果你想要使用 Vim 编辑器来打开文件，则可以将下面的代码添加到你的 Fish Shell 配置文件 `config.fish` 中：

```
set -x EDITOR vim
```

另外，你也可以添加自定义的函数来帮助你更轻松地写入文件。例如，下面的代码将会创建一个名为 `write` 的函数，它将会接受文件名和文本作为参数，并将文本写入指定的文件中：

```Fish Shell
function write
    set filename $argv[1]
    set text $argv[2]
    echo $text > $filename
end
```

使用这个自定义函数，我们可以更轻松地写入文件，如下所示：

```Fish Shell
write hello.txt "Hello again, world!"
```

现在，打开 `hello.txt` 文件，你将会看到里面包含着我们刚刚输入的文本。

## 另请参阅

这篇博客文章介绍了 Fish Shell 编程中写入文本文件的基本方法，但这只是冰山一角。如果你想要更深入地了解 Fish Shell，可以参阅以下链接：

- [官方文档](https://fishshell.com/docs/current/index.html)
- [使用 Fish Shell 的 10 个技巧](https://dev.to/jkovacs/10-useful-fish-shell-commands-3fbg)
- [Fish Shell 使用指南](https://medium.com/@andreasmekics/fish-shell-setup-guide-287782cbeee3)

Happy coding! 🐟