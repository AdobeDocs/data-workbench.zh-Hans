---
description: 通信配置文件Communications.cfg包含Insight Server网络设置和Access Control.cfg文件的路径。
title: 配置通信
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# 配置通信{#configuring-communications}

通信配置文件Communications.cfg包含Insight Server网络设置和Access Control.cfg文件的路径。

这些设置可帮助您连接到[!DNL Insight Server]。

**推荐频度：** 仅在必要时

**要查看和修改[!DNL Insight]**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开“服务器管理器”工作区。
1. 右键单击要配置的[!DNL Insight Server]图标，然后单击&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Components]**&#x200B;以查看其内容。 [!DNL Communications.cfg] 文件位于此目录中。
1. 右键单击&#x200B;*服务器名称*&#x200B;列中[!DNL Communications.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL Temp]列中会出现[!DNL Communications.cfg]的复选标记。
1. 右键单击[!DNL Temp]列中新建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在[!DNL Communications.cfg]窗口中，单击&#x200B;**[!UICONTROL component]**&#x200B;以查看其内容。
1. 根据需要更改设置。 有关此文件中可用参数的信息，请参阅[通信配置设置](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1)。

   ![步骤信息](assets/cfg_communications_examplevalues.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，右键单击[!DNL Temp]列中文件的复选标记，然后选择&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]**>*。
