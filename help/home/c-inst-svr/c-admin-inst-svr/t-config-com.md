---
description: 通信配置文件Communications.cfg包含Insight Server网络设置和访问控制.cfg文件的路径。
solution: Analytics
title: 配置通信
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---


# 配置通信{#configuring-communications}

通信配置文件Communications.cfg包含Insight Server网络设置和访问控制.cfg文件的路径。

这些设置可帮助您连接到 [!DNL Insight Server]。

**推荐频率：** 仅在必要时

**视图和修改[!DNL Insight]**

1. 在> [!DNL Insight]选项卡上 [!DNL Admin] ，单 [!DNL Dataset and Profile] 击缩略图以打 **[!UICONTROL Servers Manager]** 开“服务器管理器”工作区。
1. 右键单击要配置的 [!DNL Insight Server] 图标，然后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击 **[!UICONTROL Components]** 以视图其内容。 [!DNL Communications.cfg] 文件位于此目录中。
1. Right-click the check mark in the *server name* column for [!DNL Communications.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Communications.cfg].
1. 右键单击列中新创建的复选标 [!DNL Temp] 记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在窗口 [!DNL Communications.cfg] 中，单击 **[!UICONTROL component]** 以视图其内容。
1. 根据需要更改设置。 有关此文件中可用参数的信息，请参 [阅通信配置设置](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1)。

   ![步骤信息](assets/cfg_communications_examplevalues.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]右键单击列中文件的复选标记， [!DNL Temp] 然后选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

