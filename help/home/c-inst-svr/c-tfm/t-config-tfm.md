---
description: 转换功能在Insight Server FSU计算机上运行，以启用日志源数据的导出以供其他应用程序使用。
solution: Analytics
title: 配置转换
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 12%

---


# 配置转换{#configuring-transform}

转换功能在Insight Server FSU计算机上运行，以启用日志源数据的导出以供其他应用程序使用。

[!DNL Transform] 可以读 [!DNL .vsl] 取文件、日志文件、XML文件和ODBC数据，并将数据导出为文件、文本文件或分隔文本文件，这些文 [!DNL .vsl] 件可以由data warehouse加载例程、审计机构或其他目标使用。 数据提取和转换可以连续执行，也可以按计划执行。提供 [!DNL Insight Server] 已更改事件数据输出的每个FSU必须运行 [!DNL Transform]。

>[!NOTE]
>
>通常 [!DNL Transform] 安装在FSU [!DNL Insight Server] 上。 However, your implementation may require installation on an [!DNL Insight Server] DPU. 有关详细信息，请联系 Adobe。

有关安装、配置和运行 [!DNL Transform] 的系统要求的信息，请参阅“最低系统要求”**&#x200B;文档。

Adobe将功 [!DNL Transform] 能作为用户档案分发到发 [!DNL .zip] 行包的文 [!DNL Insight Server] 件中。 该 [!DNL Transform] 用户档案是内部用户档案，可提供附加功能 [!DNL Insight Server]。 与Adobe提供的所有其他内部用户档案一样，用户档案不应更改。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

用户档案包含以下文件：

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* 日志处理数据集包含文件

所有这些文件都位于 [!DNL Dataset] 用户档案的文件夹中。

**安装[!DNL Transform]用户档案[!DNL Insight Server]**

>[!NOTE]
>
>以下安装说明假定您已经 [!DNL Insight] 在安装位置和安装 [!DNL Insight] 位置 [!DNL Insight Server] 之间建立了连接 [!DNL Transform]。 如果尚未这样做，请参阅* [!DNL Insight] 用户指南*。

1. 打开发 [!DNL .zip] 行包的文 [!DNL Insight Server] 件，并打开该文 [!DNL Profiles] 件中的文 [!DNL .zip] 件夹。
1. 将文件夹 [!DNL Transform] 复制到安 [!DNL Profiles] 装目录中的 [!DNL Insight Server] 文件夹中。 您希望最终在您的文件 [!DNL ...\Profiles\Transform] 夹上显示一 [!DNL Insight Server] 个文件夹，如以下示例所示。

   ![步骤信息](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >如果遵循了安装的所有步骤(请 [!DNL Insight Server] 参 [阅Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md))，则您可能已在 [!DNL Transform] 用户档案目录中有一个文件夹。

1. 请按照以下步骤 [!DNL profile.cfg] 更新要使用的用户档案的文件 [!DNL Transform]。 完成这些步骤后，数据集将重新处理。

   1. 打开 [!DNL Profile Manager].
   1. 右键单击旁边的复选标 [!DNL profile.cfg] 记，然后单 **[!UICONTROL Make Local]**&#x200B;击。 A check mark for this file appears in the [!DNL User] column.

   1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 The [!DNL profile.cfg] window appears.

   1. 在窗 [!DNL profile.cfg]口中，右键单 **[!UICONTROL Directories]** 击，然后 **[!UICONTROL Add new]** 单击> **[!UICONTROL Directory]**。

      要将新目录添加到目录列表的末尾，请右键单击列表中最后一个目录的编号或名称，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 键入新目录的名称： [!DNL Transform]
   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在列 [!DNL Profile Manager]中，右键单击列中的复 [!DNL profile.cfg] 选 [!DNL User] 标记，然后单 **[!UICONTROL Save to]** 击> *&lt;**[!UICONTROL profile name]**>*。

      >[!NOTE]
      >
      >请勿将修改后的配置文件保存到Adobe提供的任何内部用户档案(包括用户档案)，因为当您安装对这些用户档案的更新时，您所做的更改将被覆盖。

