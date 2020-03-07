---
description: 可以使用“明细表”中的 TargetBulkUpload.exe，将 Data Workbench 数据导出到 Adobe Target。
title: 导出到Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 导出到Adobe Target{#export-to-adobe-target}

可以使用“明细表”中的 TargetBulkUpload.exe，将 Data Workbench 数据导出到 Adobe Target。

通过Data Workbench，您可以导出文件并作为集成Adobe Experience Cloud的一部分与Adobe Target集成。

您可以在服务器安装文件中的“Server\Scripts”**[!DNL TargetBulkUpload]***文件夹找到* 文件。这个可执行文件具有重试逻辑和其他可优化性能的逻辑。

运行上传脚本 `TargetBulkUpload.cfg` 之前，您可以修改文 *件并将其移到Server/Admin/Export* 文件夹。 例如，您可以将“最大超时间隔”设置为720分钟（默认），以在指定时间段后超时上传。

**工作原理**

数据成功发送到Target后，将持续监视上传状态。 如果上传成功，则会记录成功消息。 如果上传失败或处于挂起状态，则继续监视。 您可以在文件中配置超时间 `TargetBulkUpload.cfg` 隔。 如果上传卡在Target，则会记录一条消息，并且状态仍可被监视。

跟踪中为触发的导出生成了两个日志文件，位于 [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

该文 `targetbulkuploadexportname.log` 件具有多批记录的详细状态、要访问的边缘服务器以及状态（成功、失败、找不到配置文件、状态未知和卡住）。 如果发现任何批卡住，则不再处理该批。 滞留的批URL可用于跟踪状态。 请参阅文件中的以下示例数 `targetbulkuploadexportname.log.completed` 据：

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

卡住状态值随卡住批总大小递增，而不管上载成功或失败的数量。 总行值也会按相同数量的卡住批量大小递增。

>[!NOTE]
>
>Previously, DWB data was exported using the [!DNL ExportIntegration.exe]. 目前，只有 MMP、CRS 和 S/FTP 导出使用该可执行文件。Adobe Target integration now uses the [!DNL TargetBulkUpload.exe] in Data Workbench.

