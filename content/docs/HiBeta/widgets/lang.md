---
title: 语言标记
tags:
    - Hugo
    - HiBeta
---

该微件用于标示某段文字的语言。

> [!IMPORTANT]
> 该微件通过指定 [HTML lang 属性](https://developer.mozilla.org/docs/Web/HTML/Reference/Global_attributes/lang) 由浏览器实现显示对应的字形。
>
> 如果系统或浏览器过旧、没有对应语言的字体或存在字体兼容性问题，将导致即使指定了语言标签也无法正确显示对应语言的字形！

## 短代码

### 参数

| 名称           | 必要 | 值       | 描述                                                                                           |
| -------------- | ---- | -------- | ---------------------------------------------------------------------------------------------- |
| （位置参数 1） | 是   | 语言标签 | [HTML lang 属性](https://developer.mozilla.org/docs/Web/HTML/Reference/Global_attributes/lang) |
| （位置参数 2） | 是   | 文字     |                                                                                                |

### 示例

{{< example type="col" inline=true >}}
{{< example >}}
{{</* lang "zh-Hans" "骨" */>}}
{{< /example >}}
{{< example >}}
{{</* lang "zh-Hant" "骨" */>}}
{{< /example >}}
{{< example >}}
{{</* lang "ja" "骨" */>}}
{{< /example >}}
{{< example >}}
{{</* lang "ko" "骨" */>}}
{{< /example >}}
{{< /example >}}

| 统一码<br/>Unicode | 中国大陆<br/>简体中文<br/>`zh-Hans` | 中国台湾<br/>繁体中文<br/>`zh-Hant` | 日文<br/>`ja`          | 韩文<br/>`ko`          |
| ------------------ | ----------------------------------- | ----------------------------------- | ---------------------- | ---------------------- |
| `U+534A`           | {{< lang "zh-Hans" "半" >}}         | {{< lang "zh-Hant" "半" >}}         | {{< lang "ja" "半" >}} | {{< lang "ko" "半" >}} |
| `U+5E73`           | {{< lang "zh-Hans" "平" >}}         | {{< lang "zh-Hant" "平" >}}         | {{< lang "ja" "平" >}} | {{< lang "ko" "平" >}} |
| `U+623F`           | {{< lang "zh-Hans" "房" >}}         | {{< lang "zh-Hant" "房" >}}         | {{< lang "ja" "房" >}} | {{< lang "ko" "房" >}} |
| `U+6E2F`           | {{< lang "zh-Hans" "港" >}}         | {{< lang "zh-Hant" "港" >}}         | {{< lang "ja" "港" >}} | {{< lang "ko" "港" >}} |
| `U+76F4`           | {{< lang "zh-Hans" "直" >}}         | {{< lang "zh-Hant" "直" >}}         | {{< lang "ja" "直" >}} | {{< lang "ko" "直" >}} |
| `U+89D2`           | {{< lang "zh-Hans" "角" >}}         | {{< lang "zh-Hant" "角" >}}         | {{< lang "ja" "角" >}} | {{< lang "ko" "角" >}} |
| `U+9001`           | {{< lang "zh-Hans" "送" >}}         | {{< lang "zh-Hant" "送" >}}         | {{< lang "ja" "送" >}} | {{< lang "ko" "送" >}} |
| `U+9AA8`           | {{< lang "zh-Hans" "骨" >}}         | {{< lang "zh-Hant" "骨" >}}         | {{< lang "ja" "骨" >}} | {{< lang "ko" "骨" >}} |
