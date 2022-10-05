---
description: Adobe为特定应用程序开发的配置文件和查找文件是内部配置文件，可提供用于分析数据集的量度、维度和工作区。
title: 安装配置文件和查找文件
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 5%

---

# 安装配置文件和查找文件{#installing-profiles-and-lookup-files}

{{eol}}

Adobe为特定应用程序开发的配置文件和查找文件是内部配置文件，可提供用于分析数据集的量度、维度和工作区。

与Adobe提供的所有其他内部用户档案一样，不应更改这些用户档案。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

Adobe将应用程序的配置文件和查找文件作为 [!DNL .zip] 文件。 每个zip文件都以其配置文件和查找文件所包含的应用程序命名。 (例如， [!DNL Site52.zip] 包含Site v5.2的配置文件。) 的 [!DNL .zip] 文件包含两个文件夹( [!DNL Lookups] 和 [!DNL Profiles])。

>[!NOTE]
>
>如果您还没有包含应用程序配置文件和查找文件的安装文件，请先从AdobeFTP站点下载这些文件，然后再开始。

您必须在 [!DNL Insight Server] 处理并运行数据集配置文件的计算机。 如果您运行的 [!DNL Insight Server] 群集时，必须在主控服务器上安装文件。 有关数据集配置文件的信息，请参阅 *数据集配置指南*.

**为Adobe应用程序安装配置文件**

1. 打开 [!DNL Profiles] 文件夹 [!DNL .zip] 文件(由Adobe提供)。

1. 复制 [!DNL Profiles] 文件夹 [!DNL .zip] 文件 [!DNL Profiles] 文件夹中 [!DNL Insight Server] 安装目录。 您希望最终获得[!DNL ...\Profiles\]*&lt; [!DNL internal profile name]>* 文件夹 [!DNL Insight Server] 如以下示例中所示。 您的实际配置文件名称可能会有所不同。

   ![](assets/win_installprofiles.png)

1. 导航到&#x200B; [!DNL Profiles\]*&lt; [!DNL dataset profile name]>* 文件夹。 [!DNL Insight Server] 并找到 [!DNL profile.cfg] 文件。

   >[!NOTE]
   >
   >如果您是首次安装配置文件，则可以使用提供的示例配置文件作为数据集配置文件。 您可以在 [!DNL profile.cfg] 文件(它的名字可能类似于 [!DNL profile.cfg.offline]) [!DNL Profiles\Sample] 文件夹中 [!DNL Insight Server] 安装目录。

1. 打开 [!DNL profile.cfg] 文件（如记事本），然后执行以下操作：

   1. 在“目录”矢量中添加内部配置文件的条目。 配置文件名称对应于您复制到 [!DNL Profiles] 文件夹 [!DNL Insight Server] 机器。

   1. 根据需要更新目录数。
   1. 将服务器的通用名称添加到此文件的“通用名称”行，如下所示：

      ```
      Profile = profileInfo: 
      Directories = vector: n+1 items
        0 = string: Base\\
        1 = string: internal profile name 1\\
        2 = string: internal profile name 2\\
      . . .
        n = string: internal profile name n\\
      Processing Servers = vector: 1 items
        0 = ProfileServerInfo: 
          Common Name = string: serverCommonName
          Server = string: 
      ```

      >[!NOTE]
      >
      >的 *serverCommonName* 在 [!DNL profile.cfg] 文件对应于 [!DNL Insight Server] 处理并运行数据集配置文件的计算机。 有关更新说明 [!DNL profile.cfg] 以便数据集配置文件在 [!DNL Insight Server] 群集，请参阅 [Insight Server聚类](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. 保存文件。确保将文件另存为 [!DNL profile.cfg] 如果用不同的名字命名。

**为Adobe应用程序安装查找文件**

1. 打开 [!DNL Lookups] 文件夹 [!DNL .zip] 文件(由Adobe提供)。

1. 复制 [!DNL Lookups] 文件夹 [!DNL .zip] 文件 [!DNL Lookups] 文件夹中 [!DNL Insight Server] 安装目录。 您希望最终获得[!DNL ...\Lookups\]*&lt; [!DNL internal profile name]>* 文件夹 [!DNL Insight Server] 如以下示例中所示。 您的实际配置文件名称可能会有所不同。

   ![](assets/win_installLookups.png)
