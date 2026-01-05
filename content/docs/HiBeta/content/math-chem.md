---
title: 数学、化学表达式
tags:
  - Hugo
  - HiBeta
---

使用 [KaTeX](https://katex.org/) 支持 [LaTeX](https://www.latex-project.org/) 格式的数学表达式。

使用 KaTeX 的 [mhchem](https://github.com/KaTeX/KaTeX/tree/main/contrib/mhchem) 扩展支持化学表达式。

## 用法

> [!TIP]
> 可通过双击表达式区域显示/隐藏该图表的 LaTeX 源码

### 数学

{{< example type="col" extended=true title="独立的段落" >}}
{{< example >}}
这是一个成独立的段落的数学表达式：

```math
\int_a^x \!\!\!\int_a^s f(y)\,dy\,ds = \int_a^x f(y)(x-y)\,dy
```

{{< /example >}}
{{< example >}}
也可使用 `math` 短代码：

{{</* math */>}}
\phi_n(\kappa) = \frac{1}{4\pi^2\kappa^2}
\int_0^\infty \frac{\sin(\kappa R)}{\kappa R}
\frac{\partial}{\partial R}
\left[R^2\frac{\partial D_n(R)}{\partial R}\right]\,dR
{{</* /math */>}}
{{< /example >}}
{{< example >}}
含有错误的部分会使用红色标出：
{{</* math */>}}
\int_a^x \/!\!\!\int_a^s f(y)\,dy\,ds = \int_a^x f(y)(x-y)\,dy
{{</* /math */>}}
{{< /example >}}
{{< /example  >}}

{{< example type="col" extended=false title="行内" >}}
{{< example >}}
行内表达式：{{</* math */>}} ax^2 + bx + c = 0 {{</* /math */>}}。
{{< /example >}}
{{< example >}}
含有错误的行内表达式：{{</* math */>}} $// {{</* /math */>}}。
{{< /example >}}
{{< /example  >}}

### 化学

{{< example type="col" extended=true title="独立的段落" >}}
{{< example >}}
这是一个成独立的段落的化学表达式：

```chem
CO2 + C -> 2 CO
```

{{< /example >}}
{{< example >}}
也可使用 `chem` 短代码：

{{</* chem */>}}
x Na(NH4)HPO4 ->[\Delta] (NaPO3)_x + x NH3 ^ + x H2O
{{</* /chem */>}}
{{< /example >}}
{{< /example  >}}

{{< example type="col" extended=false title="行内" >}}
{{< example >}}
行内表达式：{{</* chem */>}} H2O {{</* /chem */>}}。
{{< /example >}}
{{< /example  >}}

## 透传

> [!WARNING]
> 目前虽支持 [透传](https://gohugo.io/render-hooks/passthrough/) 使用常见的标记（如 `$$ ... $$`、`\[ ... \]`、`\( ... \)` 等）来展示表达式，
>
> 但出于稳定性考虑，更推荐使用代码块或短代码

### 数学

{{< example type="col" extended=false >}}
{{< example >}}
\[ x={-b\pm\sqrt{b^2-4ac} \over 2a} \]
{{< /example >}}
{{< example >}}
$$ \sum_{i=0}^{n-1} i $$
{{< /example >}}
{{< example >}}
行内：\( ax^2 + bx + c = 0 \)。
{{< /example >}}
{{< /example  >}}

### 化学

透传使用化学表达式须手动添加 `\ce{ ... }` 标记。

{{< example type="col" extended=false >}}
{{< example >}}
\[ \ce{ CO2 + C -> 2 CO } \]
{{< /example >}}
{{< example >}}
$$ \ce{ SO4^2- + Ba^2+ -> BaSO4 v } $$
{{< /example >}}
{{< example >}}
行内：\( \ce{ H2O } \)。
{{< /example >}}
{{< /example  >}}
