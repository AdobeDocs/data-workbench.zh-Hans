---
description: 使用Worktop或文本编辑器编辑现有Report.cfg文件的步骤。
title: 编辑现有 Report.cfg 文件
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
exl-id: 69038c0c-bb01-4e61-aad6-1be0bdec8a6d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# 编辑现有 Report.cfg 文件{#editing-existing-report-cfg-files}

使用Worktop或文本编辑器编辑现有Report.cfg文件的步骤。

>[!NOTE]
>
>* 必须联机工作才能编辑[!DNL Report.cfg]文件。 要联机工作，请在[!DNL Worktop]中右键单击标题栏，然后单击&#x200B;**[!UICONTROL Work Online]**。
   >
   >
* 如果[!DNL Report.cfg]文件中的&#x200B;**[!UICONTROL Allow Report Regeneration]**&#x200B;参数设置为[!DNL True]，则当您更改该文件并将该文件保存回服务器时，[!DNL Report]会自动重新生成该集中的报表。 尽管会重新生成报表，但不会通过电子邮件重新发送报表。 有关执行此操作的步骤，请参阅[通过电子邮件重新发送报表](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607)。

>



您可以从[!DNL Worktop]中编辑现有的[!DNL Report.cfg]，也可以使用文本编辑器编辑现有的。

使用[!DNL Worktop]的[!DNL Reports]选项卡编辑[!DNL Report.cfg]文件，可仅编辑文件中已存在的参数、矢量和矢量项。 如果需要向文件添加参数或矢量，则必须使用文本编辑器（如记事本）对其进行编辑。

* [使用Worktop编辑现有Report.cfg](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [使用文本编辑器编辑现有Report.cfg](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## 使用Worktop {#section-7bce3bca006149c79be7678430f21945}编辑现有Report.cfg

>[!NOTE]
>
>必须联机工作才能编辑[!DNL Worktop]中的[!DNL Report.cfg]。

1. 在Data Workbench的[!DNL Reports]选项卡中，为要配置的报表集选择子文件夹（选项卡或下拉子目录）。
1. 单击 **[!UICONTROL Report.cfg]**。此报表集的[!DNL Report.cfg]参数将显示。

1. 根据需要编辑配置参数。 有关这些参数的信息，请参阅[Report.cfg参数](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
1. 右键单击参数顶部的&#x200B;**[!UICONTROL Report.cfg (modified)]**&#x200B;并单击&#x200B;**[!UICONTROL Save to]***&lt;**[!UICONTROL server location]**>*保存文件。

## 使用文本编辑器{#section-06f3d2a8d7f34bc2841180caf10a1eb7}编辑现有Report.cfg

1. 右键单击工作区，然后单击&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**&#x200B;以打开[!DNL Reports Manager]。

1. 单击报表集的文件夹。
1. 右键单击此报表集[!DNL Report.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。

1. 在[!DNL User]列中，右键单击此报表集[!DNL Report.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 将打开[!DNL Report.cfg]文件。

   默认情况下，[配置报表集](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)中显示的示例[!DNL Report.cfg]仅包含[!DNL Report.cfg]文件中包含的参数。 以下示例包括可用于[!DNL Report.cfg]文件的所有参数，可将其用作参数条目的模型：

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

1. 根据需要编辑配置参数。 有关这些参数的信息，请参阅[Report.cfg参数](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
1. 保存并关闭该文件。
1. 在[!DNL Reports Manager]中，右键单击[!DNL Report.cfg]文件[!DNL User]列中的复选标记，然后选择&#x200B;**[!UICONTROL Save to]*****[!UICONTROL profile name]**>*。
