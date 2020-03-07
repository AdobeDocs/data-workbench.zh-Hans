---
description: 转换功能在Insight Server FSU计算机上运行，以支持导出日志源数据以供其他应用程序使用。
solution: Insight
title: 配置转换
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 配置转换{#configuring-transform}

转换功能在Insight Server FSU计算机上运行，以支持导出日志源数据以供其他应用程序使用。

[!DNL Transform] 可以读 [!DNL .vsl][!DNL .vsl] 取文件、日志文件、XML文件和ODBC数据，并将数据导出为文件、文本文件或分隔文本文件，这些文件可以由数据仓库加载例程、审计机构或其他目标使用。 数据提取和转换可以连续执行，也可以按计划执行。必须 [!DNL Insight Server] 运行每个提供已更改事件数据输出的FSU [!DNL Transform]。

>[!NOTE]
>
>通常， [!DNL Transform] 安装在 [!DNL Insight Server] FSU上。 However, your implementation may require installation on an [!DNL Insight Server] DPU. 有关详细信息，请联系 Adobe。

有关安装、配置和运行 [!DNL Transform] 的系统要求的信息，请参阅“最低系统要求”**&#x200B;文档。

Adobe将功能 [!DNL Transform] 作为发布包的文件 [!DNL .zip] 中的配置文 [!DNL Insight Server] 件分发。 该配 [!DNL Transform] 置文件是内部配置文件，可为其提供附加功能 [!DNL Insight Server]。 与Adobe提供的所有其他内部配置文件一样，不应更改配置文件。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

配置文件由以下文件组成：

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* 日志处理数据集包含文件

所有这些文件都位于配置文 [!DNL Dataset] 件的文件夹中。

**在上安装[!DNL Transform]配置文件[!DNL Insight Server]**

>[!NOTE]
>
>以下安装说明假定您已经 [!DNL Insight] 在安装位置和安装位置之 [!DNL Insight] 间 [!DNL Insight Server] 建立了连接 [!DNL Transform]。 如果尚未这样做，请参阅*用 [!DNL Insight] 户指南*。

1. 打开发 [!DNL .zip] 行包的文 [!DNL Insight Server] 件，并打开该文件 [!DNL Profiles] 中的文件 [!DNL .zip] 夹。
1. 将文件 [!DNL Transform] 夹复制到安 [!DNL Profiles] 装目录中 [!DNL Insight Server] 的文件夹。 您希望最终在您的文件 [!DNL ...\Profiles\Transform] 夹上找到一个 [!DNL Insight Server] 文件夹，如以下示例所示。

   ![步骤信息](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >如果遵循了安装的所有步骤(请参 [!DNL Insight Server] 阅 [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md))，则Profiles目录中可能已有 [!DNL Transform] 一个文件夹。

1. 使用以下步骤更新 [!DNL profile.cfg] 要使用的配置文件的文件 [!DNL Transform]。 完成这些步骤后，数据集将重新处理。

   1. 打开 [!DNL Profile Manager].
   1. 右键单击旁边的复选标记， [!DNL profile.cfg] 然后单击 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.

   1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 The [!DNL profile.cfg] window appears.

   1. 在窗 [!DNL profile.cfg]口中，右键单击并 **[!UICONTROL Directories]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要将新目录添加到目录列表的末尾，请右键单击列表中最后一个目录的编号或名称，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 键入新目录的名称： [!DNL Transform]
   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在列 [!DNL Profile Manager]中，右键单击列中的复 [!DNL profile.cfg] 选 [!DNL User] 标记，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

      >[!NOTE]
      >
      >请勿将修改后的配置文件保存到Adobe提供的任何内部配置文件（包括配置文件）中，因为当您安装这些配置文件的更新时，您所做的更改会被覆盖。

