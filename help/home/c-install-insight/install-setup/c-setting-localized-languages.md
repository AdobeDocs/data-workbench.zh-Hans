---
description: 通过 insight.zbin 文件设置客户端应用程序的语言。
solution: Analytics
title: 设置本地化语言
topic: Data workbench
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 设置本地化语言{#setting-up-localized-languages}

通过 insight.zbin 文件设置客户端应用程序的语言。

## 更新 Data Workbench 服务器组件 {#section-5d07a081befc4eaa8fdf7fea904e0d48}

管理员必须首先完成以下任务，才能更新这些服务器组件：

1. **更新至 Data Workbench 服务器 6.x。**&#x200B;您需要通过更新 [!DNL base\localization\*.zbin] 文件来更新 Data Workbench 本地化服务器。然后会将此 [!DNL insight.zbin] 文件复制到客户端。

   [!DNL insight.zbin] 文件连同 [!DNL insight.exe] 文件一起包含在安装文件夹中。If you connect to a server that doesn&#39;t provide you with language-specific [!DNL .zbin] files, then data workbench will proceed to use this file.

   备用 [!DNL insight.zbin] 文件可用任何语言提供。As a result, if you use data workbench in Chinese and connect to a server that doesn&#39;t support this language, then your data workbench client will still be in Chinese, even if the server changes your base profile and removes your [!DNL .zbin] files from the [!DNL Base/Localization] folder.

1. **更新 Data Workbench 报表服务器。**&#x200B;位于 Data Workbench 报表服务器根文件夹中的 [!DNL insight.zbin] 默认将为英语。As the administrator, you will be required to select and copy the [!DNL .zbin] file from the updated report server package and place it in the root directory of the data workbench report server. 与客户端一样，报表服务器也需要所选语言的适当参数，例如 [!DNL Insight.exe -zh-cn]。

   1. 停止报表服务器服务。
   1. 复制新报表服务器包中的 [!DNL Localization] 文件夹。
   1. 从 [!DNL Localization] 文件夹中，复制 [!DNL Insight.zbin] 文件并将其置于 [!DNL Insight.exe] 所在的报表服务器根目录中。

   1. Add any required arguments, such as [!DNL insight.exe -zh-cn]
   1. 重新启动报表服务器。

## 更新 Data Workbench 客户端 {#section-9653d3fcaf2a4337a97b685857e7aeac}

更新服务器后，请按照以下步骤更新每个客户端。

1. 为确保客户端在此更新期间不会从服务器获取更新，请将 [!DNL Insight.cfg] 参数设置为 False。

   ```
   Update Software = bool: false
   ```

1. 重新启动客户端。
1. Navigate to the Software and Docs profile (SoftDocs profile) and download the required **[!UICONTROL insight.zbin]** file from the client package: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Move the [!DNL insight.zbin] file to the folder where [!DNL insight.exe] is located.

1. 为确保客户端文件现在从服务器获取更新，请将 [!DNL Insight.cfg] 文件参数更改为 True：

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >您的客户端将与服务器同步，并且您将看到一条消息，说明它正在更新。 下载结束时，您将收到一条消息，询问您是否要重新启动客户端。

1. 单击&#x200B;**确定**&#x200B;重新启动客户端。

如果您收到以下消息，则表示 [!DNL zbin] 文件与 [!DNL Insight.exe] 不在相同的位置。

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**本地化的启动屏幕**

Data Workbench 会查找以下启动屏幕文件：

* 英语（默认）: [!DNL Base/Images/<version_product> Splash.png]
* 中文（从-zh-cn开始）: [!DNL Base/Images/<version_product> Splash zh-cn.png].

如果请求的启动屏幕缺失，则 Data Workbench 将在默认情况下访问英语启动屏幕。

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->

