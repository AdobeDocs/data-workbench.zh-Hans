---
description: “配置”选项打开您的 Insight.cfg 文件，该文件可控制到多个服务器的连接。
title: 配置选项
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 35%

---

# 配置选项{#configuration-option}

“配置”选项打开您的 Insight.cfg 文件，该文件可控制到多个服务器的连接。

![](assets/cfg_Workstation.png)

**编辑 Insight.cfg 文件**

1. 在 [!DNL Insight.cfg] 窗口中，根据需要修改各个参数。有关[!DNL Insight.cfg]文件中参数的详细描述，请参阅[Insight配置参数](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。
1. 要保存配置设置，请右键单击窗口顶部的&#x200B;**[!UICONTROL Insight.cfg (modified)]** ，然后单击&#x200B;**[!UICONTROL Save as Insight.cfg]**。

**添加新服务器**

1. 在[!DNL Insight.cfg]窗口中，右键单击&#x200B;**[!UICONTROL Servers]** ，然后单击&#x200B;**[!UICONTROL Add new child]** > **[!UICONTROL Server]**。

   ![](assets/cfg_Workstation_AddServer.png)

1. 完成或修改服务器参数，以便Data Workbench可以访问所需的服务器。 有关[!DNL Insight.cfg]文件中参数的详细描述，请参阅[Insight配置参数](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。
1. 对于要配置连接的每个服务器，重复步骤 1 和步骤 2。
1. 要保存配置设置，请右键单击窗口顶部的&#x200B;**[!UICONTROL Insight.cfg (modified)]** ，然后单击&#x200B;**[!UICONTROL Save as Insight.cfg]**。

Data Workbench尝试使用您指定的设置连接到服务器。 如果已建立连接，则[!DNL Servers Manager]中会显示一个绿色节点，如下所示。 如果Data Workbench无法连接到服务器，则会显示一个红色节点。

![](assets/vis_SysStat_RedGreenDots.png)
