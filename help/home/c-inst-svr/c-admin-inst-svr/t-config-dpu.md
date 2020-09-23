---
description: DPU配置文件DPU.cfg为Insight Server指定各种性能参数。
solution: Analytics
title: 配置 DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 5%

---


# 配置 DPU.cfg{#configuring-dpu-cfg}

DPU配置文件DPU.cfg为Insight Server指定各种性能参数。

设置这些参数的方式取决于数据集大小和许多其他因素。 请与Adobe咨询服务部门联系，以获得性能调整方面的帮助。

**推荐频率：** 仅在必要时

**更改DPU[!DNL Insight Server]性能设置**

1. 在> [!DNL Insight]选项卡上 [!DNL Admin] ，单 [!DNL Dataset and Profile] 击缩略图以打 **[!UICONTROL Servers Manager]** 开“服务器管理器”工作区。
1. 右键单击要配置的 [!DNL Insight Server] 图标，然后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击 **[!UICONTROL Components]** 以视图其内容。 [!DNL DPU.cfg] 文件位于此目录中。
1. Right-click the check mark in the *server name* column for [!DNL DPU.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL DPU.cfg].
1. 右键单击列中新创建的复选标 [!DNL Temp] 记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. In the [!DNL DPU.cfg] window, click component to view its contents.
1. 根据需要更改性能和路径设置。 有关此文件中可用参数的列表，请参阅 [DPU性能设置](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1)。

   >[!NOTE]
   >
   >请在更改此文件中的任何参数之前与Adobe联系。

   ![](assets/cfg_DPU_egvalues.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]右键单击列中文件的复选标记， [!DNL Temp] 然后选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

