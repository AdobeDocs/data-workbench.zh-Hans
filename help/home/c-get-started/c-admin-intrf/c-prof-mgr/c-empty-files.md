---
description: 如果您没有从配置文件中删除文件的权限，或者您不希望永久删除文件，则可以使用空（零字节）文件隐藏文件。
solution: Analytics
title: 通过清空文件（零字节）来隐藏文件
topic: Data workbench
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 通过清空文件（零字节）来隐藏文件{#hide-a-file-by-emptying-it-zero-byte}

如果您没有从配置文件中删除文件的权限，或者您不希望永久删除文件，则可以使用空（零字节）文件隐藏文件。

In the [!DNL Profile Manager], a hyphen (-), instead of a check mark, in a column identifies a zero-byte file.

![](assets/vis_ProfMgr_Zero-byte.png)

Unlike the other methods of hiding files (such as [!DNL order.txt], the Show parameter, and the Hidden parameter), Data Workbench treats zero-byted files as non-existent. 例如，如果将可视化或度量定义中使用的维设置为零字节，则Data Workbench会分别为该可视化或度量生成错误。

此功能在许多情况下都非常有用，包括在您希望执行以下操作时：

* **在Data Workbench中使文件不可用** ，无需删除文件所需的配置文件权限。
* **将量度、维度或过滤器移动至其他位置**，而不需要从原始位置中删除文件所必需的配置文件权限。
* **隐藏菜单项。** 例如，配置 [!DNL Base] 文件在文 [!DNL Metric Legend] 件中有定义 [!DNL Metric.vw] 。 假定您的公司已创建三个需要在“添加图例”>“量度”子菜单中显示的量度图例。You can zero-byte the [!DNL Base] profile [!DNL Metric.vw] file so that only your new submenu and three new metric legends appear.

**隐藏文件**

1. In the [!DNL Profile Manager], open the necessary folders and subfolders to locate the file that you want to zero-byte.
1. Right-click the check mark next to the name of the file and click **[!UICONTROL Make Local]**.
1. 打开本地文件并删除其内容。
1. 保存并关闭该文件。

