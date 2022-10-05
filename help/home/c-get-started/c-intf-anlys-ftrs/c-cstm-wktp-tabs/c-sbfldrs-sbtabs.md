---
description: 默认情况下，新创建的选项卡将相关联目录中的子文件夹显示为分层的下拉子目录，而不是子选项卡。
title: 将子文件夹显示为子选项卡
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 29%

---

# 将子文件夹显示为子选项卡{#display-subfolders-as-subtabs}

{{eol}}

默认情况下，新创建的选项卡将相关联目录中的子文件夹显示为分层的下拉子目录，而不是子选项卡。

您可以通过在子选项卡中放置 [!DNL empty folder.useTabs] 文件 *工作配置文件名称*\Workspaces\*选项卡名称文件夹*，位于Data Workbench安装目录内。

以下示例显示了 [!DNL Custom] 选项卡。

![](assets/client-sub.png)

如果您将 [!DNL empty folder.useTabs] 文件，“自定义”文件夹中的所有子文件夹都显示在 [!DNL Worktop] 作为子选项卡，如以下示例中所示：

![](assets/client-sub2.png)

**在[!DNL Worktop]** 中将子文件夹显示为子选项卡

>[!NOTE]
>
>每个目录级别必须具有 [!DNL Tab Name.useTabs] 子文件夹内容的文件显示为子选项卡，而不是分层的下拉子目录。

1. 在 [!DNL Profile Manager]，单击 **[!UICONTROL Workspaces]** 查看其内容。
1. 在 *工作配置文件名称* 列中，右键单击其中一个 [!DNL folder.useTabs] 文件，单击 **[!UICONTROL Copy]**.
1. 在 [!DNL User] “工作区”\*选项卡名称*文件夹的列，然后单击 **[!UICONTROL Paste]**. 现在选项卡中的子文件夹将显示为子选项卡。
1. （可选）若要使此更改对工作配置文件的所有用户可用，请右键单击 [!DNL new folder.useTabs] 文件 [!DNL User] 列，单击 **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**> 。
