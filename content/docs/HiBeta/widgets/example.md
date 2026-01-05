---
title: Example
tags:
  - Hugo
  - HiBeta
---

该微件用于生成 Markdown 源码和实际渲染的显示效果对照的表格。

## 短代码

### 参数

| 名称        | 类型                         | 必要   | 值                          | 描述                                                |
| ----------- | ---------------------------- | ------ | --------------------------- | --------------------------------------------------- |
| （*Inner*） |                              | **是** |                             |                                                     |
| `title`     | {{<datatype string 字符串>}} | 否     |                             | 表格标题                                            |
| `type`      | {{<datatype string 字符串>}} | 否     | **`row`**（默认）、`col`    | 上下对照 或 左右对照 显示                           |
| `inline`    | {{<datatype bool 布尔>}}     | 否     | `true`、**`false`**（默认） | 使用 `code` 或 `pre` 展示 Markdown 源码             |
| `icon`      | {{<datatype bool 布尔>}}     | 否     | **`true`**（默认）、`false` | 是否显示 Markdown 图标 ({{<icon "xi-markdown">}})   |
| `extended`  | {{<datatype bool 布尔>}}     | 否     | **`true`**（默认）、`false` | 是否使渲染效果栏占满横向空间，只适用于 `type="row"` |
| `class`     | {{<datatype string 字符串>}} | 否     |                             | 额外的 CSS 类                                       |
| `style`     | {{<datatype string 字符串>}} | 否     |                             | 额外的 CSS 样式                                     |

### 用法

1. 将需要对照展示的 Markdown 源码放在闭合的此短代码中间
    {{< example type="col" >}}
{{</* example */>}}
**Bold** *Italic* ~~Strikethrough~~
{{</* /example */>}}
    {{< /example >}}

    {{% notice type="important" simple=true small=true %}}对于需要展示的内容，若**包含短代码**，需要使用 **`/*`** 和 **`*/`** 禁止短代码的直接渲染{{% /notice %}}

    {{< example type="col" >}}
{{</* example */>}}
*Markdown* 图标：{{</*/* icon "xi-markdown" */*/>}}
{{</* /example */>}}
    {{< /example >}}

2. 通过此短代码的自我嵌套，可在一个表格中对照展示多段 Markdown 源码
    {{< example type="col" >}}
{{</* example type="col" inline=true */>}}
    {{</* example */>}}
        **Bold**
    {{</* /example */>}}
    {{</* example */>}}
        *Italic*
    {{</* /example */>}}
    {{</* example */>}}
        ~~Strikethrough~~
    {{</* /example */>}}
{{</* /example */>}}
    {{< /example >}}

### 示例

下面展示基本参数的示例，更多具体示例可通过查看使用了此短代码的页码的源码。

- 参数 `title`
    {{< example type="col" >}}
{{</* example title="标题" */>}}
*Italic*
{{</* /example */>}}
    {{< /example >}}

- 参数 `type`
    {{< example type="col" >}}
{{< example >}}
{{</* example type="row" */>}}
*Italic*
{{</* /example */>}}
{{< /example >}}
{{< example >}}
{{</* example type="col" */>}}
*Italic*
{{</* /example */>}}
{{< /example >}}
    {{< /example >}}

- 参数 `inline`
    {{< example type="col" >}}
{{< example >}}
{{</* example inline=true */>}}
*Italic*
{{</* /example */>}}
{{< /example >}}
{{< example >}}
{{</* example inline=false */>}}
*Italic*
{{</* /example */>}}
{{< /example >}}
    {{< /example >}}

- 参数 `icon`
    {{< example type="col" >}}
{{< example >}}
{{</* example icon=true */>}}
*Italic*
{{</* /example */>}}
{{< /example >}}
{{< example >}}
{{</* example icon=false */>}}
*Italic*
{{</* /example */>}}
{{< /example >}}
    {{< /example >}}

- 参数 `extended`
    {{< example type="row" extended=true >}}
{{</* example type="row" extended=true */>}}
*Italic*
{{</* /example */>}}
{{< /example >}}
    {{< example type="row" extended=false >}}
{{</* example type="row" extended=false */>}}
*Italic*
{{</* /example */>}}
    {{< /example >}}
