---
description: 在创建并保存报表集文件夹中的工作区后，必须创建新的Report.cfg文件。
solution: Analytics
title: 配置报告集
topic: Data workbench
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置报告集{#configure-the-report-set}

在创建并保存报表集文件夹中的工作区后，必须创建新的Report.cfg文件。

必须在报告集的 [!DNL Report.cfg] 文件中指定生成和分发报告的时间和方式。

**创建新的Report.cfg**

1. 在Data Workbench中，在工 [!DNL Profile Manager] 作区中右键单击，然后单击 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** >打开 **[!UICONTROL Profile Manager]**。
1. 单击 **[!UICONTROL Reports]** 以打开文 [!DNL Reports] 件夹。
1. 单击报告集的文件夹。
1. 在报表 [!DNL User] 集文件夹的列中，右键单击并选择 **[!UICONTROL Create]** > **[!UICONTROL Report]**。 列中将 [!DNL Report.cfg] 显示一个新 [!DNL File]文件。
1. 在新文 [!DNL User] 件的列中，右键 [!DNL Report.cfg] 单击该文件的复选标记，然 [!DNL Report.cfg] 后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。

   ![步骤信息](assets/cfg_reportcfg.png)

1. 根据需要编辑配置参数。 有关这些参数的信息，请参 [阅Report.cfg参数](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

   >[!NOTE]
   >
   >此示例 [!DNL Report.cfg] 中显示的示例默认情况下仅包含文件中包含 [!DNL Report.cfg] 的参数。 如果需要向文件添加其他参 [!DNL Report.cfg] 数，则必须使用文本编辑器。 有关执行此操作的步骤，请参 [阅编辑现有Report.cfg文件](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)。

1. 保存文件，方法是右键单 **[!UICONTROL Report.cfg (modified)]** 击文件顶部，然后单击 **[!UICONTROL另存为报告\]***&lt;**[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**。
1. 关闭文件。
1. 在中， [!DNL Profile Manager]右键单击新文件列中的复选 [!DNL User] 标记，然后 [!DNL Report.cfg] 选择&lt; **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*。
