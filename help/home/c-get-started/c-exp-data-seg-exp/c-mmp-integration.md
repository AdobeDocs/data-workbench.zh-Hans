---
description: 通过Data Workbench，您可以导出文件，并作为集成Adobe Experience Cloud的一部分与“配置文件”和“受众导出”集成。
title: 主营销配置文件导出
uuid: bae0f0c5-a452-4afd-9f2c-5f3ab69a12d2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# 主营销配置文件导出{#master-marketing-profile-export}

通过Data Workbench，您可以导出文件，并作为集成Adobe Experience Cloud的一部分与配置文件和受众集成。

<!-- <a id="section_731922BC8628479198A41EF3EA72F2FF"></a> -->

档案和受众是Experience Cloud Identity Service [(Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)，它是Experience Cloud的一项核心服务)的一部分 [!DNL Adobe Experience Cloud]。 The Profiles and Audiences export allows audiences to be shared across the Experience Cloud using a unique Experience Cloud ID (ECID) that is assigned to every visitor and then used by [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html). The [!DNL ExportIntegration.exe] application ( [!DNL E:\Server\Scripts]) is employed to generate both MMP and Adobe Target exports.

**将FSU服务器配置为使用配置文件和受众**

1. 访问您的 FSU 服务器。
1. 打开 MMPExport.cfg 文件。`Server/Admin/Export/MMPExport.cfg`。
1. 根据需要，在所有字段中输入值。例如：

   >[!NOTE]
   >
   >MMP/AAM集成依赖于Amazon的s3存储桶进行数据传输。
   >
   >
   >MMP (s3) 传输所需的 s3 信息可从 Audience Manager 团队获取。

   ```
   Sample MMPExport.cfg
   MMP Export Configuration = MMPExportConfiguration: 
   s3 Bucket = string: aws_bucket_for_mmp 
   s3 Object Directory = string: test/files/ 
   s3 Region = string: us-east-1 
   s3 Access Key = string: ZZKI62OO5YBA 
   s3 Secret Key = string: ioqwa3OpNE5 
   data Provider Name = string: 895 
   client ID = string: mcprofile2-test 
   client Secret = string: saea1287617212987q 
   username = string: mmptest 
   password = string: pass 
   numRecordsPerChunk = int:  
   numThreads = int:  
   maxRetriesOnSendFailure = unsigned int:
   ```

   >[!NOTE]
   >
   >The [!DNL MMPExport.cfg]file also lets you take all records, split them into sets, and create chunks of records. 记录区块随后会被导出到 Amazon S3。Three mandatory parameters are required to create chunks of records: [!DNL numRecordsPerChunk], [!DNL numThreads], and [!DNL maxRetriesOnSendFailure].

**参数的定义**

<table id="table_DDEFBC45895A4663973F9C2EB9052FEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>s3 存储段</i> </td> 
   <td colname="col2"> AWS S3 存储段，用来存放传送到的导出内容。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 对象目录</i> </td> 
   <td colname="col2"> 保存 s3 文件的路径。它支持子目录。 <p> <p>重要：路径中不允许出现空格和多字节字符，这会在导出过程中产生错误（允许使用连字符）。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 区域</i> </td> 
   <td colname="col2"> AWS s3 区域，用来存放发送而来的导出内容。例如 us-east-1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 访问键</i> </td> 
   <td colname="col2"> AWS s3 访问键 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 密钥</i> </td> 
   <td colname="col2"> AWS s3 密钥 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>数据提供程序名称</i> </td> 
   <td colname="col2"> 这将是用于在 AAM 中分别存储区段和特征的文件夹名称。它对于每个客户而言都应当是唯一的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>客户端 ID</i> </td> 
   <td colname="col2"> 这是为面向 MMP 设置的客户提供的唯一客户端 ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>客户端密钥</i> </td> 
   <td colname="col2"> <p><i></i>这是为面向 MMP 设置的客户提供的唯一客户端密钥。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>用户名</i> </td> 
   <td colname="col2"> MMP 用户名 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>密码</i> </td> 
   <td colname="col2"> MMP 密码 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numRecordsPerChunk</i> </td> 
   <td colname="col2"> <p>根据记录数确定区块大小。 </p> <p>实现将用户指定的值剪辑为min = 1000 records&amp; nbsp;（~50 KB块）&amp; nbsp；和max = 50000记录（~2.5 MB块）。&amp; nbsp；如果用户未指定此配置属性，则使用默认值10000。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numThreads</i> </td> 
   <td colname="col2"> <p>确定可并行发送的单个区块数量。该参数接受 1 到 24 个线程之间的值，默认值为 12 个线程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>maxRetriesOnSendFailure</i> </td> 
   <td colname="col2"> <p>确定区块发送失败时可重新尝试的次数。默认值为 0，表示不重试。 </p> <p>两次重试之间的休眠间隔时间为 2 秒。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**从客户端生成 MMP 导出**

1. 在客户端中，打开一个工作区，然后右键单击 **[!UICONTROL Tools]**> **[!UICONTROL Detail Table]**。
1. 添加&#x200B;**级别**。
1. 右键单击标题并选择&#x200B;**添加属性**。
1. 右键单击标题并选择&#x200B;**新建主营销配置文件导出**。 ![](assets/mmp_mmp_export.png)
1. 展开&#x200B;**查询**。

   ![](assets/mmp_mmp_query.png)

1. 展开 **MMP 配置**。
1. （必需）输入 **MMP 区段名称**&#x200B;和 **MMP 访客 ID 字段**。这些参数不能留为空白。
1. **MMP 区段名称**&#x200B;应匹配 MMP 中定义的区段 ID。
1. **MMP 访客 ID** 是在步骤 4 中定义的与&#x200B;**访客 ID** 对应的属性列。
1. 在这些字段中输入值后，您可以通过右键单击导出内容的标题并选择“**另存为** User\.export”，以保存导出内容。
1. 打开&#x200B;**管理员** > **配置文件管理器**，并将导出内容保存到配置文件。

   如果输入的所有数据都正确，这将在 FSU ([!DNL Server/Exports]) 中生成一个导出文件，它还将使用 [!DNL MMPExport.cfg] 中的信息把导出内容传送到 AWS。The log for this is provided in [!DNL Server/Trace/]. 例如， [!DNL MMP-102014-133651- `<Segment Export Name>` .log]

```
Query = SegmentExportQuery: 
Command = string: ExportIntegration.exe 
Command Arguments = string: \"%file%.cfg\" \"%file%\" 
Filter = string: 
Level = string: Page View 
MMP Configuration = MMPConfiguration: 
MMP Segment Name = string: 12345 
MMP Visitor ID Field = string: Tracking ID 
Oneshot = bool: true 
Output Fields = vector: 3 items 
0 = ColumnDefinition: 
Column Name = string: 
Field Name = string: Tracking ID 
1 = ColumnDefinition: 
Column Name = string: 
Field Name = string: PID 
2 = ColumnDefinition: 
Column Name = string: 
Field Name = string: SID 
Output File = string: MMPTest.txt 
Output Format = string: %1%\t%2%\t%3%\r\n 
Schedule End Time = string: 
Schedule Every = string: 
Schedule Start Time = string: 
Time Limit (sec) = double: 1800 
```

| 配置详细信息 | 描述 |
|---|---|
| MMP 区段 ID | 必需. 这是一个需要在 Audience Manager 中最先定义的标识符。 |
| MMP 访客 ID 字段 | 映射ECID。 |

