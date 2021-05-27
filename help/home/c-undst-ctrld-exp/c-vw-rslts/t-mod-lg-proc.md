---
description: 必须将x-experience字段添加到Log Processing.cfg文件中，该文件用于创建扩展维度。
solution: Analytics,Analytics
title: 修改 Log Processing.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# 修改 Log Processing.cfg{#modifying-log-processing-cfg}

必须将x-experience字段添加到Log Processing.cfg文件中，该文件用于创建扩展维度。

请参阅[Modifying Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6)。

**修改Log Processing.cfg**

1. 在[!DNL Insight]中，打开[!DNL Profile Manager]，方法是：在工作区中右键单击并单击&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**，或在[!DNL Admin]选项卡上打开“配置文件管理”工作区。
1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Dataset]**&#x200B;以显示其内容。
1. 右键单击[!DNL Log Processing.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中将显示此文件的复选标记。
1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 出现[!DNL Log Processing.cfg]窗口。
1. 单击&#x200B;**[!UICONTROL Fields]**&#x200B;以显示其内容。
1. 右键单击当前列表中的最后一个字段，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Field]**。
1. 在新创建的字段中键入x-experience，如以下示例所示：

   ![步骤信息](assets/logprocessing.png)

1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Profile Manager]中，右键单击[!DNL User]列中[!DNL Log Processing.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>*&#x200B;以保存本地对工作配置文件所做的更改。

   >[!NOTE]
   >
   >数据集会立即开始重新处理。

   有关日志处理和字段的详细信息，请参阅&#x200B;*Dataset Configuration Guide*。
