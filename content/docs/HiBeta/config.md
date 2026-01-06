---
title: 配置
tags:
  - Hugo
  - HiBeta
---

除了 [Hugo 全局配置](https://gohugo.io/overview/configuration/) 之外, 可配置的其他参数。

## 示例

{{< tabs title="hugo." >}}
{{% tab title="YAML" icon="xi-filetype-yml" %}}

```yaml {noHeader=true}
markup:
  _merge: shallow
menus:
  main:
    - name: 文章
      url: /posts
      weight: 1
  home:
    - name: Posts
      url: /posts
      weight: 1
params:
  description: Description
  toc: true
  defaultAuthor: DefaultAuthor
  copyrightLicense: ''
  datetimeFormats:
    time: '15:04:05'
    date: '2006-01-02'
    dateShort: '01/02'
    datetime: '2006-01-02 15:04:05 MST'
  home:
    backgroundColor: '#000'
    frontgroundColor: '#fff'
    logo: LOGO
  footer:
    poweredBy: true
    showVersion: true
    copyright:
      year: 2026
      author: Author
      link: 'https://example.com'
      rights: All Rights Reserved.
  repository:
    branch: main
    owner: owner
    repo: repo
    urlEdit: 'https://github.com/%s/%s/edit/%s/%s'
    urlView: 'https://github.com/%s/%s/blob/%s/%s'
  development:
    replaceCdnHosts:
      - 'https://cdnjs.cloudflare.com'
```

{{% /tab %}}
{{% tab title="TOML" icon="bi-file-text" %}}

```toml {noHeader=true}
[markup]
    _merge = "shallow"

[menus]
    [[menus.main]]
        name = '文章'
        url = '/posts'
        weight = 1

    [[menus.home]]
        name = 'Posts'
        url = '/posts'
        weight = 1

[params]
    description = "Description"
    toc = true
    defaultAuthor = "DefaultAuthor"
    copyrightLicense = ""
    [params.datetimeFormats]
        time = "15:04:05"
        date = "2006-01-02"
        dateShort = "01/02"
        datetime = "2006-01-02 15:04:05 MST"
    [params.home]
        backgroundColor = "#000"
        frontgroundColor = "#fff"
        logo = "LOGO"
    [params.footer]
        poweredBy = true
        showVersion = true
        [params.footer.copyright]
            year = 2026
            author = "Author"
            link = "https://example.com"
            rights = "All Rights Reserved."
    [params.repository]
        branch = 'main'
        owner = 'owner'
        repo = 'repo'
        urlEdit = 'https://github.com/%s/%s/edit/%s/%s'
        urlView = 'https://github.com/%s/%s/blob/%s/%s'
    [params.development]
        replaceCdnHosts = ['https://cdnjs.cloudflare.com']
```

{{% /tab %}}
{{% tab title="JSON" icon="xi-filetype-json" %}}

```json {noHeader=true}
{
  "markup": {
    "_merge": "shallow"
  },
  "menus": {
    "main": [
      {
        "name": "文章",
        "url": "/posts",
        "weight": 1
      }
    ],
    "home": [
      {
        "name": "Posts",
        "url": "/posts",
        "weight": 1
      }
    ]
  },
  "params": {
    "description": "Description",
    "toc": true,
    "defaultAuthor": "DefaultAuthor",
    "copyrightLicense": "",
    "datetimeFormats": {
      "time": "15:04:05",
      "date": "2006-01-02",
      "dateShort": "01/02",
      "datetime": "2006-01-02 15:04:05 MST"
    },
    "home": {
      "backgroundColor": "#000",
      "frontgroundColor": "#fff",
      "logo": "LOGO"
    },
    "footer": {
      "poweredBy": true,
      "showVersion": true,
      "copyright": {
        "year": 2026,
        "author": "Author",
        "link": "https://example.com",
        "rights": "All Rights Reserved."
      }
    },
    "repository": {
      "branch": "main",
      "owner": "owner",
      "repo": "repo",
      "urlEdit": "https://github.com/%s/%s/edit/%s/%s",
      "urlView": "https://github.com/%s/%s/blob/%s/%s"
    },
    "development": {
      "replaceCdnHosts": [
        "https://cdnjs.cloudflare.com"
      ]
    }
  }
}
```

{{% /tab %}}
{{< /tabs >}}

## 参数

### `markup._merge`

使用透传功能以通过标记（如 `$$ ... $$`、`\[ ... \]`、`\( ... \)` 等）来[渲染表达式](/docs/hibeta/content/math-chem/#%E9%80%8F%E4%BC%A0)，需要将此参数设置为 `shallow`。

### `menus`

- `menus.main`：上方顶栏中导航栏的菜单
- `menus.home`：主页中的菜单

配置方法见 [Hugo 文档](https://gohugo.io/configuration/menus/)。

### `params.description`

*未实现*

### `params.toc`

- 类型：{{<datatype bool 布尔>}}
- 默认值： `false`

是否启用文章的目录。可通过 [页面参数](https://gohugo.io/methods/page/params/) 覆盖此参数。

### `params.defaultAuthor`

- 类型：{{<datatype string 字符串>}}
- 默认值： *`nil`*

当没有指定文章作者时的默认作者。

### `params.copyrightLicense`

- 类型：{{<datatype string 字符串>}}
- 默认值： *`nil`*

当没有指定文章所使用的许可时的默认许可。

### `params.datetimeFormats`

- `time`：时间格式
- `date`：日期格式
- `dateShort`：短日期格式
- `datetime`：完整时间日期格式

格式化字符串的用法见 [Go 文档](https://pkg.go.dev/time#pkg-constants)。

默认值：

- `time`：`15:04:05`
- `date`：`2006-01-02`
- `dateShort`：`01/02`
- `datetime`：`2006-01-02 15:04:05 -07:00`

### `params.home`

- `backgroundColor`、`frontgroundColor` {{<datatype string 字符串>}}

    主页的背景颜色和前景颜色，格式为 [CSS 颜色](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Colors/Color_values)。

- `logo` {{<datatype string 字符串>}}

    若为有效的资源（图片）路径，则主页标志显示为指定的图片，否则直接显示此处设置的字符串。

### `params.footer`

- `poweredBy`
  - 类型：{{<datatype bool 布尔>}}
  - 默认值： `false`

  是否在页脚显示 “Powered By Hugo” 的字样。

- `showVersion`
  - 类型：{{<datatype bool 布尔>}}
  - 默认值： `false`

  是否在页脚的 “Powered By Hugo” 的字样中显示构建网站时使用的 Hugo 版本，例如 “Powered by Hugo v0.154.1”。

#### `params.footer.copyright`

页脚的版权信息。

- `year`：版权起始年份
- `author`：版权所有者
- `link`：版权所有者的链接
- `rights`：权利声明

### `params.repository`

用于生成页面对应源码仓库的链接的配置。

- `owner`：仓库所有者
- `repo`：仓库名称
- `branch`：分支
- `urlEdit`、`urlView`：对应文件的编辑、查看链接

  为 [Go 格式化字符串](https://pkg.go.dev/fmt#hdr-Printing)，带有四个字符串变量，依次为 `owner`、`repo`、`branch`、文件路径。
  - 若存在对应的提交，则 `branch` 位置为此提交的哈希值。
  - 默认为 GitHub 的链接格式：
    - urlEdit：`https://github.com/%s/%s/edit/%s/%s`
    - urlView：`https://github.com/%s/%s/blob/%s/%s`

### `params.development`

开发环境的相关设置。

- `replaceCdnHosts`
  - 类型：{{<datatype string>}}{{<datatype homoarray 字符串数组>}}
  - 默认值： *`nil`*

  将使用的外部资源的 CDN 的主机名替换为本地地址。
