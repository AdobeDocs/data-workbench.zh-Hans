---
description: 当Insight Server在正常操作过程中检测到错误时，管理警报会向指定的电子邮件地址发送电子邮件通知。
title: 配置管理警报
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 5%

---

# 配置管理警报{#configuring-administrative-alerts}

当Insight Server在正常操作过程中检测到错误时，管理警报会向指定的电子邮件地址发送电子邮件通知。

**推荐频度：** 在生产之前

>[!NOTE]
>
>使用管理警报要求[!DNL Insight Server]有权访问转发SMTP服务器以通过电子邮件发送警报。

电子邮件通知的收件人应为主要系统管理人员和主要利益相关方。

管理警报文件[!DNL Administrative Alerts.cfg]用于配置[!DNL Insight Server]的管理警报。

>[!NOTE]
>
>如果您运行的是群集，则必须在群集中的主控[!DNL Insight Server]上创建或修改警报。

**创建或修改管理警报**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开“服务器管理器”工作区。
1. 右键单击要配置的[!DNL Insight Server]图标，然后单击&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Components]**&#x200B;以查看其内容。 [!DNL Administrative Alerts.cfg] 文件位于此目录中。
1. 右键单击[!DNL Administrative Alerts.cfg]的*服务器名称*列中的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL Temp]列中会出现[!DNL Administrative Alerts.cfg]的复选标记。
1. 右键单击[!DNL Temp]列中新建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在[!DNL Administrative Alerts.cfg]窗口中，单击&#x200B;**[!UICONTROL component]**&#x200B;以查看其内容。
1. 根据需要填写参数。 有关此文件中可用参数的列表，请参阅[管理警报配置设置](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491)。

   ![步骤信息](assets/cfg_adminalerts_examplevalues.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，右键单击[!DNL Temp]列中文件的复选标记，然后选择&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]**>*。

1. （可选）如果您在群集中工作，并且希望对每个数据处理单元应用相同的管理警报，则必须将更新的[!DNL Administrative Alerts.cfg]文件复制并粘贴到主控[!DNL Insight Server]安装目录的[!DNL Components for Processing Servers]文件夹中。
