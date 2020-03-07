---
description: 管理警报会在Insight Server在正常操作过程中检测到错误时，向指定的电子邮件地址发送电子邮件通知。
solution: Insight
title: 配置管理警报
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置管理警报{#configuring-administrative-alerts}

管理警报会在Insight Server在正常操作过程中检测到错误时，向指定的电子邮件地址发送电子邮件通知。

**推荐频率：** 生产前

>[!NOTE]
>
>使用管理警报时，需要有权 [!DNL Insight Server] 访问转发SMTP服务器以通过电子邮件发送警报。

电子邮件通知的收件人应是主要系统管理人员和主要利益相关方。

管理警报文件 [!DNL Administrative Alerts.cfg]用于配置管理警报 [!DNL Insight Server]。

>[!NOTE]
>
>如果运行群集，则必须在群集中的主设备上创建或修改 [!DNL Insight Server] 警报。

**创建或修改管理警报**

1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。
1. 右键单击要配置的 [!DNL Insight Server] 图标，然后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Components]** 查看其内容。 [!DNL Administrative Alerts.cfg] 文件位于此目录中。
1. 右键单击*服务器名称*列中的复选标记，然 [!DNL Administrative Alerts.cfg] 后单击 **[!UICONTROL Make Local]**。 A check mark appears in the [!DNL Temp] column for [!DNL Administrative Alerts.cfg].
1. 右键单击列中新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在窗 [!DNL Administrative Alerts.cfg] 口中，单 **[!UICONTROL component]** 击以查看其内容。
1. 根据需要填写参数。 有关此文件中可用参数的列表，请参阅管理 [警报配置设置](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491)。

   ![步骤信息](assets/cfg_adminalerts_examplevalues.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]右键单击列中文件的复选标记，然 [!DNL Temp] 后选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

1. （可选）如果您在群集中工作，并且希望对每个数据处理单元应用相同的管理警报，则必须将更新后的文件复制并粘贴到主安装目录 [!DNL Administrative Alerts.cfg] 内 [!DNL Components for Processing Servers] 的文件 [!DNL Insight Server] 夹中。
