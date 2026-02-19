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
[**汉**]{;^}(hàn)[字]{;^}(_zì_)
{{< /example >}}
{{< /example >}}

{{< notice type="tip" render=false >}}
如下所见，繁体中文汉字、日文汉字、韩文汉字并非对应语言的正确字形：
{{< example unescape=true type="col" inline=true >}}
{{< example >}}
[骨]{;^}(ㄍㄨˇ)
{{< /example >}}
{{< example >}}
[骨]{;^}(ほね)
{{< /example >}}
{{< example >}}
[骨]{;^}(골)
{{< /example >}}
{{< /example >}}
如果需要指定语言，请使用<b>短代码</b>。
{{< /notice >}}

## 短代码

### 参数

<table>
<thead>
  <tr><th>名称</th><th>必要</th><th>值</th><th>描述</th></tr>
</thead>
<tbody>
  <tr>
    <td rowspan="4">（位置参数）</td><td>是</td><td>原文</td><td></td>
  </tr>
  <tr>
    <td>是</td><td>注音或字符注释</td><td></td>
  </tr>
  <tr>
    <td>否</td><td>原文语言</td><td></td>
  </tr>
  <tr>
    <td>否</td><td>注音或字符注释的语言</td><td>不指定即使用原文语言</td>
  </tr>
</tbody>
</table>

### 示例

{{< example unescape=true type="col" inline=true >}}
{{< example >}}
{{</* ruby "骨" "gǔ" */>}}
{{< /example >}}
{{< example >}}
{{</* ruby "**骨**" "*gǔ*" */>}}
{{< /example >}}
{{< /example >}}

{{< example unescape=true type="col" inline=true >}}
{{< example >}}
{{</* ruby "骨" "gǔ" "zh-Hans" */>}}
{{< /example >}}
{{< example >}}
{{</* ruby "骨" "ㄍㄨˇ" "zh-Hant" */>}}
{{< /example >}}
{{< example >}}
{{</* ruby "骨" "ほね" "ja" "ja-Hrkt" */>}}
{{< /example >}}
{{< example >}}
{{</* ruby "骨" "골" "ko-Kore" "ko" */>}}
{{< /example >}}
{{< /example >}}
