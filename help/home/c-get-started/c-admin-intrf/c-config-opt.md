---
description: “配置”选项打开您的 Insight.cfg 文件，该文件可控制到多个服务器的连接。
solution: Analytics
title: 配置选项
topic: Data workbench
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置选项{#configuration-option}

“配置”选项打开您的 Insight.cfg 文件，该文件可控制到多个服务器的连接。

![](assets/cfg_Workstation.png)

**编辑 Insight.cfg 文件**

1. 在 [!DNL Insight.cfg] 窗口中，根据需要修改各个参数。有关文件中参数的详细说明，请参 [!DNL Insight.cfg] 阅Insight配 [置参数](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。
1. 要保存配置设置，请右键单击窗 **[!UICONTROL Insight.cfg (modified)]** 口顶部的按钮，然后单击 **[!UICONTROL Save as Insight.cfg]**。

**添加新服务器**

1. 在窗 [!DNL Insight.cfg] 口中，右键单击并 **[!UICONTROL Servers]** 单击 **[!UICONTROL Add new child]** > **[!UICONTROL Server]**。

   ![](assets/cfg_Workstation_AddServer.png)

1. 完成或修改服务器参数，使Data Workbench能够访问所需的服务器。 有关文件中参数的详细说明，请参 [!DNL Insight.cfg] 阅Insight配 [置参数](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。
1. 对于要配置连接的每个服务器，重复步骤 1 和步骤 2。
1. 要保存配置设置，请右键单击窗 **[!UICONTROL Insight.cfg (modified)]** 口顶部的按钮，然后单击 **[!UICONTROL Save as Insight.cfg]**。

Data Workbench会尝试使用您指定的设置连接到服务器。 If a connection is established, a green node appears in the [!DNL Servers Manager] as shown below. 如果Data Workbench无法连接到服务器，则会显示一个红色节点。

![](assets/vis_SysStat_RedGreenDots.png)

