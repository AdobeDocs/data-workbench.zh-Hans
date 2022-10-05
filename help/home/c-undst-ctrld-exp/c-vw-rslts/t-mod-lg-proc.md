---
description: 必须将x-experience字段添加到Log Processing.cfg文件中，该文件用于创建扩展维度。
solution: Analytics
title: 修改 Log Processing.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# 修改 Log Processing.cfg{#modifying-log-processing-cfg}

{{eol}}

必须将x-experience字段添加到Log Processing.cfg文件中，该文件用于创建扩展维度。

请参阅 [修改Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**修改Log Processing.cfg**

1. 在 [!DNL Insight]，打开 [!DNL Profile Manager] 右键单击工作区并单击 **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**，或在 [!DNL Admin] 选项卡。
1. 在 [!DNL Profile Manager]，单击 **[!UICONTROL Dataset]** 以显示其内容。
1. 右键单击旁边的复选标记 [!DNL Log Processing.cfg] 单击 **[!UICONTROL Make Local]**. 此文件的复选标记将显示在 [!DNL User] 列。
1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. 的 [!DNL Log Processing.cfg] 窗口。
1. 单击 **[!UICONTROL Fields]** 以显示其内容。
1. 右键单击当前列表中的最后一个字段，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. 在新创建的字段中键入x-experience，如以下示例所示：

   ![步骤信息](assets/logprocessing.png)

1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.
1. 在 [!DNL Profile Manager]，右键单击的复选标记 [!DNL Log Processing.cfg] 在 [!DNL User] 列，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* 以保存本地对工作配置文件所做的更改。

   >[!NOTE]
   >
   >数据集会立即开始重新处理。

   有关日志处理和字段的详细信息，请参阅 *数据集配置指南*.
