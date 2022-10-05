---
description: 转换功能在Insight Server FSU计算机上运行，以允许导出日志源数据以供其他应用程序使用。
title: 配置转换
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 12%

---

# 配置转换{#configuring-transform}

{{eol}}

转换功能在Insight Server FSU计算机上运行，以允许导出日志源数据以供其他应用程序使用。

[!DNL Transform] 可读 [!DNL .vsl] 文件、日志文件、 XML文件和ODBC数据，并将数据导出为 [!DNL .vsl] 可供data warehouse加载例程、审计代理或其他目标使用的文件、文本文件或分隔文本文件。 数据提取和转换可以连续执行，也可以按计划执行。每个 [!DNL Insight Server] 必须运行提供已更改事件数据输出的FSU [!DNL Transform].

>[!NOTE]
>
>通常， [!DNL Transform] 安装在 [!DNL Insight Server] FSU。 但是，您的实施可能需要在 [!DNL Insight Server] DPU。 有关详细信息，请联系 Adobe。

有关安装、配置和运行 [!DNL Transform] 的系统要求的信息，请参阅“最低系统要求”**&#x200B;文档。

Adobe分发 [!DNL Transform] 功能作为 [!DNL .zip] 文件 [!DNL Insight Server] 发行包。 的 [!DNL Transform] 配置文件是内部配置文件，可为 [!DNL Insight Server]. 与Adobe提供的所有其他内部用户档案一样，不应更改用户档案。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

配置文件包含以下文件：

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* 日志处理数据集包含文件

所有这些文件都位于 [!DNL Dataset] 文件夹。

**安装 [!DNL Transform] 个人资料[!DNL Insight Server]**

>[!NOTE]
>
>以下安装说明假定您已安装 [!DNL Insight] 并在 [!DNL Insight] 和 [!DNL Insight Server] 安装位置 [!DNL Transform]. 如果您尚未执行此操作，请参阅* [!DNL Insight] 用户指南*。

1. 打开 [!DNL .zip] 文件 [!DNL Insight Server] 版本包，然后打开 [!DNL Profiles] 文件夹 [!DNL .zip] 文件。
1. 复制 [!DNL Transform] 文件夹 [!DNL Profiles] 文件夹中 [!DNL Insight Server] 安装目录。 你最后想用 [!DNL ...\Profiles\Transform] 文件夹 [!DNL Insight Server] 如以下示例中所示。

   ![步骤信息](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >如果您执行了安装的所有步骤 [!DNL Insight Server] (请参阅 [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)) [!DNL Transform] 文件夹。

1. 请按照以下步骤更新 [!DNL profile.cfg] 文件 [!DNL Transform]. 完成这些步骤后，数据集将重新处理。

   1. 打开 [!DNL Profile Manager].
   1. 右键单击旁边的复选标记 [!DNL profile.cfg] 单击 **[!UICONTROL Make Local]**. 此文件的复选标记将显示在 [!DNL User] 列。

   1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. 的 [!DNL profile.cfg] 窗口。

   1. 在 [!DNL profile.cfg]窗口，右键单击 **[!UICONTROL Directories]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      要将新目录添加到目录列表末尾，请右键单击列表中最后一个目录的编号或名称，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. 键入新目录的名称： [!DNL Transform]
   1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

   1. 在 [!DNL Profile Manager]，右键单击的复选标记 [!DNL profile.cfg] 在 [!DNL User] 列，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >请勿将修改的配置文件保存到Adobe提供的任何内部配置文件（包括配置文件）中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。
