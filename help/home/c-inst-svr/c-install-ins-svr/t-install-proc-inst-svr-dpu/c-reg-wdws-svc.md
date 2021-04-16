---
description: 开始Insight Server并同时将其注册为Microsoft Windows服务的过程。
title: 将 Insight Server 注册为 Windows 服务
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 8%

---

# 将 Insight Server 注册为 Windows 服务{#registering-insight-server-as-a-windows-service}

开始Insight Server并同时将其注册为Microsoft Windows服务的过程。

>[!NOTE]
>
>首次启动 [!DNL Insight Server] 时，它会自动连接到 Adobe 许可证服务器以注册您的数字证书。要成功完成注册过程，您执行以下步骤时必须将计算机连接到Internet。

**开始并 [!DNL Insight Server] 将其注册为Windows服务**

1. 打开命令提示符，然后导航到安装[!DNL Insight Server]的文件夹中的bin子目录。

   示例：[!DNL C:\Adobe\Server\bin]

1. 在命令提示符下，执行以下命令以开始[!DNL Insight Server]，并同时注册它以在Microsoft Windows下作为服务运行：

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. 要确认[!DNL Insight Server]是否正确运行，请单击&#x200B;**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**。 此命令序列可能因您使用的Windows版本而异。

   1. 在服务列表中，找到&#x200B;**[!DNL Adobe Insight Server]**&#x200B;的条目，并确认其状态为“Started（启动）” ，其启动类型为“Automatic（自动）”。
   1. 关闭“服务”控制面板。

1. 要检查开始过程中[!DNL Insight Server]是否出现任何错误，请单击&#x200B;**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**。 此命令序列可能因您使用的Windows版本而异。

   1. 在[!DNL Event Viewer]窗口的左窗格中，选择&#x200B;**[!UICONTROL Application]**&#x200B;日志。
   1. 在右侧窗格中，查找[!DNL Source]列中带有“Adobe”的事件。
   1. 如果从“Adobe”中找到错误，请按住多次单击该错误以显示[!DNL Event Properties]窗口。 此窗口提供有关错误的详细信息。

1. 检查完[!DNL Applications]日志后，关闭事件查看器。

您已完成[!DNL Insight Server]的安装。 [!DNL Insight Server] 设计为连续运行。如果重新启动计算机，[!DNL Insight Server]将自动重新启动。 如果需要手动开始并停止[!DNL Insight Server]，则可以使用Windows中的“服务”控制面板执行此操作。 如以下部分所述，您可以选择将[!DNL Insight Server]服务配置为定期自动重新启动。

## 将服务配置为自动重新启动{#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] 是为了继续不间断运行。它通常仅在执行不频繁的任务（如软件升级或证书更改）或在事件某些系统错误时停止或启动。 在正常系统操作期间，无需停止或重新启动[!DNL Insight Server]服务；但是，您可以将服务配置为定期（每日、每周或每月）重新启动，例如清除事件消息。

**将服务配 [!DNL Insight Server] 置为自动重新启动**

1. 导览至安装[!DNL Insight Server]的目录中的[!DNL Components]文件夹。

   示例：[!DNL C:\Adobe\Server\Components]

1. 使用文本编辑器（如记事本）创建名为[!DNL ScheduledRestart.cfg]的新文件。
1. 在[!DNL ScheduledRestart.cfg]文件中输入以下文本：

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
      <td colname="col1"> <i>Month DD, YYYY HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>您希望首次重新启动<span class="keyword"> Insight Server </span>的时间。 </p> <p>示例：August 13, 2013 22:30:00 EST </p> <p> <p>注意： 必须指定时区。 如果未指定，则时区不默认为系统时间。 如果要实施夏令时或类似的时钟偏移策略，则必须在Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span>计算机中保存包含相应规则的<span class="filepath"> .dst </span>文件。 有关支持的时区缩写和有关实施夏令时的信息的列表，请参阅<a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211">时区代码</a>。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>频率</i> </td> 
      <td colname="col2"> <p>以下值之一： 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">个月 </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">周 </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">天 </li> 
       </ul> </p> <p>指示希望在开始时间中指定的初始时间后重新启动<span class="keyword"> Insight Server </span>的频率。 </p> <p>例如，如果您希望<span class="keyword"> Insight Server </span>每周重新启动一次，您应将此值设置为“week”。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 保存[!DNL ScheduledRestart.cfg]文件。

   验证[!DNL ScheduledRestart.cfg]文件是否位于[!DNL Insight Server]安装目录的[!DNL Components]文件夹中。
