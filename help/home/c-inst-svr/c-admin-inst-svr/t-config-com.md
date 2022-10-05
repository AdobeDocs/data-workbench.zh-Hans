---
description: 通信配置文件Communications.cfg包含Insight Server网络设置和Access Control.cfg文件的路径。
title: 配置通信
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# 配置通信{#configuring-communications}

{{eol}}

通信配置文件Communications.cfg包含Insight Server网络设置和Access Control.cfg文件的路径。

这些设置可帮助您连接到 [!DNL Insight Server].

**推荐频率：** 仅在必要时

**要查看和修改[!DNL Insight]**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，单击 **[!UICONTROL Servers Manager]** 缩略图以打开“服务器管理器”工作区。
1. 右键单击 [!DNL Insight Server] 要配置并单击 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，单击 **[!UICONTROL Components]** 查看其内容。 [!DNL Communications.cfg] 文件位于此目录中。
1. 右键单击 *服务器名称* 列 [!DNL Communications.cfg] 单击 **[!UICONTROL Make Local]**. 在 [!DNL Temp] 列 [!DNL Communications.cfg].
1. 右键单击 [!DNL Temp] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 在 [!DNL Communications.cfg] 窗口，单击 **[!UICONTROL component]** 查看其内容。
1. 根据需要更改设置。 有关此文件中可用参数的信息，请参阅 [通信配置设置](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![步骤信息](assets/cfg_communications_examplevalues.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，右键单击 [!DNL Temp] 列和选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
