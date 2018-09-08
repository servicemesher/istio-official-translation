# Reference 的翻译

Reference 部分多数文件是来自源码注释生成的 HTML，也就没有英文版的 Markdown 可以进行翻译，个所以过程和其他部分并不完全一致。下面列出几个需要注意的点。

## Front matter 的写法

### title

来自该页面的头部，如果是专属名词，可不用翻译

### description

原文来自上层索引页面的简介

### weight

权重可以参考英文页面中，该页面所处的位置，例如排序为第 7，则 weight 取值 70

~~~plain
---
title: Fluentd
description: 用于将日志发送给 Fluentd 守护进程的适配器。
weight: 70
---
~~~

## Markdown 文本中的源码

请遵循和其他文件一致的写法

~~~plain
{{< text yaml>}}
hello:
  world
{{< /text >}}
~~~

## 大纲层次

在渲染结果中，查看大纲层级和英文页面是否一致。

## 拼写检查

注意灵活使用反引号来对专属名词进行标记。

