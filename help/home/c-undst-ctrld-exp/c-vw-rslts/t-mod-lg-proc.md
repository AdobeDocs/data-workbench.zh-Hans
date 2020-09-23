---
description: 必须向Log Processing.cfg文件添加x-experice字段，该文件用于创建扩展维。
solution: Analytics,Analytics
title: 修改 Log Processing.cfg
topic: Data workbench
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---


# 修改 Log Processing.cfg{#modifying-log-processing-cfg}

必须向Log Processing.cfg文件添加x-experice字段，该文件用于创建扩展维。

请参 [阅修改Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6)。

**修改Log Processing.cfg**

1. 在中 [!DNL Insight]，通过 [!DNL Profile Manager] 在工作区中右键单击并单击> **[!UICONTROL Admin]** 或打 **[!UICONTROL Profile Manager]**&#x200B;开选项卡上的“用户档案管理”工作 [!DNL Admin] 区打开。
1. 在中， [!DNL Profile Manager]单击 **[!UICONTROL Dataset]** 以显示其内容。
1. 右键单击旁边的复选标 [!DNL Log Processing.cfg] 记，然后单 **[!UICONTROL Make Local]**&#x200B;击。 A check mark for this file appears in the [!DNL User] column.
1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 The [!DNL Log Processing.cfg] window appears.
1. Click **[!UICONTROL Fields]** to show its contents.
1. 右键单击当前列表中的最后一个字段，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Field]**。
1. 在新创建的字段中键入x-experice，如以下示例所示：

   ![步骤信息](assets/logprocessing.png)

1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。
1. 在列 [!DNL Profile Manager]中，右键单击该复选标 [!DNL Log Processing.cfg] 记，然 [!DNL User] 后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]*** >以保存对工作用户档案进行的本地更改。

   >[!NOTE]
   >
   >数据集会立即开始重新处理。

   有关日志处理和字段的详细信息，请参 *阅《数据集配置指南》*。

