---
title: 代码语法高亮
tags:
  - Hugo
  - HiBeta
---

## Highlight.JS

默认使用 [Highlight.JS](https://highlightjs.org) 进行代码语法高亮。

可通过代码块或短代码使用。

### 支持的语言

- 默认情况下只支持以下 “Common” 类别中的语言 [^1] ：
    `bash`、`c`、`cpp`、`csharp`、`css`、`diff`、`go`、`graphql`、`ini`、`java`、`javascript`、`json`、`kotlin`、`less`、`lua`、`makefile`、`markdown`、`objectivec`、`perl`、`php`、`php-template`、`plaintext`、`python`、`python-repl`、`r`、`ruby`、`rust`、`scss`、`shell`、`sql`、`swift`、`typescript`、`vbnet`、`wasm`、`xml`、`yaml`
    [^1]: <https://highlightjs.org/download/>

- 可通过 **页面参数**[^2] `hljs.languages` 添加其他 HLJS 支持的语言
    [^2]: <https://gohugo.io/content-management/front-matter/#parameters>
  - 例如添加 `powershell` 的支持：

    {{< tabs title="content/example.md" >}}
{{% tab title="YAML" icon="xi-filetype-yml" %}}

```yaml
---
title: Example
params:
  hljs:
    languages:
       - powershell
---
```

{{% /tab %}}
{{% tab title="TOML" icon="bi-file-text" %}}

```toml
+++
title = 'Example'
[params.hljs]
languages = [ "powershell" ]
+++
```

{{% /tab %}}
{{% tab title="JSON" icon="xi-filetype-json" %}}

```json
{
  "title": "Example",
  "params": {
    "hljs": {
      "languages": [
        "powershell"
      ]
    }
  }
}
```

{{% /tab %}}
{{< /tabs >}}

### 用法

#### 代码块

{{< example type="col" extended=false >}}

```javascript
const array1 = [1, 2, 3, 4];
const sum = array1.reduce((a, b) => a + b);
```

{{< /example  >}}

##### 参数

可以添加以花括号包裹、以空格为分割的参数：

{{< example type="col" extended=false >}}

```javascript {lineNos=true title="helloworld.js" copy=true }
(() => {
    console.log("Hello World!");
})();
```

{{< /example  >}}

| 名称           | 类型                         | 必要           | 值                                                                                                  | 描述                                     |
| -------------- | ---------------------------- | -------------- | --------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| `noHeader`     | {{<datatype bool 布尔>}}     | 否             | `true`、**`false`**（默认）                                                                         | 是否禁用代码顶部的标题栏                 |
| `title`        | {{<datatype string 字符串>}} | 否             |                                                                                                     | 标题                                     |
| `copy`         | {{<datatype bool 布尔>}}     | 否             | `true`、**`false`**（默认）                                                                         | 是否显示「{{<icon "xi-copy">}}复制」按钮 |
| `lineNos`      | {{<datatype bool 布尔>}}     | 否             | `true`、**`false`**（默认）                                                                         | 是否显示行号                             |
| `lineNoStart`  | {{<datatype int 整数>}}      | 否             | 默认为 `1`                                                                                          | 起始行号                                 |
| ~~`hl_Lines`~~ | {{<datatype string 字符串>}} | *否（未实现）* | ~~以空格为分隔符：<br>`a` 行号为`a`的行 <br>`a,b` 行号为`a`和`b`的行 <br>`a-b` 行号为`a`到`b`的行~~ | ~~高亮的行的行号~~                       |

#### 短代码

使用 `code` 短代码对行内的代码进行语法高亮：

{{< example type="col" extended=false >}}
行内 {{</* code */>}}console.log("a"){{</* /code */>}}
{{< /example  >}}

通常情况下，HLJS 会自动判断代码的语言，如果自动检测结果有误或您希望明确指明代码的语言，可以使用首个位置参数指定语言：

{{< example type="col" extended=false >}}
行内 {{</* code java */>}}console.log("a"){{</* /code */>}}
{{< /example  >}}

## Chroma

保留了 Hugo 内建的 [Chroma](https://github.com/alecthomas/chroma) 代码语法高亮，须使用短代码来调用。

更多信息见 [Hugo 文档](https://gohugo.io/shortcodes/highlight/)。

{{< example type="col" extended=false >}}
{{</* highlight go "linenos=inline, style=github" */>}}
package main
import "fmt"
func main() {
    for i := 0; i < 3; i++ {
        fmt.Println("Value of i:", i)
    }
}
{{</* /highlight */>}}
{{< /example  >}}



