---
description: 使用Worktop或文本编辑器编辑现有Report.cfg文件的步骤。
title: 编辑现有 Report.cfg 文件
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
exl-id: 69038c0c-bb01-4e61-aad6-1be0bdec8a6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# 编辑现有 Report.cfg 文件{#editing-existing-report-cfg-files}

{{eol}}

使用Worktop或文本编辑器编辑现有Report.cfg文件的步骤。

>[!NOTE]
>
>* 您必须联机工作才能进行编辑 [!DNL Report.cfg] 文件。 要联机工作，请从 [!DNL Worktop]，右键单击标题栏并单击 **[!UICONTROL Work Online]**.
>
>* 如果 **[!UICONTROL Allow Report Regeneration]** 参数 [!DNL Report.cfg] 文件设置为 [!DNL True]，当您更改该文件并将该文件保存回服务器时， [!DNL Report] 自动重新生成该集中的报表。 尽管会重新生成报表，但不会通过电子邮件重新发送报表。 要执行此操作的步骤，请参阅 [通过电子邮件重新发送报表](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).
>


您可以编辑现有 [!DNL Report.cfg] 从 [!DNL Worktop] 或使用文本编辑器。

编辑 [!DNL Report.cfg] 使用 [!DNL Reports] 选项卡 [!DNL Worktop] 允许您仅编辑文件中已存在的那些参数、矢量和矢量项。 如果需要向文件添加参数或矢量，则必须使用文本编辑器（如记事本）对其进行编辑。

* [使用Worktop编辑现有Report.cfg](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [使用文本编辑器编辑现有Report.cfg](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## 使用Worktop编辑现有Report.cfg {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>您必须联机工作才能编辑 [!DNL Report.cfg] 从 [!DNL Worktop].

1. 在Data Workbench中， [!DNL Reports] 选项卡，为要配置的报表集选择子文件夹（选项卡或下拉子目录）。
1. 单击 **[!UICONTROL Report.cfg]**。的参数 [!DNL Report.cfg] 显示。

1. 根据需要编辑配置参数。 有关这些参数的信息，请参阅 [Report.cfg参数](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. 通过右键单击保存文件 **[!UICONTROL Report.cfg (modified)]** ，然后单击 **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## 使用文本编辑器编辑现有Report.cfg {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. 打开 [!DNL Reports Manager] 右键单击工作区并单击 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. 单击报表集的文件夹。
1. 右键单击 [!DNL Report.cfg] 对于此报表集，单击 **[!UICONTROL Make Local]**.

1. 在 [!DNL User] 列中，右键单击旁边的复选标记 [!DNL Report.cfg] 对于此报表集，单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 的 [!DNL Report.cfg] 文件。

   示例 [!DNL Report.cfg] 显示 [配置报表集](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) 仅包含 [!DNL Report.cfg] 文件。 以下示例包括 [!DNL Report.cfg] 文件可用作参数条目的模型：

   ```
   Attachments = vector: 1 items
     0 = Attachment:
       FileName = string: c:\\myimage.jpg
       Content Type = string: image/jpeg
   Alert Threshold = int: 0
   Allow Report Regeneration = bool: true
   Color Set = int: 1
   Command To Execute = string: 
   Default Excel Template = string: 
   Dimension Name = string: 
   Email Only If Perfect = bool: false
   End Date = string: 
   Every = string: month
   Excel Watchdog Timeout (seconds) = double: 300.0
   Filter Formula = string: 
   Gamma Correction = double: 1
   Hide Logos = bool: false
   Lookup File = string: 
   Mail Report = MailReport: 
     Body XSL Template = string: 
     Recipients = vector: 0 items
     SMTP Server = SmtpServerInfo: 
       Address = string: 
       Password = string: 
       User = string: 
     Sender Address = string: 
     Sender Name = string: 
     Subject = string: 
   Notification Only = bool: false
   Output Root = string: 
   Report Types = vector: 3 items
     0 = string: thumbnail
     1 = string: png
     2 = string: excel
   Start Date = string: 7/1/06 19:16 EDT
   Thumbnail X = int: 240
   Thumbnail Y = int: 180
   Top N Metric = string: 
   Top N Value = int: 0
   Use Local Sample Only = bool: false
   Workspace Path = string: 
   ```

1. 根据需要编辑配置参数。 有关这些参数的信息，请参阅 [Report.cfg参数](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. 保存并关闭该文件。
1. 在 [!DNL Reports Manager]，右键单击 [!DNL User] 列 [!DNL Report.cfg] 文件，选择 **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
