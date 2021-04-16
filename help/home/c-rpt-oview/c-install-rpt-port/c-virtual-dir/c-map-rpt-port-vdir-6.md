---
description: 将报表门户映射到虚拟目录(IIS 6.0)的步骤。
title: 将报表门户映射到虚拟目录 (IIS 6.0)
uuid: e09d23d7-09de-4180-8260-60527f47aa98
exl-id: 39335705-7391-49af-a63d-c0fe4ca3f8f0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 3%

---

# 将报表门户映射到虚拟目录 (IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

将报表门户映射到虚拟目录(IIS 6.0)的步骤。

将[!DNL Report Portal]映射到IIS 6.0上的虚拟目录涉及三个不同的任务:

1. [编辑配置文件](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [将配置文件导入IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [在IIS上启用活动服务器页(ASP)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

您必须完成所有三个任务。

## 编辑配置文件{#section-eaf1c58935074cfa840dac33e1286520}

1. 在安装[!DNL Report Portal]的计算机上，在文本编辑器（如记事本）中打开\*PortalName*\ReportPortalSetup.xml。

1. 使用编辑器的查找并替换功能，将字符串&quot;VSVirtualPortalName&quot;全局替换（全部替换）为门户名称。 例如，如果要使用“VisualReportPortal”作为[!DNL Report Portal]的名称，则应搜索“VSVirtualPortalName”并将其替换为“VisualReportPortal”。
1. 在此文件中找到以下元素：

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. 将此元素的[!DNL Path]属性设置为[!DNL Report Server]保存报表集输出的目录的物理位置。

   输出文件夹可以位于任意位置，可以命名任何内容，并包含每个报表集的子文件夹。

   >[!NOTE]
   >
   >它必须与在报表集[!DNL Report.cfg]文件的“输出根”参数中指定的目录相同。 有关详细信息，请参阅[配置Report.cfg文件](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d)。

   以下代码示例显示将报表保存到[!DNL E:\VSReport\ReportOutput]时如何设置[!DNL Path]属性：

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >必须正确设置[!DNL Path]属性。

1. 如果更改了[!DNL Output]元素的默认[!DNL Path]，请从&#x200B;*\PortalName*\PortalFiles\Output folder to the output directory that you specified in Step 4移动[!DNL profiles.xml]文件。 在上面的示例中，您将[!DNL profiles.xml]移动到[!DNL E:\VSReport\ReportOutput]。

1. 通过搜索所有[!DNL C:\Inetpub\wwwroot]实例并用正确的路径替换其它[!DNL IIsWebVirtualDir]元素的[!DNL Path]属性，验证是否将所有其他元素的属性映射到正确的位置。

1. 保存文件。如果要保留原始文件，可以使用新名称保存配置文件。

## 将配置文件导入IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. 在安装[!DNL Report Portal]的计算机上，使用&#x200B;**[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**&#x200B;开始IIS管理器。

1. 选择&#x200B;**[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**。

1. 右键单击&#x200B;**[!UICONTROL Default Web Site]**&#x200B;并选择&#x200B;**[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**（从文件）。

1. 选择&#x200B;**[!UICONTROL ReportPortalSetup.xml]**&#x200B;文件，然后单击&#x200B;**[!UICONTROL Read File]**。

1. 验证是否为[!DNL Report Portal]列出了六个虚拟目录，如以下示例所示。

   ![](assets/rptPort_dia_VirDirs.png)

   如果看不到六个虚拟目录或收到错误消息，请单击&#x200B;**[!UICONTROL Cancel]**&#x200B;并检查配置文件是否有错误。

1. 选择列表中的第一个虚拟目录（另一个是另五个的父目录），然后单击&#x200B;**[!UICONTROL OK]**。 IIS导入映射并将虚拟目录添加到默认网站。

   确保生成的目录结构有一个父文件夹（与门户名称相同）和五个子目录，如以下示例所示。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 单击每个虚拟目录，以确保IIS可以找到它所表示的物理目录。 如果IIS显示错误，请右键单击虚拟目录名称并验证[!DNL Local Path]字段是否指向正确的物理目录。

## 在IIS {#section-a7725ec2afc64ffc854c5bd8c5c31802}上启用活动服务器页(ASP)

要使用[!DNL Report Portal]，必须在IIS上启用ASP。 （默认情况下，安装IIS 6.0时会禁用ASP。） 请按照以下过程验证IIS上是否启用了ASP。

1. 在“IIS管理器”窗口中，选择&#x200B;**[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**。
1. 验证[!DNL Active Server Pages]扩展是否设置为[!DNL Allowed]。

   ![](assets/report_aspenable.png)

1. 如果“Status（禁止）”为“Prodited（禁止）” ，请选择&#x200B;**[!UICONTROL Active Server Pages]** ，然后单击&#x200B;**[!UICONTROL Allow]**。
1. 关闭IIS管理器。
