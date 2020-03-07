---
description: 必须向Log Processing.cfg文件添加x-experice字段，该文件用于创建扩展维。
solution: Insight,Analytics
title: Modifying Log Processing.cfg
topic: Data workbench
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modifying Log Processing.cfg{#modifying-log-processing-cfg}

必须向Log Processing.cfg文件添加x-experice字段，该文件用于创建扩展维。

请参 [阅修改Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6)。

**修改Log Processing.cfg**

1. 在中， [!DNL Insight]通过在工作 [!DNL Profile Manager] 区中右键单击并单击 **[!UICONTROL Admin]** >，或打开选项卡上的“配置文件管理”工作区， **[!UICONTROL Profile Manager]**&#x200B;打开该工 [!DNL Admin] 作区。
1. 在中， [!DNL Profile Manager]单击以 **[!UICONTROL Dataset]** 显示其内容。
1. 右键单击旁边的复选标记， [!DNL Log Processing.cfg] 然后单击 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.
1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 The [!DNL Log Processing.cfg] window appears.
1. Click **[!UICONTROL Fields]** to show its contents.
1. 右键单击当前列表中的最后一个字段，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Field]**。
1. 在新创建的字段中键入x-experice，如下例所示：

   ![步骤信息](assets/logprocessing.png)

1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。
1. 在中， [!DNL Profile Manager]右键单击列中的复选标记， [!DNL Log Processing.cfg] 然 [!DNL User] 后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* 以保存对工作配置文件进行的本地更改。

   >[!NOTE]
   >
   >数据集会立即开始重新处理。

   有关日志处理和字段的详细信息，请参阅《数据 *集配置指南》*。

