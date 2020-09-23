---
description: Adobe为特定应用程序开发的用户档案和查找文件是内部用户档案，它们提供支持分析数据集的度量、维度和工作区。
solution: Analytics
title: 安装配置文件和查找文件
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 5%

---


# 安装配置文件和查找文件{#installing-profiles-and-lookup-files}

Adobe为特定应用程序开发的用户档案和查找文件是内部用户档案，它们提供支持分析数据集的度量、维度和工作区。

与Adobe提供的所有其他内部用户档案一样，不应更改这些用户档案。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

Adobe将应用程序的用户档案和查找文件作为文件进行 [!DNL .zip] 分发。 每个zip文件都为其用户档案和查找文件所包含的应用程序命名。 (例如，包 [!DNL Site52.zip] 含站点v5.2的用户档案文件。) 文件 [!DNL .zip] 包含两个文件夹( [!DNL Lookups] 和 [!DNL Profiles])。

>[!NOTE]
>
>如果您还没有包含应用程序用户档案和查找文件的安装文件，请在开始之前从AdobeFTP站点下载这些文件。

您必须在处理和运行用户档案集的 [!DNL Insight Server] 计算机上安装该用户档案及其查找文件。 如果运行的是群 [!DNL Insight Server] 集，则必须在主控服务器上安装文件。 For information about dataset profiles, see the *Dataset Configuration Guide*.

**为用户档案应用程序安装Adobe**

1. 从Adobe提 [!DNL Profiles] 供给您 [!DNL .zip] 的文件中打开文件夹。

1. 将文件中文件夹内的所 [!DNL Profiles] 有文件夹复 [!DNL .zip] 制到安装 [!DNL Profiles] 目录中的 [!DNL Insight Server] 文件夹中。 您最后希望在您的&#x200B; [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>* 文 [!DNL Insight Server] 件夹中显示&lt;>。 您的实际用户档案名称可能不同。

   ![](assets/win_installprofiles.png)

1. 导览至安&#x200B; [!DNL Profiles\]*装[!DNL dataset profile name]目录中的&lt;* >文件夹，并 [!DNL Insight Server] 在此目 [!DNL profile.cfg] 录中找到该文件。

   >[!NOTE]
   >
   >如果您是第一次安装用户档案，则可以使用提供的示例用户档案作为数据集用户档案。 您可以在安 [!DNL profile.cfg] 装目录的文件夹中找到示例用户档案的文 [!DNL profile.cfg.offline]件(它可能命名为类似 [!DNL Profiles\Sample][!DNL Insight Server] 的名称)。

1. 使用文 [!DNL profile.cfg] 本编辑器（如记事本）打开文件，并执行以下操作：

   1. 在“目录”矢量中添加内部用户档案的条目。 用户档案名称与您复制到计算机上文件夹的目 [!DNL Profiles] 录的名称相 [!DNL Insight Server] 对应。

   1. 根据需要更新目录数。
   1. 将服务器的通用名称添加到此文件的通用名称行，如下所示：

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
      >在文 *件中为Common* Name指定的serverCommonName与要处理并运行数据集用户档案的 [!DNL profile.cfg][!DNL Insight Server] 计算机的服务器公用名称相对应。 有关更新以 [!DNL profile.cfg] 使数据集用户档案在群集上运行的说 [!DNL Insight Server] 明，请参 [阅Insight Server Clusters](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)。

1. 保存文件。请务必将文件保存为 [!DNL profile.cfg] 以其他方式命名。

**为Adobe应用程序安装查找文件**

1. 从Adobe提 [!DNL Lookups] 供给您 [!DNL .zip] 的文件中打开文件夹。

1. 将文件中文件夹内的所 [!DNL Lookups] 有文件夹复 [!DNL .zip] 制到安装 [!DNL Lookups] 目录中的 [!DNL Insight Server] 文件夹中。 您最后希望在您的&#x200B; [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>* 文 [!DNL Insight Server] 件夹中显示&lt;>。 您的实际用户档案名称可能不同。

   ![](assets/win_installLookups.png)

