---
title: "正则表达式元字符"
categories: [ "计算机技术","正则"]
tags: [  ]
draft: true
slug: "584"
date: "2021-10-12 18:20:00"
---

在编写处理字符串的程序或网页时，经常会有查找符合某些复杂规则的字符串的需要。正则表达式就是用于描述这些规则的工具。换句话说，正则表达式就是记录文本规则的代码。

下面列出 iBM 帮助文档列出的 perl 正则表达式元字符

| 元字符    | 描述                                                         |
| --------- | ------------------------------------------------------------ |
| \         | 将下一个字符标记为特殊字符或字面值。例如， n 匹配字符 n ，而 \n 匹配 换行符。序列 \\ 匹配 \，而 \( 匹配 ( 。 |
| ^         | 匹配输入的开始部分。                                         |
| $         | 匹配输入的结束部分。                                         |
| *         | 零次 或 更多次 匹配前面的字符。例如， zo*  匹配 z 或 zoo 。  |
| +         | 一次 或 更多次 匹配前面的字符。例如， zo+  匹配 zoo ，但是 不匹配 z 。 |
| ?         | 零次 或 一次 匹配前面的字符。例如， a?ve? 匹配 never 中的 ve 。 |
| .         | 匹配任何 单个字符，但换行符除外。                            |
| (pattern) | 匹配模式并记住匹配项。通过使用以下代码，匹配的子串可以检索自生成的匹配项集合： Item [0]...[n] 。要匹配圆括号字符 ( ) ，请使用 \( 或 \) 。 |
| x\\|y      | 匹配 x 或 y 。 例如， z\|wood  匹配 z  或 wood 。 (z\|w)oo  匹配 zoo 或 wood 。 |
| {n}       | n 是一个非负整数。精确匹配 n 次。例如， o{2} 不匹配 Bob 中的 o，但是匹配 foooood 中的 前两个 o 。 |
| {n,}      | 在此表达式中， n  是一个非负整数。至少 n 次匹配前面的字符。例如， o{2,} 不匹配 Bob 中的 o ，但是匹配 foooood 中的所有 o 。 o{1,}  表达式等效于 o+ ， o{0,} 等效于 o* 。 |
| {n,m}     | m 和 n 变量是非负整数。至少 n 次且至多 m 次匹配前面的字符。例如， o{1,3} 匹配 fooooood 中的 前三个 o 。 o{0,1}  表达式等效于 o? 。 |
| [xyz]     | 一个字符集。匹配任意一个包含的字符。例如， [abc] 匹配 plain  中的 a 。 |
| [^xyz]    | 一个否定字符集。匹配任何未包含的字符。例如， [^abc] 匹配 plain 中的 p 。 |
| [a-z]     | 字符范围。匹配指定范围中的任何字符。例如， [a-z]  匹配英语字母中的任何小写的字母字符。 |
| [^m-z]    | 一个否定字符范围。匹配未在指定范围中的任何字符。例如， [m-z] 匹配未在范围 m 到 z 之间的任何字符。 |
| \A        | 仅匹配字符串的开头。                                         |
| \b        | 匹配 某个单词 边界，即，某个单词和空格之间的位置。例如， er\b 匹配 never 中的 er ，但是不匹配 verb 中的 er 。 |
| \B        | 匹配 非单词 边界。 ea*r\B 表达式匹配 never early 中的 ear 。 |
| \d        | 匹配数字字符。                                               |
| \D        | 匹配非数字字符。                                             |
| \f        | 匹配换页字符。                                               |
| \n        | 匹配换行符。                                                 |
| \r        | 匹配回车字符。                                               |
| \s        | 匹配任何空格，包括空白、制表符、换页字符等等。               |
| \S        | 匹配任何 非空格 字符。                                       |
| \t        | 匹配 跳进 字符。                                             |
| \v        | 匹配 垂直跳进字符。                                          |
| \w        | 匹配任何 单词字符，包括下划线。此表达式等效于 [A-Za-z0-9_] 。 |
| \W        | 匹配任何 非单词字符。此表达式等效于 [^A-Za-z0-9__] 。        |
| \z        | 仅匹配字符串的结尾。                                         |
| \Z        | 仅匹配字符串的结尾，或者结尾的换行符之前。                   |

## 参考文献

- [正则表达式中的元字符](https://www.ibm.com/docs/zh/rational-clearquest/9.0.0?topic=tags-meta-characters-in-regular-expressions)
- [正则表达式30分钟入门教程](https://deerchao.cn/tutorials/regex/regex.htm)