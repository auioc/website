---
title: Kbd
tags:
  - Hugo
  - HiBeta
---

## 简介

该微件用于展示按键。它可以用来显示单个按键，组合按键或一个按键序列。

## 短代码

### 参数

| 名称         | 必要     | 值                          | 描述             |
| ------------ | -------- | --------------------------- | ---------------- |
| （匿名参数） | 是       | （见下方）                  | 按键             |
| ~~keys~~     | *未实现* | `true`（默认）、~~`false`~~ | 是否使用按键别名 |

### 示例

<div class="flex warp">
{{< example type="col" inline=true >}}
{{< example >}}
{{</* kbd "A+B" */>}}
{{< /example >}}
{{< example >}}
{{</* kbd "Ctrl+B" */>}}
{{< /example >}}
{{< example >}}
{{</* kbd "Ctrl+Alt+Del" */>}}
{{< /example >}}
{{< /example >}}
&nbsp;
{{< example type="col" inline=true >}}
{{< example >}}
{{</* kbd A B C D */>}}
{{< /example >}}
{{< example >}}
{{</* kbd "Alt+" 0 1 7 7 */>}}
{{< /example >}}
{{< example >}}
{{</* kbd "Alt+0" 1 7 7 */>}}
{{< /example >}}
{{< /example >}}
</div>

<div class="flex warp">
{{< example type="col" inline=true >}}
{{< example >}}
{{</* kbd A "+" B */>}}
{{< /example >}}
{{< example >}}
{{</* kbd "A+" "+" "+B" */>}}
{{< /example >}}
{{< example >}}
{{</* kbd "A+" "+" B */>}}
{{< /example >}}
{{< /example >}}
&nbsp;
{{< example type="col" inline=true >}}
{{< example >}}
{{</* kbd "shift+A" */>}}
{{< /example >}}
{{< example >}}
{{</* kbd "windows+D" */>}}
{{< /example >}}
{{< example >}}
{{</* kbd "command+S" */>}}
{{< /example >}}
{{< /example >}}
</div>

## 局部模板

### `widgets\kbd.html`

#### 参数

| 名称    | 类型                                                     | 必要 | 值                                                                                                    | 描述             |
| ------- | -------------------------------------------------------- | ---- | ----------------------------------------------------------------------------------------------------- | ---------------- |
| `keys`  | {{<datatype homoarray>}}{{<datatype string 字符串数组>}} | 是   | 1. 每个元素表示一个/组按键，使用 `+` 分隔符表示组合按键<br>2. 单独的 `+` 表示 {{<kbd "+" >}} 按键本身 | 按键             |
| `alias` | {{<datatype bool 布尔>}}                                 | 否   | `true`、`false`（默认）                                                                               | 是否使用按键别名 |

## 数据

### 按键别名

{{< details summary="kbd_aliases" open=true >}}
{{<dumpdata "kbd_aliases" "yaml">}}
{{< /details >}}
