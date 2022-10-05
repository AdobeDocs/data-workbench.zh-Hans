---
description: 您可以在Data Workbench客户端中轻松地从明细表可视化创建区段导出定义。
title: 区段导出
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
exl-id: 49998b46-f3a6-43a3-a76e-468894b27ee4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 55%

---

# 区段导出{#segment-export}

{{eol}}

您可以在Data Workbench客户端中轻松地从明细表可视化创建区段导出定义。

此外， [!DNL Segment Exports] 自动将其结果合并到单个服务器，而不是在每个DPU上生成部分结果，您必须使用外部流程合并这些结果。 您可以创建区段导出文件，并将其保存到 [!DNL Profile Manager]，然后将输出文件上传到您选择的服务器。

**配置区段导出服务器**

的 [!DNL Segment Export] 功能会在区段导出服务器上创建单个输出文件，而不是在每个DPU上创建单独的输出文件。 区段导出服务器通常配置为在 FSU 上运行。

在 [!DNL Profile Manager]，打开 [!DNL Segment Export.cfg] 在工作站中，并指定您的服务器地址。 （您的地址可以是 IP 或完全限定域名。）：

![](assets/segment_export_cfg.png)

这是接收区段导出结果的Data Workbench服务器的IP。 这是一次性设置。如果 [!DNL Segment Export.cfg] 不存在，则导出不会运行。

**配置导出目录**

出于安全原因考虑，在区段导出后运行的可执行文件或批处理文件必须驻留在区段导出服务器的可配置 Scripts\ 目录中。

的 [!DNL .part] 和最终输出必须位于可配置的Exports目录中。 要运行的命令存在于 Command（命令）和 Command Arguments（命令参数）中。Command Arguments（命令参数）中 %file% 的实例将替换为输出文件的路径。

>[!NOTE]
>
>对于Data Workbench5.4，将自动创建\Exports文件夹。 以前在 5.4 版之前设置的导出目录需要在每个区段导出的文件名之前添加 Exports\ 前缀。现在添加此前缀是多余的了。

1. 在 [!DNL Communications.cfg] 目标服务器上的 [!DNL Segment Exports]，将SegmentExportServer添加到服务器列表。 （示例以红色显示）。

   ![](assets/communications_cfg_example.png)

   导出目录：指定放置位置 [!DNL .part] 和输出文件。 该位置可以是共享目录。

   Scripts Directory（脚本目录）：指定从中运行所有可执行文件或批处理文件的目录。

1. 同一服务器上的 [!DNL Access Control.cfg] 将对 URI /SegmentExportServer/ 的读写访问权限添加到群集服务器访问组：

   ![](assets/accesscontrol_cfg_example.png)

1. 更改 [!DNL .export] 文件：

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

1. 在“明细表”标题中，右键单击并选择 **[!UICONTROL Create Segment Export File]**.
1. 在 [!DNL Save as]，键入 [!DNL .export] 文件。
1. 在 [!DNL .export] 文件中，根据需要配置参数。

   工作区中的任何选择或过滤器都会应用到导出文件中。

1. 保存 [!DNL .export] 文件。

   保存的文件显示在 [!DNL Profile Manager] 保存到服务器。 当您将该文件保存到服务器时，导出随即开始。
