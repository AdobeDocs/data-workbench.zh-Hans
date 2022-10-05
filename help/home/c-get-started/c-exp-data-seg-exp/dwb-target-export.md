---
description: 可以使用“明细表”中的 TargetBulkUpload.exe，将 Data Workbench 数据导出到 Adobe Target。
title: 导出到 Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
exl-id: 41e885bb-182a-4983-98e8-65eec1da9fe9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 22%

---

# 导出到 Adobe Target{#export-to-adobe-target}

{{eol}}

可以使用“明细表”中的 TargetBulkUpload.exe，将 Data Workbench 数据导出到 Adobe Target。

Data Workbench允许您导出文件，以将其作为集成Adobe Experience Cloud的一部分与Adobe Target集成。

您可以在服务器安装文件中的“Server\Scripts”**[!DNL TargetBulkUpload]***文件夹找到* 文件。这个可执行文件具有重试逻辑和其他可优化性能的逻辑。

您可以修改 `TargetBulkUpload.cfg` 将文件移到 *服务器/管理员/导出* 文件夹。 例如，您可以将“最大超时间隔”设置为720分钟（默认），以在指定的时间段后超时上传。

**工作原理**

数据成功发送到Target后，会持续监控上传状态。 如果上传成功，则会记录一条成功消息。 如果上传失败或挂起，则继续监控。 您可以在 `TargetBulkUpload.cfg` 文件。 如果上传卡在Target，则会记录一条消息，并且仍然可以监控状态。

跟踪中为下的触发导出生成了两个日志文件 [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

的 `targetbulkuploadexportname.log` 文件具有多批记录的详细状态、要访问的边缘服务器，以及状态（成功、失败、未找到配置文件、状态未知和卡住）。 如果发现任何批次卡住，则不再处理该批次。 滞后的批处理URL可用于跟踪状态。 请参阅 `targetbulkuploadexportname.log.completed` 文件：

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

停滞状态值会随着批次总停滞大小而递增，无论上载成功或失败的次数是多少。 总行值也会按相同数量的停滞批量大小递增。

>[!NOTE]
>
>以前，DWB数据是使用 [!DNL ExportIntegration.exe]. 目前，只有 MMP、CRS 和 S/FTP 导出使用该可执行文件。Adobe Target集成现在使用 [!DNL TargetBulkUpload.exe] Data Workbench。
