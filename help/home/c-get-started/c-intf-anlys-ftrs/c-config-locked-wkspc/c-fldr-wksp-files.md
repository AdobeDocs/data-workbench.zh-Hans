---
description: 在Data Workbench安装目录的Workspaces文件夹中，folder.lock文件指定是否锁定该特定文件夹中的工作区，而工作区名称.lock文件则指定是否锁定特定工作区。
title: Folder.lock 和 workspace.lock 文件
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 35%

---

# Folder.lock 和 workspace.lock 文件{#folder-lock-and-workspace-lock-files}

在Data Workbench安装目录的Workspaces文件夹中，folder.lock文件指定是否锁定该特定文件夹中的工作区，而工作区名称.lock文件则指定是否锁定特定工作区。

当锁定整个文件夹时，您可以在 Workspaces 文件夹级别或子文件夹（选项卡）级别锁定它们。您还可以锁定或解除锁定所有的文件夹（在 Workspaces 文件夹级别），然后指定特定子文件夹（使用 [!DNL folder.lock] 文件）或特定工作区（使用&#x200B;*工作区名称*.lock 文件）的例外情况。

以下[!DNL Profile Manager]示例突出显示了三个元素：

* 主 Workspaces 文件夹对应的 [!DNL folder.lock] 文件
* [!DNL Monthly Numbers.vw]工作区文件的[!DNL Monthly Numbers.lock]文件

* Workspaces\Custom 子文件夹对应的 [!DNL folder.lock] 文件

![](assets/wsp_Locking_lockFiles.png)

在此示例中，[!DNL Workspaces folder.lock]文件被设置为已锁定，这将锁定此Data Workbench实例中的所有工作区。 Workspaces\ 子文件夹 [!DNL folder.lock] 文件被设置为已解锁，这将解除锁定“[!DNL Custom]自定义”选项卡上的所有工作区。最后，[!DNL Monthly Numbers.lock] 文件被设置为已锁定，这将锁定 Monthly Numbers 工作区。

## 创建 .lock 文件 {#section-c4f78b4b43c347368a376904effb41d2}

您可以使用[!DNL Profile Manager]或[!DNL Workspaces Manager]中的[!DNL Create menu]选项创建[!DNL new folder.lock]文件。 您还可以创建[!DNL folder.lock]或&#x200B;*工作区名称*.lock文件，方法是：将现有[!DNL .lock]文件复制并粘贴到相应的文件夹，更改文件名称（仅适用于&#x200B;*工作区名称*.lock文件），并根据需要更改文件中的设置。

**创建新的 folder.lock 文件**

1. 在Data Workbench中，通过右键单击工作区，然后单击&#x200B;**[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**&#x200B;打开[!DNL Workspaces Manager]。
1. 单击您想要创建 [!DNL folder.lock] 文件的文件夹。
1. 在该文件夹的[!DNL User]列中，右键单击单元格，然后单击&#x200B;**[!UICONTROL Create]** > **[!UICONTROL folder.lock]**。 出现[!DNL new folder.lock]文件。 [!DNL New folder.lock] 默认情况下，文件将设 [] 置为unlocked。
1. （可选）如果您需要更改文件中的设置：

   1. 右键单击该文件的复选标记。
   1. 单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 将打开[!DNL folder.lock]文件。

   1. 将设置更改为[locked]。
   1. 保存并关闭该文件。

1. 若要使此设置适用于使用同一工作配置文件的所有用户，请右键单击该文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL working profile name]**>*。

根据新文件中的设置，该文件夹中的工作区现已锁定或解锁。

**从现有文件中创建 .lock 文件**

1. 在[!DNL Profile Manager]或[!DNL Workspaces Manager]中，右键单击现有[!DNL .lock]文件的复选标记，然后单击&#x200B;**[!UICONTROL Copy]**。
1. 在要将[!DNL .lock]文件粘贴到的文件夹的[!DNL User]列中，右键单击单元格，然后单击&#x200B;**[!UICONTROL Paste]**。
1. 如果此文件用于锁定单个工作区，请右键单击[!DNL User]列中[!DNL .lock]文件的复选标记，然后更改[!DNL File]字段中的名称，以匹配要锁定的工作区名称。

   例如，要锁定[!DNL Monthly Numbers.vw]工作区，需将文件命名为“ [!DNL Monthly Numbers.lock]”。如果此文件用于锁定单个工作区，请右键单击[!DNL User]列中[!DNL .lock]文件的复选标记，然后更改[!DNL File]字段中的名称，以匹配要锁定的工作区名称。 例如，要锁定[!DNL Monthly Numbers.vw]工作区，需将文件命名为“ [!DNL Monthly Numbers.lock]”。

1. 若要更改文件中的设置：

   1. 右键单击该文件的复选标记。
   1. 单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 将打开[!DNL .lock]文件。

   1. 将设置更改为[locked]或[unlocked]。
   1. 保存并关闭该文件。

1. 若要使此设置适用于使用同一工作配置文件的所有用户，请右键单击该文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL working profile name]**>*。

根据新文件中的设置，选定工作区现已锁定或解锁。
