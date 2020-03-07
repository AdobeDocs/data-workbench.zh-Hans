---
description: 您可以从Data Workbench Client中的Detail Table可视化中轻松创建区段导出定义。
solution: Analytics
title: 区段导出
topic: Data workbench
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Segment export{#segment-export}

您可以从Data Workbench Client中的Detail Table可视化中轻松创建区段导出定义。

In addition, [!DNL Segment Exports] automatically combine their results to a single server, rather than producing partial results on each DPU that you must combine using an external process. You can create a segment export file, save it to the [!DNL Profile Manager], and upload the output file to a server of your choice.

**配置区段导出服务器**

The [!DNL Segment Export] feature creates a single output file on the segment export server, rather than separate output files created on each DPU. 区段导出服务器通常配置为在 FSU 上运行。

In the Dataset\ directory in the [!DNL Profile Manager], open the [!DNL Segment Export.cfg] in Workstation, and specify your server’s address. （您的地址可以是 IP 或完全限定域名。）：

![](assets/segment_export_cfg.png)

这是接收区段导出结果的Data Workbench Server的IP。 这是一次性设置。如果 [!DNL Segment Export.cfg] 不存在，则导出不会运行。

**配置导出目录**

出于安全原因考虑，在区段导出后运行的可执行文件或批处理文件必须驻留在区段导出服务器的可配置 Scripts\ 目录中。

The [!DNL .part] and final output must reside in the configurable Exports directory. 要运行的命令存在于 Command（命令）和 Command Arguments（命令参数）中。Command Arguments（命令参数）中 %file% 的实例将替换为输出文件的路径。

>[!NOTE]
>
>Data Workbench 5.4中新增了\Exports文件夹，该文件夹会自动创建。 以前在 5.4 版之前设置的导出目录需要在每个区段导出的文件名之前添加 Exports\ 前缀。现在添加此前缀是多余的了。

1. In [!DNL Communications.cfg] on the destination server for [!DNL Segment Exports], add a SegmentExportServer to the list of servers. （示例以红色显示）。

   ![](assets/communications_cfg_example.png)

   Exports Directory: Specifies where to put [!DNL .part] and output files. 该位置可以是共享目录。

   Scripts Directory（脚本目录）：指定从中运行所有可执行文件或批处理文件的目录。

1. 同一服务器上的 [!DNL Access Control.cfg] 将对 URI /SegmentExportServer/ 的读写访问权限添加到群集服务器访问组：

   ![](assets/accesscontrol_cfg_example.png)

1. Change your [!DNL .export] files:

   ![](assets/segment_export_query_example.png)

1. 对于每个配置文件，[!DNL Segment Export.cfg] 都位于 Dataset\ 目录中，并且包含以下内容：

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. 确保 Exports Directory（导出目录）和 Scripts Directory（脚本目录）中引用的目录都存在。

   只有 Scripts Directory（脚本目录）中的可执行文件和批处理文件可以作为区段导出的命令运行。

**创建区段导出文件**

1. 在工作区中，创建显示数据子集的明细表（“可视化”>“明细表”），并添加属性。
1. 如果需要，在工作区中进行相应的选择。（任何选择或过滤器都适用于导出。）

   ![](assets/create_segment_export_file.png)

1. 在Detail Table标题中，右键单击并选择 **[!UICONTROL Create Segment Export File]**。
1. 在 [!DNL Save as]中，键入文件的名 [!DNL .export] 称。
1. On the [!DNL .export] file, configure the parameters as necessary.

   工作区中的任何选择或过滤器都会应用到导出文件中。

1. Save the [!DNL .export] file.

   The saved file displays in the [!DNL Profile Manager] for you to save to the server. 当您将该文件保存到服务器时，导出随即开始。

