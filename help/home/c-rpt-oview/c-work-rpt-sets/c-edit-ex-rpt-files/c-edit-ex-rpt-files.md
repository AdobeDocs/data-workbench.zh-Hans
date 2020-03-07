---
description: 使用Worktop或文本编辑器编辑现有Report.cfg文件的步骤。
solution: Analytics
title: 编辑现有Report.cfg文件
topic: Data workbench
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 编辑现有Report.cfg文件{#editing-existing-report-cfg-files}

使用Worktop或文本编辑器编辑现有Report.cfg文件的步骤。

>[!NOTE]
>
>* 必须联机工作才能编辑文 [!DNL Report.cfg] 件。 要联机工作，请在标 [!DNL Worktop]题栏中右键单击并单击 **[!UICONTROL Work Online]**。
   >
   >
* 如果文 **[!UICONTROL Allow Report Regeneration]** 件中的参数 [!DNL Report.cfg] 设置为，则当您对该文件进行更改并将该文件保存回服务器时， [!DNL True][!DNL Report] 会自动重新生成该集中的报告。 尽管它会重新生成报告，但不会通过电子邮件重新发送报告。 有关执行此操作的步骤，请参阅通过电子邮件 [发送报告(Resending Reports by Email](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607))。
>



您可以从或使用文 [!DNL Report.cfg] 本编辑 [!DNL Worktop] 器编辑现有文本。

使用 [!DNL Report.cfg] 选项卡编辑文 [!DNL Reports] 件 [!DNL Worktop] 后，您只能编辑文件中已存在的那些参数、矢量和矢量项。 如果需要向文件添加参数或矢量，则必须使用文本编辑器（如记事本）编辑它。

* [使用Worktop编辑现有Report.cfg](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [使用文本编辑器编辑现有Report.cfg](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## 使用Worktop编辑现有Report.cfg {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>您必须在线工作才能从 [!DNL Report.cfg] 中编辑 [!DNL Worktop]。

1. 在Data Workbench的选项卡 [!DNL Reports] 中，为要配置的报表集选择子文件夹（选项卡或下拉子目录）。
1. 单击 **[!UICONTROL Report.cfg]**. 此报告集 [!DNL Report.cfg] 的参数显示。

1. 根据需要编辑配置参数。 有关这些参数的信息，请参 [阅Report.cfg参数](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
1. Save the file by right-clicking **[!UICONTROL Report.cfg (modified)]** at the top of the parameters and clicking **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## 使用文本编辑器编辑现有Report.cfg {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. 在工 [!DNL Reports Manager] 作区中右键单击，然后单击 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** >打开 **[!UICONTROL Reports Manager]**。

1. 单击报告集的文件夹。
1. 右键单击此报告集旁边的复 [!DNL Report.cfg] 选标记，然后单击 **[!UICONTROL Make Local]**。

1. 在列 [!DNL User] 中，右键单击此报告集旁边的复 [!DNL Report.cfg] 选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 The [!DNL Report.cfg] file opens.

   默认情 [!DNL Report.cfg] 况下，配 [置报告集中显示的示例仅包含文件中](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)[!DNL Report.cfg] 包含的参数。 以下示例包括可用于文件的所有参数， [!DNL Report.cfg] 这些参数可用作参数条目的模型：

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

1. 根据需要编辑配置参数。 有关这些参数的信息，请参 [阅Report.cfg参数](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
1. 保存并关闭该文件。
1. 在中， [!DNL Reports Manager]右键单击文件列中的复选 [!DNL User] 标记，然 [!DNL Report.cfg] 后选择 **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*。

