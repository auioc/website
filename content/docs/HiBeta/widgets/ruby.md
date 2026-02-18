---
title: 注音和字符注释
tags:
  - Hugo
  - HiBeta
---

## 简介

该微件使用 [HTML`<ruby>`元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Reference/Elements/ruby)来展示注音或字符注释。

## Markdown 扩展语法

{{< example unescape=true type="col" inline=true >}}
{{< example >}}
[汉]{;^}(hàn)[字]{;^}(zì)
{{< /example >}}
{{< example >}}
[漢]{;^}(ㄏㄢˋ)[字]{;^}(ㄗˋ)
{{< /example >}}
{{< example >}}
[漢]{;^}(かん)[字]{;^}(じ)
{{< /example >}}
{{< example >}}
[漢]{;^}(한)[字]{;^}(자)
{{< /example >}}
{{< /example >}}

{{< example unescape=true type="col" inline=true >}}
[**汉**]{;^}(hàn)[字]{;^}(*zì*)
{{< /example >}}

## 短代码

### 参数

| 名称         | 必要              | 值                                    | 描述 |
| ------------ | ----------------- | ------------------------------------- | ---- |
| （匿名参数） | 是（有且只有2个） | 第1个：原文<br/>第2个：注音或字符注释 |      |

### 示例

{{< example unescape=true type="col" inline=true >}}
{{< example >}}
{{</* ruby "汉" "hàn" */>}}
{{< /example >}}
{{< example >}}
{{</* ruby "漢" "ㄏㄢˋ" */>}}
{{< /example >}}
{{< example >}}
{{</* ruby "漢" "かん" */>}}
{{< /example >}}
{{< example >}}
{{</* ruby "漢" "한" */>}}
{{< /example >}}
{{< /example >}}
