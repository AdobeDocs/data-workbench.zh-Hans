---
description: DPU配置文件DPU.cfg为Insight Server指定各种性能参数。
title: 配置 DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 5%

---

# 配置 DPU.cfg{#configuring-dpu-cfg}

DPU配置文件DPU.cfg为Insight Server指定各种性能参数。

这些参数的设置方式取决于数据集大小和许多其他因素。 请联系Adobe咨询服务部门，以获取有关性能调整的帮助。

**推荐频度：** 仅在必要时

**更改DPU [!DNL Insight Server] 性能设置**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开“服务器管理器”工作区。
1. 右键单击要配置的[!DNL Insight Server]图标，然后单击&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Components]**&#x200B;以查看其内容。 [!DNL DPU.cfg] 文件位于此目录中。
1. 右键单击&#x200B;*服务器名称*&#x200B;列中[!DNL DPU.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL Temp]列中会出现[!DNL DPU.cfg]的复选标记。
1. 右键单击[!DNL Temp]列中新建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在[!DNL DPU.cfg]窗口中，单击组件以查看其内容。
1. 根据需要更改性能和路径设置。 有关此文件中可用参数的列表，请参阅[DPU性能设置](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1)。

   >[!NOTE]
   >
   >在更改此文件中的任何参数之前，请联系Adobe。

   ![](assets/cfg_DPU_egvalues.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，右键单击[!DNL Temp]列中文件的复选标记，然后选择&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]**>*。
