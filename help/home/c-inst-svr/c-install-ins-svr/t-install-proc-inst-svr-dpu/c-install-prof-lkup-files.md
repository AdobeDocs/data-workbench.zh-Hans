---
description: Adobe为您的特定应用程序开发的用户档案和查找文件是内部用户档案，它们提供可分析数据集的量度、维度和工作区。
title: 安装配置文件和查找文件
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 5%

---

# 安装配置文件和查找文件{#installing-profiles-and-lookup-files}

Adobe为您的特定应用程序开发的用户档案和查找文件是内部用户档案，它们提供可分析数据集的量度、维度和工作区。

与Adobe提供的所有其他内部用户档案一样，不应更改这些用户档案。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

Adobe以[!DNL .zip]文件的形式分发应用程序的用户档案和查找文件。 每个zip文件都为其用户档案和查找文件所包含的应用程序命名。 (例如，[!DNL Site52.zip]包含站点v5.2的用户档案文件。) [!DNL .zip]文件包含两个文件夹（[!DNL Lookups]和[!DNL Profiles]）。

>[!NOTE]
>
>如果您还没有包含应用程序用户档案和查找文件的安装文件，请先从Adobe FTP站点下载这些文件，然后再开始。

必须在处理和运行用户档案集用户档案的[!DNL Insight Server]计算机上安装该数据及其查找文件。 如果运行[!DNL Insight Server]群集，则必须在主控服务器上安装文件。 有关数据集用户档案的信息，请参阅&#x200B;*Dataset Configuration Guide*。

**为Adobe用户档案安装**

1. 从Adobe提供给您的[!DNL .zip]文件打开[!DNL Profiles]文件夹。

1. 将[!DNL .zip]文件中[!DNL Profiles]文件夹内的所有文件夹复制到[!DNL Insight Server]安装目录中的[!DNL Profiles]文件夹。 您希望在[!DNL Insight Server]上最终包含&#x200B; [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>*&#x200B;文件夹，如以下示例所示。 您的实际用户档案名称可能不同。

   ![](assets/win_installprofiles.png)

1. 导览至安装[!DNL Insight Server]的目录中的&#x200B; [!DNL Profiles\]*&lt;[!DNL dataset profile name]>*&#x200B;文件夹，并在此目录中找到[!DNL profile.cfg]文件。

   >[!NOTE]
   >
   >如果您是第一次安装用户档案，则可以使用提供的示例用户档案作为数据集用户档案。 在[!DNL Insight Server]安装目录的[!DNL Profiles\Sample]文件夹中，可以找到[!DNL profile.cfg]文件（其名称可能类似于[!DNL profile.cfg.offline]）的“示例”用户档案。

1. 使用文本编辑器（如记事本）打开[!DNL profile.cfg]文件，并执行以下操作：

   1. 在“目录”矢量中添加内部用户档案的条目。 用户档案名称与您复制到[!DNL Insight Server]计算机上[!DNL Profiles]文件夹的目录名称相对应。

   1. 根据需要更新目录数。
   1. 将服务器的公用名称添加到此文件的公用名称行，如下所示：

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
      >您为[!DNL profile.cfg]文件中的“公用名称”指定的&#x200B;*serverCommonName*&#x200B;与您正在处理并运行数据集用户档案的[!DNL Insight Server]计算机的服务器通用名称相对应。 有关更新[!DNL profile.cfg]以使数据集用户档案在[!DNL Insight Server]群集上运行的说明，请参阅[ Insight Server Clusters](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)。

1. 保存文件。如果文件的命名不同，请务必将其保存为[!DNL profile.cfg]。

**为您的Adobe应用程序安装查找文件**

1. 从Adobe提供给您的[!DNL .zip]文件打开[!DNL Lookups]文件夹。

1. 将[!DNL .zip]文件中[!DNL Lookups]文件夹内的所有文件夹复制到[!DNL Insight Server]安装目录中的[!DNL Lookups]文件夹。 您希望在[!DNL Insight Server]上最终包含&#x200B; [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>*&#x200B;文件夹，如以下示例所示。 您的实际用户档案名称可能不同。

   ![](assets/win_installLookups.png)
