---
description: 默认情况下，新创建的选项卡将相关联目录中的子文件夹显示为分层的下拉子目录，而不是子选项卡。
title: 将子文件夹显示为子选项卡
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 29%

---

# 将子文件夹显示为子选项卡{#display-subfolders-as-subtabs}

默认情况下，新创建的选项卡将相关联目录中的子文件夹显示为分层的下拉子目录，而不是子选项卡。

您可以将子文件夹显示为子选项卡（如以下示例所示），方法是将[!DNL empty folder.useTabs]文件放在&#x200B;*工作配置文件名称*\Workspaces\*tab name文件夹*的Data Workbench安装目录内。

以下示例显示了包含下拉子目录的[!DNL Custom]选项卡。

![](assets/client-sub.png)

如果将[!DNL empty folder.useTabs]文件放在Workspaces\Custom文件夹中，则Custom文件夹中的所有子文件夹都会在[!DNL Worktop]中显示为子选项卡，如以下示例所示：

![](assets/client-sub2.png)

**在[!DNL Worktop]** 中将子文件夹显示为子选项卡

>[!NOTE]
>
>每个目录级别都必须有一个[!DNL Tab Name.useTabs]文件，子文件夹的内容才会显示为子选项卡，而不是分层的下拉子目录。

1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Workspaces]**&#x200B;以查看其内容。
1. 在&#x200B;*工作配置文件名称*&#x200B;列中，右键单击其中一个[!DNL folder.useTabs]文件的复选标记，然后单击&#x200B;**[!UICONTROL Copy]**。
1. 右键单击“工作区”\*选项卡名称*文件夹的[!DNL User]列，然后单击&#x200B;**[!UICONTROL Paste]**。 现在选项卡中的子文件夹将显示为子选项卡。
1. （可选）若要使此更改对工作配置文件的所有用户可用，请右键单击[!DNL User]列中[!DNL new folder.useTabs]文件的白色复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL working profile name]**>。
