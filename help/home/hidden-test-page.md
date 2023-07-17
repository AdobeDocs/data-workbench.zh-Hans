---
title: 隐藏测试页面
description: 此页面在搜索和目录中隐藏
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="下载Premium"
badgeExam: label="考试ADO-E903" type="neutral"
exl-id: 25669153-b90c-4cf6-81aa-cabcbf2cbcb6
source-git-commit: 3480cc9b82a5561a364a88f3d09c14cca56a0c7a
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 4%

---

# 隐藏测试页面

## 预览问题

以下段落无法在VSC预览中正确呈现。 我不知道为什么。

如果您的密码由管理 [!DNL Adobe]，您可以 [更改Adobe帐户中的密码](https://helpx.adobe.com/manage-account/using/change-or-reset-password.html){target="_blank"}.

## 注释类型

所有支持的注释类型。

>[!NOTE]
>
>This is a standard NOTE block.

>[!TIP]
>
>This is a standard tip.

>[!IMPORTANT]
>
>这是一个重要的注意事项。

>[!WARNING]
>
>这是一个警告。

>[!CAUTION]
>
>这是警告。

>[!ADMIN]
>
>这是一份管理员注释，呈现为“管理”。 仅限EXL。

>[!AVAILABILITY]
>
>这是可用性说明。 仅限EXL。

>[!PREREQUISITES]
>
>这是先决条件说明。 仅限EXL。

>[!INFO]
>
>这是信息注释。 仅限EXL。

>[!ERROR]
>
>这是错误注释。 仅限EXL。

>[!SUCCESS]
>
>这是“成功”注释。 仅限EXL。

>[!MORELIKETHIS]
>
>* 页面 1
>* 页面 2

## 徽章

徽章是用作内容指示器的彩色标签。 例如，您可以添加徽章以将文章标记为 _测试版_ 或节为 _Premium_. 您可以更改徽章的颜色并关联URL和工具提示。

[!BADGE 徽章示例]

有两种类型的徽章，每种徽章的语法不同：

* **元数据**  — 在页面顶部附近显示徽章
* **内联**  — 显示语法所在的徽章

### 元数据徽章

在元数据中添加标记语法时，会将标记放置在文章中的页面标题(H1)上方。

您可以命名徽章，例如，使用 _徽章1_ 或 _徽章2_. 或者，您可以更富创造性（只要名称以开头） _徽章_)。

元数据示例：

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium：** 此示例显示带有URL和工具提示的Premium徽章。

* **徽章考试：** 此示例显示带有考试ID号的深色徽章。

#### 内联徽章

在徽章自身行或标题、表格或其他页面元素中指定徽章信息。

以下是带有测试版标签、蓝色颜色、URL和工具提示的内联徽章的语法：

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### 可用的徽章颜色

徽章使用Adobe频谱中定义的颜色：

| 类型 | 徽章 |
|---|---|
| 信息（默认） | [!BADGE Beta]{type=Informative url="https://www.example.com"} |
| 正面 | [!BADGE 新功能]{type=Positive url="https://www.example.com" tooltip="转到example.com"} |
| 负面 | [!BADGE 已终止]{type=negative tooltip="此功能现已终止使用"} |
| 中性 | [!BADGE 也许]{type=Neutral tooltip="一个骑手从马上掉了下来……"} |
| 注意 | [!BADGE 注意]{type=Caution tooltip="黄色状态"} |

语法示例

```
|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off the horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|
```

### 徽章要求

* 元数据中只允许使用两个徽章。 此规则可配置，因此请告知我们您是否需要例外。
* 只需要徽章标签。 此 `type`， `url`、和 `tooltip` 参数是可选的。 此 `type` 参数确定颜色。 此 `url` 参数允许用户单击徽章以打开文章或页面。 此 `tooltip` 参数在mouseover上显示工具提示文本。
* 将徽章添加到 `TOC.md` 文件在指南中的每篇文章上显示徽章。 如果指定徽章跳转到文章的URL，请确保使用根链接(例如， `/help/guide/article.md`)而不是相对链接(例如， `article.md`)以考虑不同文件夹中的文章。
* 将徽章添加到 `metadata-new.md` 在存储库中的每个文章上显示徽章。
* 对于元数据徽章，请确保所有值都用引号括起来。 对于内联徽章，请确保 `url` 和 `tooltip` 用引号括起来。
* 有效类型值包括 *信息性* （默认，蓝色）， *正面* （绿色）， *负面* （红色）， *中性* （深灰色），和 *注意* （黄色）。
* 徽章标签已本地化。
* 如果指定了多个元数据徽章，则会根据徽章名称按字母顺序显示徽章，例如 `badge1:` 或 `badgeWeb`.
* 如果您希望在新选项卡中打开URL，请使用以下语法：

  ```
  [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
  ```

  已呈现:

  [!BADGE 在新选项卡中打开]{type=Negative url="https://www.adobe.com newtab=true" tooltip="在新选项卡中打开adobe.com"}

## 文本突出显示

Workfront团队要求能够使用黄色突出显示来指示即将推出的功能的预览。 下面是它的工作方式。

示例 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

已呈现:

此整个段落不应突出显示。 <span class="preview"> 这个词是 **粗体** 高亮显示的句子内。</span> 这还只是最后一句话。

示例 2:

```
Highlighting should start after this paragraph.

<div class="preview">

Start of DIV.

This is a new paragraph, then an image

![image](/help/home/assets/analytics-icon-24.png)

Last highlighted item.

</div>

Not highlighted
```

已呈现:

突出显示应在此段落之后开始。

<div class="preview">

DIV的开头。

这是新段落，然后是图像

![image](/help/home/assets/analytics-icon-24.png)

最后一个高亮显示的项目。

</div>

未突出显示

## 代码块的语法突出显示

Experience League支持代码块的语法高亮显示。 确保指定语言，例如 `java` 在开始的一组反撇号之后，确保正确高亮显示语法。 有关有效语言的列表，请参阅 [https://prismjs.com](https://prismjs.com/#supported-languages). 如果缺少任何语言，请记录jira票证。

### 代码块中的行编号

添加 `{line-numbers="true"}` 在语言之后启用行编号。

行号示例(&amp;grave；&amp;grave；&amp;grave；`html {line-numbers="true"}`)：

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**开始在线编号_**

添加 `start-number="n"` 在行号语法之后，在非1的编号上开始编号。

带有新起始线(&amp;grave；&amp;grave；&amp;grave；&amp;grave；`html {line-numbers="true" start-line="7"}`)：

```html {line-numbers="true" start-line="7"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```

### 代码块中的行突出显示

添加 `highlight="n"` 在行号语法之后，用于突出显示代码块中的行。 指定 `11-13, 16` 将突出显示第11行至第13行和第16行。

以线条突出显示(&amp;grave；&amp;grave；&amp;grave；`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`)：

```html {line-numbers="true" start-line="7" highlight="11-13, 16"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```
