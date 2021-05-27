---
description: 在报表集文件夹中创建并保存工作区后，必须新建一个Report.cfg文件。
title: 配置报表集
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# 配置报表集{#configure-the-report-set}

在报表集文件夹中创建并保存工作区后，必须新建一个Report.cfg文件。

必须在[!DNL Report.cfg]文件中为报表集指定何时以及如何生成和分发报表。

**创建新Report.cfg**

1. 在Data Workbench中，通过右键单击工作区，然后单击&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**，打开[!DNL Profile Manager]。
1. 单击&#x200B;**[!UICONTROL Reports]**&#x200B;以打开[!DNL Reports]文件夹。
1. 单击报表集的文件夹。
1. 在报表集文件夹的[!DNL User]列中，右键单击并选择&#x200B;**[!UICONTROL Create]** > **[!UICONTROL Report]**。 新的[!DNL Report.cfg]文件将显示在[!DNL File]列中。
1. 在新[!DNL Report.cfg]文件的[!DNL User]列中，右键单击[!DNL Report.cfg]文件的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。

   ![步骤信息](assets/cfg_reportcfg.png)

1. 根据需要编辑配置参数。 有关这些参数的信息，请参阅[Report.cfg参数](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

   >[!NOTE]
   >
   >默认情况下，此示例中显示的示例[!DNL Report.cfg]仅包含[!DNL Report.cfg]文件中包含的参数。 如果需要向[!DNL Report.cfg]文件添加其他参数，则必须使用文本编辑器来添加。 有关执行此操作的步骤，请参阅[编辑现有Report.cfg文件](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)。

1. 右键单击文件顶部的&#x200B;**[!UICONTROL Report.cfg (modified)]**&#x200B;并单击&#x200B;**[!UICONTROL Save as Reports\]***&lt;**[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**保存文件。
1. 关闭文件。
1. 在[!DNL Profile Manager]中，右键单击新[!DNL Report.cfg]文件[!DNL User]列中的复选标记，然后选择&#x200B;**[!UICONTROL Save to]*****[!UICONTROL profile name]**>*。
