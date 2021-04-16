---
description: 默认情况下，新创建的选项卡将相关联目录中的子文件夹显示为分层的下拉子目录，而不是子选项卡。
title: 将子文件夹显示为子选项卡
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 29%

---

# 将子文件夹显示为子选项卡{#display-subfolders-as-subtabs}

默认情况下，新创建的选项卡将相关联目录中的子文件夹显示为分层的下拉子目录，而不是子选项卡。

通过将[!DNL empty folder.useTabs]文件放在Data Workbench安装目录中的工作用户档案名称&#x200B;*\Workspaces\*tab名称文件夹*中，可以将子文件夹显示为子选项卡（如下例所示）。*

以下示例显示了带有下拉子目录的[!DNL Custom]选项卡。

![](assets/client-sub.png)

如果将[!DNL empty folder.useTabs]文件放在Workspaces\Custom文件夹中，则Custom文件夹内的所有子文件夹都将作为子选项卡显示在[!DNL Worktop]中，如下例所示：

![](assets/client-sub2.png)

**在[!DNL Worktop]** 中将子文件夹显示为子选项卡

>[!NOTE]
>
>每个目录级别都必须有一个[!DNL Tab Name.useTabs]文件，子文件夹的内容才能显示为子选项卡，而不是分层的下拉子目录。

1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Workspaces]**&#x200B;视图其内容。
1. 在&#x200B;*工作用户档案名称*&#x200B;列中，右键单击其中一个[!DNL folder.useTabs]文件的复选标记，然后单击&#x200B;**[!UICONTROL Copy]**。
1. 右键单击Workspaces\*tab name*文件夹的[!DNL User]列，然后单击&#x200B;**[!UICONTROL Paste]**。 现在选项卡中的子文件夹将显示为子选项卡。
1. （可选）要使此更改对工作用户档案的所有用户可用，请右键单击[!DNL User]列中[!DNL new folder.useTabs]文件的白色复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**。
