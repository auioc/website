---
title: 转义
tags:
  - Hugo
  - HiBeta
---

在某些特殊情况下, 文章内容可能与 Markdown 基本/扩展语法冲突，此时应对冲突的语法中的字符进行转义以渲染得到需要的内容。

## 语法

以下两种语法等价：

- {{< kbd "{" ";+" >}} {{< kbd "需要转义的字符+" >}} {{< kbd "}" >}}
  {{< example unescape=true type="col" inline=true >}}
{{;;}x}
  {{< /example >}}

- {{< kbd "{" "?+" >}} {{< kbd "需要转义的字符+" >}} {{< kbd "}" >}}
  {{< example unescape=true type="col" inline=true >}}
{{??}x}
  {{< /example >}}

## 示例

{{< example unescape=true type="col" inline=true >}}
{{< example unescape=false >}}
:blush:
{{< /example >}}
{{< example >}}
{{;;}:}blush:
{{< /example >}}
{{< example >}}
{{??}:}blush:
{{< /example >}}
{{< example >}}
{{{;;};}:}blush:
{{< /example >}}
{{< example >}}
{{{??}?}:}blush:
{{< /example >}}
{{< /example >}}

{{< example unescape=true type="col" inline=true >}}
{{< example >}}
[汉]{;^}(hàn)
{{< /example >}}
{{< example >}}
[汉]{{;;}^}(hàn)
{{< /example >}}
{{< example >}}
[汉]{{??}^}(hàn)
{{< /example >}}
{{< example >}}
[汉]{{{;;};}^}(hàn)
{{< /example >}}
{{< example >}}
[汉]{{{??}?}^}(hàn)
{{< /example >}}
{{< /example >}}
