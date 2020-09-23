---
description: 管理警报在正常操作过程中，当Insight Server检测到错误时，会将电子邮件通知发送到指定的电子邮件地址。
solution: Analytics
title: 配置管理警报
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 5%

---


# 配置管理警报{#configuring-administrative-alerts}

管理警报在正常操作过程中，当Insight Server检测到错误时，会将电子邮件通知发送到指定的电子邮件地址。

**推荐频率：** 生产前

>[!NOTE]
>
>使用管理警报时，需要 [!DNL Insight Server] 有权访问转发SMTP服务器以通过电子邮件发送警报。

电子邮件通知的收件人应为主要系统管理人员和主要利益相关者。

管理警报文 [!DNL Administrative Alerts.cfg]件用于配置管理警报 [!DNL Insight Server]。

>[!NOTE]
>
>如果运行的是群集，则必须在群集中的主控上创建或修改 [!DNL Insight Server] 警报。

**创建或修改管理警报**

1. 在> [!DNL Insight]选项卡上 [!DNL Admin] ，单 [!DNL Dataset and Profile] 击缩略图以打 **[!UICONTROL Servers Manager]** 开“服务器管理器”工作区。
1. 右键单击要配置的 [!DNL Insight Server] 图标，然后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击 **[!UICONTROL Components]** 以视图其内容。 [!DNL Administrative Alerts.cfg] 文件位于此目录中。
1. 右键单击*服务器名称*列中的复选标记， [!DNL Administrative Alerts.cfg] 然后单击 **[!UICONTROL Make Local]**。 A check mark appears in the [!DNL Temp] column for [!DNL Administrative Alerts.cfg].
1. 右键单击列中新创建的复选标 [!DNL Temp] 记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在窗口 [!DNL Administrative Alerts.cfg] 中，单击 **[!UICONTROL component]** 以视图其内容。
1. 根据需要填写参数。 有关此文件中可用参数的列表，请参阅管 [理警报配置设置](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491)。

   ![步骤信息](assets/cfg_adminalerts_examplevalues.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]右键单击列中文件的复选标记， [!DNL Temp] 然后选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

1. （可选）如果您在群集中工作，并且希望对每个数据处理单元应用相同的管理警报，则必须将更新后的文件复制并 [!DNL Administrative Alerts.cfg] 粘贴到主控安 [!DNL Components for Processing Servers] 装目录中的 [!DNL Insight Server] 文件夹中。
