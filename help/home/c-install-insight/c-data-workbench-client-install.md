---
description: 以下是安装 Data Workbench 中工作站（客户端）的要求和建议。
title: 工作站要求
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 49%

---

# 工作站要求{#workstation-requirements}

以下是安装 Data Workbench 中工作站（客户端）的要求和建议。

有关其他Data Workbench系统要求，请参阅[服务器系统要求](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html)。

>[!IMPORTANT]
>
>升级服务器、报表服务器和客户端组件的目的是为了在 64 位 Windows 操作系统上运行。

**开始之前**

确保在安装 Data Workbench 工作站（客户端）之前已完成以下任务：

* 为下列可执行文件&#x200B;**添加** ***Windows Server 2012 中 MS 系统中心终端保护***&#x200B;的&#x200B;*已排除进程*：

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   这将启用这些允许列表接口可执行文件的权限。

* **安装 Microsoft Excel 以导出分析数据。** 要将工作区中的数据导出为Microsoft Excel( [!DNL .xls] 或 [!DNL .xlsx])文件，安装Data Workbench的计算机必须安装并注册Excel。如果Excel尚未注册，且Data Workbench首次尝试访问它，则Excel将显示一个注册对话框。 如果您不确定是否注册了副本，请手动启动 Excel，如果显示注册对话框，则完成注册过程。

   >[!NOTE]
   >
   >随着 Data Workbench 6.4 的发布，对 Excel 2007 的支持已经终止。此外，由于 Data Workbench 只能在 64 位架构的 Microsoft Windows 上运行，因此建议同时还安装 64 位版本的 Microsoft Excel。

* **安装 Adobe [!DNL Acrobat] 以将缩放的工作区打印成 PDF。** 要将缩放工作区打印为Adobe PDF格式，安装Data Workbench的计算机必须安装 [!DNL Acrobat] Adobe。

* **提供对打印机的访问以便打印工作区。** 要从Data Workbench打印工作区，安装Data Workbench的计算机必须有权访问打印机。Data Workbench可以将工作区打印到彩色或单色打印机，并且不需要postscript或其他高级打印机功能。 为了获得最佳效果，Adobe 建议您采用彩色打印机打印工作区。
* **实施安全措施。** 您应当遵循公司对Data Workbench计算机的常规企业安全策略。为了实现其主要目的，Data Workbench只需要连接到服务器（通过端口80和443）以及任何收集数据的服务器。 只要您维护Data Workbench软件并为Data Workbench分配至少10 GB的存储空间，您就可以将Data Workbench硬件用于任何其他用途。
* 为了准确呈现可视化，安装工作站的计算机必须安装相应的&#x200B;**图形适配器**（请参阅下文的“图形适配器要求”）。

**Data Workbench 客户端要求**

**操作系统**

* Microsoft Windows 7（64 位）
* Microsoft Windows 8.1（64 位）
* Microsoft Windows 10 64位

>[!NOTE]
>
>Data Workbench 6.1及更高版本不支持Windows XP。

**分辨率**

* 必需：1024 x 768(XGA)
* 建议：1920 x 1200(WUXGA)

**图形适配器**

* 必需：支持OpenGL 3.2的OpenGL硬件加速
* 建议：专用视频适配器（例如NVIDIA或ATI适配器）

**处理器**

* 必需：1.2 GHz或更高Intel或AMD
* 建议：ICore 2双级

**内存**

* 必需：2 GB
* 建议：4 GB

**连接**

* 必需：指向DPU的512 Kbps链接
* 建议：2Mbps或更快的DPU链路

**文件系统**

NTFS

**磁盘存储器**

至少十 (10) GB 或更大空闲硬盘驱动器空间

**打印**

用于打印工作区和报表的打印机访问权限（彩色或灰度打印机）

**其他**

* 专用鼠标
* 较低眩光的工作环境
* 哑光面显示器
