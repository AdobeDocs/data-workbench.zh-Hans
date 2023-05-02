---
title: 隐藏的测试页
description: 此页面在搜索和目录中处于隐藏状态
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
exl-id: 25669153-b90c-4cf6-81aa-cabcbf2cbcb6
source-git-commit: a3625867de6b7b8f8b7f71b3b124f028356dabad
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 3%

---

# 隐藏的测试页

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
>这是警告。

>[!CAUTION]
>
>这是一个警告。

>[!ADMIN]
>
>这是管理员说明。 仅限EXL。

>[!AVAILABILITY]
>
>这是可用说明。 仅限EXL。

>[!PREREQUISITES]
>
>这是先决条件说明。 仅限EXL。

>[!INFO]
>
>这是“信息”注释。 仅限EXL。

>[!ERROR]
>
>这是错误说明。 仅限EXL。

>[!SUCCESS]
>
>这是成功说明。 仅限EXL。

>[!MORELIKETHIS]
>
>* 页面 1
>* 页面 2


## 徽章

徽章是用作内容指示器的彩色标签。 例如，您可以添加一个徽章，以将文章标记为 _Beta_ 或作为 _Premium_. 您可以更改徽章的颜色，并关联URL和工具提示。

[!BADGE 徽章示例]

徽章有两种类型，每种类型的语法不同：

* **元数据**  — 在页面顶部附近显示徽章
* **内联**  — 显示语法所在的标记

### 元数据徽章

在元数据中添加标记语法会在文章中页面标题(H1)的上方放置一个标记。

例如，您可以使用 _徽章1_ 或 _徽章2_. 或者，您可以更具创意(只要名称以 _徽章_)。

元数据示例：

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium:** 此示例显示一个带有URL和工具提示的Premium徽章。

* **badgeExam:** 此示例显示一个带有考试ID号的深色徽章。

#### 内联徽章

在标题、表格或其他页面元素中，在其自己的行或其他页面元素中指定标记信息。

以下是带有测试版标签、蓝色、URL和工具提示的内联标记的语法：

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### 可用徽章颜色

徽章使用Adobe色谱中定义的颜色：

| 类型 | 徽章 |
|---|---|
| 信息（默认） | [!BADGE Beta]{type=Informative url="https://www.example.com"} |
| 正面 | [!BADGE 新功能]{type=Positive url="https://www.example.com" tooltip="转到example.com"} |
| 负面 | [!BADGE 已终止]{type=negative tooltip="此功能现已终止使用"} |
| 中性 | [!BADGE 也许]{type=Neutral tooltip="一个骑手从马上摔下来……"} |
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

* 元数据中仅允许使用两个徽章。 此规则是可配置的，因此如果您需要例外，请告知我们。
* 只需要标记标签。 的 `type`, `url`和 `tooltip` 参数是可选的。 的 `type` 参数确定颜色。 的 `url` 参数允许用户单击徽章以打开文章或页面。 的 `tooltip` 参数在鼠标悬停时显示工具提示文本。
* 向 `TOC.md` 文件会在指南中的每篇文章上显示标记。 如果为徽章指定了跳转到文章的URL，请确保使用根链接(例如， `/help/guide/article.md`)不是相对链接(例如， `article.md`)来考虑不同文件夹中的文章。
* 将标记添加到 `metadata-new.md` 在存储库中的每篇文章中显示标记。
* 对于元数据徽章，请确保所有值都用引号括起来。 对于内联徽章，请确保 `url` 和 `tooltip` 用引号括起来。
* 有效类型值包括 *信息* （默认，蓝色）， *积极* （绿色）、 *负* （红色）、 *中性* （深灰色）和 *注意* （黄色）。
* 标记标签已本地化。
* 如果指定了多个元数据徽章，则会根据徽章名称(如 `badge1:` 或 `badgeWeb`.
* 如果希望在新选项卡中打开URL，请使用以下语法：

   ```
   [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
   ```

   已呈现:

   [!BADGE 在新选项卡中打开]{type=Negative url="https://www.adobe.com newtab=true" tooltip="在新选项卡中打开adobe.com"}

## 文本突出显示

Workfront团队要求能够使用黄色突出显示指示即将推出的功能的预览。 这是它的工作方式。

示例 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

已呈现:

不应突出显示整个段落。 <span class="preview"> 这个词是 **粗体** 在突出显示的句子中。</span> 这只是最后一句。

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

突出显示应在此段后开始。

<div class="preview">

DIV的开头。

这是新段落，然后是图像

![image](/help/home/assets/analytics-icon-24.png)

上次突出显示的项目。

</div>

未突出显示

## 代码块的语法突出显示

Experience League支持代码块的语法突出显示。 确保指定语言，例如 `java` 在后撇号的开始集之后，确保正确突出显示语法。 有关有效语言的列表，请参阅 [https://prismjs.com](https://prismjs.com/#supported-languages). 如果缺少任何语言，请记录一张日志票证。

### 代码块中的行编号

添加 `{line-numbers="true"}` 在语言之后启用行编号。

行号(&grave;&grave;&grave;&grave;)的示例。`html {line-numbers="true"}`):

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**第_行开始编号**

添加 `start-number="n"` 在行号语法之后，以1以外的数字开始编号。

示例，包含新的起始线(&grave;&grave;&grave;;`html {line-numbers="true" start-line="7"}`):

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

### 代码块中的线条突出显示

添加 `highlight="n"` 在行号语法之后突出显示代码块中的行。 指定 `11-13, 16` 将突出显示第11至13和16行。

加亮线条(&grave;&grave;&grave;&grave;)的示例。`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`):

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
