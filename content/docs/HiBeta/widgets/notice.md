---
title: Notice
tags:
  - Hugo
  - HiBeta
---

## 简介

该微件用于展示一条提示信息。

## Markdown Blockquotes

### 类型

1. 与 [GitHub Alerts](https://docs.github.com/en/contributing/style-guide-and-content-model/style-guide#alerts) 兼容，支持五个类型 (Note, Tip, Important, Warning, Caution):

    {{< example >}}
> [!NOTE]
> Useful information that users should know, even when skimming content.

> [!TIP]
> Helpful advice for doing things better or more easily.

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

> [!WARNING]
> Urgent info that needs immediate user attention to *avoid problems*.

> [!CAUTION]
> Advises about **risks** or negative outcomes of certain actions.
    {{< /example >}}

1. 额外添加四个类型 (Info, Success, Error, Danger):

    {{< example >}}
> [!INFO]
> The quick brown ~~fox~~ jumps over the lazy dog.

> [!SUCCESS]
> The quick brown fox jumps over the lazy dog.

> [!ERROR]
> The quick brown fox jumps over the lazy dog.

> [!DANGER]
> The quick brown fox jumps over the lazy dog.
    {{< /example >}}

### 标题

可覆盖默认的标题：

{{< example >}}
> [!INFO] 这是一条提示信息
> The quick brown fox jumps over the lazy dog.
{{< /example >}}


## 短代码

### 参数

| 名称     | 类型                                                     | 必要   | 值                          | 描述                                                  |
| -------- | -------------------------------------------------------- | ------ | --------------------------- | ----------------------------------------------------- |
| `type`   | {{<datatype string 字符串>}}                             | **是** | （见上方，共 9 个类型）     | 提示类型                                              |
| `title`  | {{<datatype string 字符串>}}                             | 否     |                             | 提示的标题，默认与类型相关                            |
| `icon`   | {{<datatype string 字符串>}} / {{<datatype bool>}} false | 否     |                             | 提示的图标，默认与类型相关<br>设置为 `false` 禁用图标 |
| `small`  | {{<datatype bool 布尔>}}                                 | 否     | `true`、**`false`**（默认） | 小号的提示                                            |
| `simple` | {{<datatype bool 布尔>}}                                 | 否     | `true`、**`false`**（默认） | 简化的提示                                            |

### 示例

{{< example >}}
{{%/* notice type="info" */%}}The quick brown fox jumps over the lazy dog.{{%/*/notice*/%}}
{{%/* notice type="info" icon=false */%}}这是一个**没有图标**的提示{{%/*/notice*/%}}
{{%/* notice type="info" icon="bi-pen" */%}}这是一个指定了**图标**的提示{{%/*/notice*/%}}
{{%/* notice type="info" icon="bi-pen" title="Pen" */%}}这是一个指定了**图标**和**标题**的提示{{%/*/notice*/%}}
{{%/* notice type="tip" small=true */%}}这是一个小号的提示{{%/*/notice*/%}}
{{%/* notice type="tip" simple=true */%}}这是一个简化的提示{{%/*/notice*/%}}
{{%/* notice type="tip" simple=true small=true */%}}这是一个简化的小号的的提示{{%/*/notice*/%}}
{{%/* notice type="tip" simple=true small=true icon=false */%}}这是一个没有图标的简化的小号的的提示{{%/*/notice*/%}}
{{< /example >}}

## 局部模板

### `widgets\notice.html`

#### 参数

| 名称      | 类型                                                     | 必要   | 值                          | 描述                                                  |
| --------- | -------------------------------------------------------- | ------ | --------------------------- | ----------------------------------------------------- |
| `page`    | {{<datatype object hugo.Page>}}                          | **是** |                             |                                                       |
| `type`    | {{<datatype string 字符串>}}                             | **是** | （见上方，共 9 个类型）     | 提示类型                                              |
| `content` |                                                          | 否     |                             | 提示的内容                                            |
| `title`   | {{<datatype string 字符串>}}                             | 否     |                             | 提示的标题，默认与类型相关                            |
| `icon`    | {{<datatype string 字符串>}} / {{<datatype bool>}} false | 否     |                             | 提示的图标，默认与类型相关<br>设置为 `false` 禁用图标 |
| `small`   | {{<datatype bool 布尔>}}                                 | 否     | `true`、**`false`**（默认） | 小号的提示                                            |
| `simple`  | {{<datatype bool 布尔>}}                                 | 否     | `true`、**`false`**（默认） | 简化的提示                                            |
