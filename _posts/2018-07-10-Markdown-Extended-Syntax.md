---

layout: 	post

title:     	Markdown扩展语法

author: 	Pan Zaiyu

date: 	2018-07-10

description: Markdown's extended syntax.

---

此文翻译自 <https://www.markdownguide.org/extended-syntax>

# 综述

John Gruber最初的设计文档中列出的基本语法添加了许多日常所需的基本元素，但对一些人来说这还不够。这就催生了扩展语法。

一些个人和组织通过添加额外的元素，如表格、代码块、语法高亮显示、URL自动链接和脚注，来扩展基本语法。这些元素可以通过使用一种基于标记语法的轻量级标记语言来实现，也可以通过向兼容的Markdown处理器添加扩展来实现。

## 可用性

扩展的语法不是在所有Markdown程序中都是可用的。你将需要检查你的应用程序所使用的轻量级标记语言是否支持扩展语法。如果它没有，那么在你的Markdown处理器中启用扩展仍然是可能的。

### 轻量级标记语言

有几种轻量级标记语言是Markdown的超集。它们包括Gruber的基本语法并基于它来实现，通过添加额外的元素，如表格、代码块、语法高亮显示、URL自动链接和脚注等。许多最流行的Markdown应用程序使用以下的轻量级标记语言之一：

- CommonMark
- GitHub Flavored Markdown (GFM)
- Markdown Extra
- MultiMarkdown

### Markdown处理程序

有很多的Markdown处理程序可找到。它们中的许多允许你添加可以扩展语法的扩展。检查你的处理程序的文档以获取更多信息。

## 表格

要添加一张表格，可以使用三个或更多的连字符(`---`)来创建每个列的标题，并用管道符(`|`)来分割每一列。你可以选择性地在表格两端添加管道符(`|`)。

    | Syntax  	| Description |
    | ----------- | ----------- |
    | Header  	| Title   	|
    | Paragraph   | Text		|

渲染后的输出如下：

| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

单元的宽度可自适应。

> **Tip**: 用连字符和管道符创建表格可能会很繁琐。为了加速这个过程，尝试使用[Markdown表格生成器](http://www.tablesgenerator.com/markdown_tables "Markdown Tables Generator")：使用图形界面构建一个表格，然后将生成的markdown风格的文本复制到你的文件中。

### 对齐

你可以通过在标题行的连字符的左边、右边或两端添加一个冒号(`:`)来对齐这一列的文本到左边、右边或者中间。

    | Syntax  	| Description | Test Text |
    | :---		|:----:   	|  ---: 	|
    | Header  	| Title   | Here's this   |
    | Paragraph   | Text| And more  |

渲染后的输出如下：

| Syntax      | Description | Test Text     |
| :---        	|    :----:   |          ---: |
| Header      | Title        | Here's this   |
| Paragraph   | Text        | And more      |

### 格式化表格中的文本

你可以再表格中格式化文本。例如，你可以添加链接、代码（仅限在代号符`` ` ``中的单词或短语，不能是代码块）和强调。

你不能添加标题、引用、列表、水平线、图像或者HTML标记。

### 转义表格中的管道符

你可以使用管道符的HTML字符编码(`&#124`）来在表格中显示一个管道符（`|`）。

## 围起的代码块

基本的Markdown语法允许你通过4个空格或1个tab来创建代码块。如果你觉得不方便，可以尝试使用围起代码块。取决于你的Markdown处理程序或编辑器，你将可在代码块的前面和后面的行使用三个代号符（`` ``` ``）或三个波浪符（`` ~~~ ``）来实现。这样做的最美之处在于，你不需要缩进任何行。

    ```
    {
      "firstName": "John",
      "lastName": "Smith",
      "age": 25
    }
    ```
渲染后的输出如下：

```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

## 语法高亮

许多Markdown处理程序支持对围起的代码块的语法高亮显示。这个特性允许你为你的代码添加其书写语言对应的颜色高亮。要添加语法高亮显示，请在围起的代码块前面的代号符的旁边指定一种语言。

    ```json
    {
      "firstName": "John",
      "lastName": "Smith",
      "age": 25
    }
    ```
渲染后的输出如下：

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

## 脚注

脚注允许你添加注释和引用，而不会使文档的主题混乱。当你创建一个脚注时，一个带有链接的超级脚本编号会出现在你添加脚注引用的地方。读者可以点击这个链接跳转到页面底部的脚注的内容。

要创建一个脚注引用，在括号内添加一个插入符和标识符（`[^1]`）。标识符可以是数字或单词，但它们不能包含空格或tab。标识符只将脚注引用与脚注本身关联——在输出中，脚注按顺序编号。

使用另一种在包含插入符和标识符的方括号后添加冒号和文本的方式添加脚注，你将不需要把脚注放在文档的末尾。你可以把它们放在任何地方，除了列表、块引号和表格等其它元素。

    Here's a simple footnote,[^1] and here's a longer one.[^bignote]
    
    [^1]: This is the first footnote.
    
    [^bignote]: Here's one with multiple paragraphs and code.
    
    	Indent paragraphs to include them in the footnote.
    
    	`{ my code }`
    
    	Add as many paragraphs as you like.

渲染后的输出如下所示（此处可能不支持）：

Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.

## 标题ID

许多Markdown处理程序支持为标题自定义ID——一些Markdown处理程序会自动添加它们。添加自定义ID允许你直接链接到标题，并使用CSS修改它们。要添加一个自定义标题ID，请在与标题相同的行中，用花括号包住自定义ID。

	### My Great Heading {#custom-id}

对应的HTML文本如下：

	<h3 id="custom-id">My Great Heading</h3>

### 链接到标题ID {#heading-ids}

你可以通过创建一个带有`#`号和自定义ID的标准链接来链接到标题。

	### My Heading {#testhead}

	[Heading IDs](#testhead)

渲染后的输出如下：

#### My Heading {#testhead}

[Heading IDs](#testhead)

一些网站可以通过添加标题ID到完整的URL来链接到标题（e.g. `[Heading IDs](https:/www.markdownguide.org/extended-syntax#heading-ids)`)。

## 删除线

你可以通过在单词的中心放置一条水平线来“删除”单词，结果就像~~这样~~。这个特性允许你指出一些单词是错误的，而不应包含在文档中。要删除单词，在单词的前后使用两个波浪号。

	~~The world is flat.~~ We now know that the world is round.

渲染后的效果如下：

~~The world is flat.~~ We now know that the world is round.

## 任务列表

任务列表允许你创建带有复选框的项目列表。在支持任务列表的Markdown应用中，复选框将显示在内容的旁边。要创建一个任务列表，在任务列表项的前面添加破折号（`-`）和带有空格的方括号（`[ ]`）。要选择复选框，请在方括号之间添加一个x（`[x]`）。

    - [x] Write the press release
    - [ ] Update the website
    - [ ] Contact the media

渲染后的效果如下：

- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media

## 自动的URL链接

许多Markdown处理程序自动地将URL转换为链接。这意味着如果你输入`http://www.example.com`，你的Markdown处理程序将会自动地将它转换为一个链接即使你没有使用括号。

	http://www.example.com

上面的URL会自动转换为链接：

http://www.example.com

###禁用自动URL链接

如果你不想一个URL被自动链接，你可以通过用代号符`` ` ``将URL标记为代码来移除链接。

    `http://www.example.com`

渲染后的输出如下：

`http://www.example.com`
