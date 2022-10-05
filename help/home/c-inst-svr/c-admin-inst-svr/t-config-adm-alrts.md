---
description: 当Insight Server在正常操作过程中检测到错误时，管理警报会向指定的电子邮件地址发送电子邮件通知。
title: 配置管理警报
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 5%

---

# 配置管理警报{#configuring-administrative-alerts}

{{eol}}

当Insight Server在正常操作过程中检测到错误时，管理警报会向指定的电子邮件地址发送电子邮件通知。

**推荐频率：** 生产前

>[!NOTE]
>
>使用管理警报时，需要 [!DNL Insight Server] 有权访问转发SMTP服务器以通过电子邮件发送警报。

电子邮件通知的收件人应为主要系统管理人员和主要利益相关方。

管理警报文件， [!DNL Administrative Alerts.cfg]，用于为配置管理警报 [!DNL Insight Server].

>[!NOTE]
>
>如果您运行的是群集，则必须在主控上创建或修改警报 [!DNL Insight Server] 在群集中。

**创建或修改管理警报**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，单击 **[!UICONTROL Servers Manager]** 缩略图以打开“服务器管理器”工作区。
1. 右键单击 [!DNL Insight Server] 要配置并单击 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，单击 **[!UICONTROL Components]** 查看其内容。 [!DNL Administrative Alerts.cfg] 文件位于此目录中。
1. 右键单击*服务器名称*列中的复选标记，即 [!DNL Administrative Alerts.cfg] 单击 **[!UICONTROL Make Local]**. 在 [!DNL Temp] 列 [!DNL Administrative Alerts.cfg].
1. 右键单击 [!DNL Temp] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 在 [!DNL Administrative Alerts.cfg] 窗口，单击 **[!UICONTROL component]** 查看其内容。
1. 根据需要填写参数。 有关此文件中可用参数的列表，请参阅 [管理警报配置设置](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![步骤信息](assets/cfg_adminalerts_examplevalues.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，右键单击 [!DNL Temp] 列和选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. （可选）如果您在群集中工作，并且希望将相同的管理警报应用于每个数据处理单元，则必须复制并粘贴更新的 [!DNL Administrative Alerts.cfg] 文件 [!DNL Components for Processing Servers] 文件夹(位于主控 [!DNL Insight Server] 安装目录。
