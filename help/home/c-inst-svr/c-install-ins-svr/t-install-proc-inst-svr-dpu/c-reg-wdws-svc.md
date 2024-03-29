---
description: 启动Insight Server并同时将其注册为Microsoft Windows服务的过程。
title: 将 Insight Server 注册为 Windows 服务
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 6%

---

# 将 Insight Server 注册为 Windows 服务{#registering-insight-server-as-a-windows-service}

{{eol}}

启动Insight Server并同时将其注册为Microsoft Windows服务的过程。

>[!NOTE]
>
>首次启动 [!DNL Insight Server] 时，它会自动连接到 Adobe 许可证服务器以注册您的数字证书。要成功完成注册过程，您必须在执行以下步骤时将计算机连接到Internet。

**开始 [!DNL Insight Server] 注册为Windows服务**

1. 打开命令提示符，然后导航到安装文件夹中的bin子目录 [!DNL Insight Server].

   示例：[!DNL C:\Adobe\Server\bin]

1. 在命令提示符下，执行以下命令以启动 [!DNL Insight Server] 同时注册为在Microsoft Windows下作为服务运行：

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. 确认 [!DNL Insight Server] 运行正确，单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. 此命令序列可能因您使用的Windows版本而异。

   1. 在服务列表中，找到 **[!DNL Adobe Insight Server]** 并确认其状态为“已启动”且其启动类型为“自动”。
   1. 关闭“服务”控制面板。

1. 检查是否 [!DNL Insight Server] 在启动过程中遇到任何错误，请单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. 此命令序列可能因您使用的Windows版本而异。

   1. 在 [!DNL Event Viewer] 窗口，选择 **[!UICONTROL Application]** 日志。
   1. 在右侧窗格中，查找在 [!DNL Source] 列。
   1. 如果从“Adobe”中找到错误，请双击该错误以显示 [!DNL Event Properties] 窗口。 此窗口提供有关错误的详细信息。

1. 检查完 [!DNL Applications] 日志，关闭事件查看器。

您已完成 [!DNL Insight Server]. [!DNL Insight Server] 设计为连续运行。 如果重新启动计算机， [!DNL Insight Server] 自动重新启动。 如果需要启动和停止 [!DNL Insight Server] 手动操作时，您可以使用Windows中的“服务”控制面板来执行此操作。 如以下部分所述，您可以选择配置 [!DNL Insight Server] 服务定期自动重新启动。

## 将服务配置为自动重新启动 {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] 旨在继续不间断运行。 通常，只有在执行不经常的任务（如软件升级或证书更改）或发生某些系统错误时，才会停止或启动该工作流。 无需停止或重新启动 [!DNL Insight Server] 在正常系统运行期间提供服务；但是，您可以将服务配置为定期（每日、每周或每月）重新启动，例如清除事件消息。

**配置 [!DNL Insight Server] 自动重新启动服务**

1. 导航到 [!DNL Components] 文件夹。 [!DNL Insight Server].

   示例：[!DNL C:\Adobe\Server\Components]

1. 使用文本编辑器（如记事本）创建一个名为 [!DNL ScheduledRestart.cfg].
1. 在 [!DNL ScheduledRestart.cfg] 文件：

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 对于此值…… </th> 
      <th colname="col2" class="entry"> 在“管理工具”中指定分类的 </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>月DD，YYYY HH:MM:SStzone</i> </td> 
      <td colname="col2"> <p>您需要的时间 <span class="keyword"> Insight Server </span> 第一次重启。 </p> <p>示例：2013年8月13日22:30:东部标准时间00 </p> <p> <p>注意：您必须指定时区。 如果未指定，时区不默认为系统时间。 如果要实施夏令时或类似的时钟调整策略，则必须保存 <span class="filepath"> .dst </span> 文件，其中包含Base\Dataset\Timezone目录(位于 <span class="keyword"> Insight Server </span> 机器。 有关支持的时区缩写列表以及有关实施夏令时的信息，请参阅 <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> 时区代码 </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>频率</i> </td> 
      <td colname="col2"> <p>以下值之一： 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">月 </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">周 </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">天 </li> 
       </ul> </p> <p>指示所需的频率 <span class="keyword"> Insight Server </span> 在“开始时间”中指定的初始时间后重新启动。 </p> <p>例如，如果您想 <span class="keyword"> Insight Server </span> 要每周重新启动一次，您应将此值设置为“week”。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 保存 [!DNL ScheduledRestart.cfg] 文件。

   验证 [!DNL ScheduledRestart.cfg] 文件在 [!DNL Components] 文件夹。 [!DNL Insight Server].
