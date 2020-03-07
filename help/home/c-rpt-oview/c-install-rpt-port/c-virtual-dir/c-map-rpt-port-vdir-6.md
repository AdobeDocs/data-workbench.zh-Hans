---
description: 将Report Portal映射到虚拟目录(IIS 6.0)的步骤。
solution: Analytics
title: 将报告门户映射到虚拟目录(IIS 6.0)
topic: Data workbench
uuid: e09d23d7-09de-4180-8260-60527f47aa98
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 将报告门户映射到虚拟目录(IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

将Report Portal映射到虚拟目录(IIS 6.0)的步骤。

将映射 [!DNL Report Portal] 到IIS 6.0上的虚拟目录涉及三个单独的任务：

1. [编辑配置文件](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [将配置文件导入IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [在IIS上启用Active Server Pages(ASP)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

您必须完成所有三项任务。

## To Edit the Configuration File {#section-eaf1c58935074cfa840dac33e1286520}

1. 在安装了 [!DNL Report Portal] 的计算机上，在文本编辑器（如记事本）中打开\*PortalName*\ReportPortalSetup.xml。

1. 使用编辑器的查找和替换功能，将字符串“VSVirtualPortalName”全局替换（全部替换）为门户的名称。 例如，如果要使用“VisualReportPortal”作为名称，则应搜索“VSVirtualPortalName”并将其替换为“VisualReportPortal”。 [!DNL Report Portal]
1. 在此文件中找到以下元素：

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. 将此元素的属 [!DNL Path] 性设置为保存报表集输出的目 [!DNL Report Server] 录的物理位置。

   输出文件夹可以位于任何位置，可以命名为任何内容，并包含每个报告集的子文件夹。

   >[!NOTE]
   >
   >它必须与在报告集文件的“输出根”参数中指 [!DNL Report.cfg] 定的目录相同。 有关详细信息，请 [参阅配置Report.cfg文件](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d)。

   以下代码示例显示了在将报告保存到 [!DNL Path] 以下位置时如何设置属性 [!DNL E:\VSReport\ReportOutput]:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >正确设置属 [!DNL Path] 性至关重要。

1. 如果更改了元素的 [!DNL Path] 默认值， [!DNL Output] 请将文件从 [!DNL profiles.xml] \PortalName **\PortalFiles\Output folder to the output directory that you specified in Step 4文件夹移动。 在以上示例中，您将移 [!DNL profiles.xml] 到 [!DNL E:\VSReport\ReportOutput]。

1. 通过搜索所 [!DNL Path] 有其他元素的实例并用正确的路径替换每个实例，验证所有其他元素的属性 [!DNL IIsWebVirtualDir][!DNL C:\Inetpub\wwwroot] 是否都映射到正确的位置。

1. 保存文件。如果要保留原始文件，可以使用新名称保存配置文件。

## 将配置文件导入IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. 在安装了IIS [!DNL Report Portal] Manager的计算机上，使用 **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** >启动IIS Manager **[!UICONTROL Internet Information Systems (IIS) Manager]**。

1. 选择 **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. 右键单击 **[!UICONTROL Default Web Site]** 并选择 **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** （从文件）。

1. 选择文 **[!UICONTROL ReportPortalSetup.xml]** 件，然后单击 **[!UICONTROL Read File]**。

1. 验证是否列出了六个虚拟目 [!DNL Report Portal] 录，如以下示例所示。

   ![](assets/rptPort_dia_VirDirs.png)

   如果看不到六个虚拟目录或收到错误消息，请单击并检 **[!UICONTROL Cancel]** 查配置文件是否有错误。

1. 选择列表中的第一个虚拟目录（另一个是其他五个的父目录）并单击 **[!UICONTROL OK]**。 IIS导入映射并将虚拟目录添加到默认Web站点。

   确保生成的目录结构有一个父文件夹（与门户的名称相同）和五个子目录，如下例所示。

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. 单击每个虚拟目录，以确保IIS可以找到它所表示的物理目录。 如果IIS显示错误，请右键单击虚拟目录名称，并验证字 [!DNL Local Path] 段是否指向正确的物理目录。

## 在IIS上启用活动服务器页(ASP) {#section-a7725ec2afc64ffc854c5bd8c5c31802}

要使用 [!DNL Report Portal]，必须在IIS上启用ASP。 （默认情况下，安装IIS 6.0时会禁用ASP。）请按照以下过程验证IIS上是否启用了ASP。

1. 在“IIS Manager（IIS管理器）”窗口中，选择 **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]**。
1. 验证扩 [!DNL Active Server Pages] 展设置为 [!DNL Allowed]。

   ![](assets/report_aspenable.png)

1. 如果“禁止”(Status)为“禁止”(Applicated)，请选 **[!UICONTROL Active Server Pages]** 择并单击 **[!UICONTROL Allow]**。
1. 关闭IIS Manager。

