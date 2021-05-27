---
description: 如果您没有从配置文件中删除文件的权限，或者您不希望永久删除文件，则可以使用空（零字节）文件隐藏文件。
title: 通过清空文件（零字节）来隐藏文件
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
exl-id: d5841fb5-afae-4352-aded-01b0b2eb9f85
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 50%

---

# 通过清空文件（零字节）来隐藏文件{#hide-a-file-by-emptying-it-zero-byte}

如果您没有从配置文件中删除文件的权限，或者您不希望永久删除文件，则可以使用空（零字节）文件隐藏文件。

在[!DNL Profile Manager]的列中，连字符(-)（而不是复选标记）标识零字节文件。

![](assets/vis_ProfMgr_Zero-byte.png)

与隐藏文件的其他方法(如[!DNL order.txt]、Show（显示）参数和Hidden（隐藏）参数)不同，Data Workbench将零字节文件视为不存在。 例如，如果将可视化或量度定义中使用的维度设置为零字节，则Data Workbench会分别为该可视化或量度生成错误。

此功能在许多情况下都非常有用，包括在您希望执行以下操作时：

* **使文件在Data Workbench** 下不可用，而不需要删除文件所需的配置文件权限。
* **将量度、维度或过滤器移动至其他位置**，而不需要从原始位置中删除文件所必需的配置文件权限。
* **隐藏菜单项。** 例如，配置文 [!DNL Base] 件在文 [!DNL Metric Legend] 件中定 [!DNL Metric.vw] 义。假定您的公司已创建三个需要在“添加图例”>“量度”子菜单中显示的量度图例。可以将[!DNL Base]配置文件[!DNL Metric.vw]设置为零字节，以便仅显示新子菜单和三个新量度图例。

**隐藏文件**

1. 在[!DNL Profile Manager]中，打开必要的文件夹和子文件夹，以找到要设置零字节的文件。
1. 右键单击文件名称旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。
1. 打开本地文件并删除其内容。
1. 保存并关闭该文件。
