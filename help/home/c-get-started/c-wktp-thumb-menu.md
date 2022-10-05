---
description: 如何从Worktop导出、复制和书签。
title: 使用操作台缩略图菜单
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
exl-id: 2220051d-5c53-48ed-8e13-62883819f22a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 79%

---

# 使用操作台缩略图菜单{#using-the-worktop-thumbnail-menu}

{{eol}}

如何从Worktop导出、复制和书签。

右键单击工作区可访问 Worktop 中的导出、复制和书签功能。

![](assets/thumbnail_menu.png)

## 界面描述 {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

在 [!DNL Worktop] 缩略图菜单：

**服务器工作区:***名称*

仅对未编辑的服务器工作区显示。将已命名工作区标识为与服务器上存储的工作区相同。

**日期：***日期和时间*

上次打开工作区的日期和时间。

**本地版本:***名称*

仅对本地版本的服务器工作区显示。将已命名工作区标识为服务器上存储的已编辑的本地版本工作区。

**用户工作区:***名称*

仅对用户工作区显示。将已命名工作区标识为仅存在于本地计算机上的工作区。

**在后台计算**

仅当联机工作时显示。在您继续工作的同时，使所选工作区中的查询在后台运行。选择该选项时，缩略图显示以下信息，该信息指示查询的进度：

* “正在处理: *n%*”- 指示查询正在进行处理以及所完成处理的百分比。
* “*n* MB 查询负载”- 查询结果的总大小。查询负载与Data Workbench服务器的总内存负载成正比，但不直接相关。 作为指导原则，10 MB 或更高的查询负载可能会耗尽您的系统资源。所列的查询负载未考虑群集。

   >[!NOTE]
   >
   >如果“在后台计算”保持选中状态，则所选工作区中的查询将成为持续查询，并继续更新并使用内存负载。 当您完成该工作区中的工作时，确保取消选择“在后台计算”。

**导出到 Excel**

将工作区数据导出到 Microsoft Excel 中的表格（.xls 和 .xslx 文件）。将工作区导出到 Excel 时，Data Workbench 会将某些可视化、维度和值图例以及文本批注中的数据导出到新的 Excel 工作簿，并且每个工作表对应一个可视化。

**导出到 Excel 模板**

导出到 Excel 模板 (.xltx)。

**Copy**

复制工作区。有关粘贴已复制的工作区的详细信息，请参阅[复制并粘贴现有工作区](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65)。

**还原到服务器版本**

仅对本地版本的服务器工作区显示。删除该工作区的本地副本。原始内容仍然位于服务器上。

**删除**

仅对用户工作区显示。删除仅存在于本地计算机上的用户工作区。有关从连接的Data Workbench服务器中删除工作区的信息，请参阅 [从工作配置文件中删除文件](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b).

**保存到服务器**

仅对本地版本的服务器工作区和用户工作区显示，并且仅适用于具有适当权限的用户。将工作区的本地副本保存到服务器。默认情况下，工作区会保存到相应的工作区 `<profile name>\Workspaces\<tab name>` 文件夹。

**书签**

在工作区中添加书签以便日后快速检索。

书签图标 ![](assets/bookmark_icon.png) 将显示在 Worktop 中工作区的上方，而工作区的名称将显示在“书签”面板中。 ![](assets/bookmark_worktop.png)
