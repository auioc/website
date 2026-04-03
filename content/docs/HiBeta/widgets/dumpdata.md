---
title: Dump Data
tags:
  - Hugo
  - HiBeta
params:
  hljs:
    languages: []
---

## 简介

该微件用于使用特定格式转储式输出[数据](https://gohugo.io/functions/hugo/data/)。

## 短代码

### 参数

| 名称           | 必要 | 值                                                                     | 描述                                      |
| -------------- | ---- | ---------------------------------------------------------------------- | ----------------------------------------- |
| （位置参数 1） | 是   | 数据的[标识符](https://gohugo.io/quick-reference/glossary/#identifier) | 使用 `/` 分割层级                         |
| （位置参数 2） | 否   | 输出格式                                                               | **`json`**（默认）、`toml`、`xml`、`yaml` |

### 示例

#### 原始数据

```json {title="data/docs/example.json"}
{
  "name": "John Doe",
  "age": 30,
  "isStudent": false,
  "hobbies": ["reading", "cycling"],
  "address": {
    "city": "New York",
    "zipcode": "10001"
  }
}
```

#### 输出示例

{{< example >}}
{{< example >}}
{{</* dumpdata "docs/example" */>}}
{{< /example >}}
{{< example >}}
{{</* dumpdata "docs/example" "yaml" */>}}
{{< /example >}}
{{< example >}}
{{</* dumpdata "docs/example" "toml" */>}}
{{< /example >}}
{{< example >}}
{{</* dumpdata "docs/example" "xml" */>}}
{{< /example >}}
{{< /example >}}
