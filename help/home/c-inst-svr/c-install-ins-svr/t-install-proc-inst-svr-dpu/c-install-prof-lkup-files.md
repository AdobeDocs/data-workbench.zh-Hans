---
description: Adobe为您的特定应用程序开发的配置文件和查找文件是内部配置文件，它们提供了可用于分析数据集的指标、维度和工作区。
solution: Insight
title: 安装配置文件和查找文件
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 安装配置文件和查找文件{#installing-profiles-and-lookup-files}

Adobe为您的特定应用程序开发的配置文件和查找文件是内部配置文件，它们提供了可用于分析数据集的指标、维度和工作区。

与Adobe提供的所有其他内部配置文件一样，不应更改这些配置文件。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

Adobe将应用程序的配置文件和查找文件作为文件分发 [!DNL .zip] 出来。 每个zip文件都以其配置文件及其包含的查找文件的应用程序命名。 (例如，包 [!DNL Site52.zip] 含站点v5.2的配置文件。)该文 [!DNL .zip] 件包含两个文件夹( [!DNL Lookups] 和 [!DNL Profiles])。

>[!NOTE]
>
>如果您还没有包含应用程序配置文件和查找文件的安装文件，请在开始之前从Adobe FTP站点下载这些配置文件和查找文件。

您必须在处理和运行数据集配置文件的 [!DNL Insight Server] 计算机上安装配置文件及其查找文件。 如果运行群集， [!DNL Insight Server] 则必须在主服务器上安装这些文件。 For information about dataset profiles, see the *Dataset Configuration Guide*.

**为Adobe应用程序安装配置文件**

1. 从Adobe [!DNL Profiles] 提供给您的 [!DNL .zip] 文件中打开文件夹。

1. 将文件中文件夹内的所 [!DNL Profiles] 有文件夹复 [!DNL .zip] 制到安装目 [!DNL Profiles] 录中的 [!DNL Insight Server] 文件夹。 您最终想得到[!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>您上的*[!DNL Insight Server] 文件夹，如以下示例所示。 您的实际配置文件名称可能不同。

   ![](assets/win_installprofiles.png)

1. 导览至安装目录中的[!DNL Profiles\]*&lt;[!DNL dataset profile name]>* 文件夹，然后 [!DNL Insight Server] 在此目录中找 [!DNL profile.cfg] 到该文件。

   >[!NOTE]
   >
   >如果您是第一次安装配置文件，则可以使用提供的示例配置文件作为数据集配置文件。 您可以在安装目 [!DNL profile.cfg] 录的文件夹中找到示例配置文件的文件（可能命名为类似） [!DNL profile.cfg.offline](示例 [!DNL Profiles\Sample][!DNL Insight Server] 配置文件)。

1. 使用文 [!DNL profile.cfg] 本编辑器（如记事本）打开文件，然后执行以下操作：

   1. 在“目录”矢量中为内部配置文件添加条目。 配置文件名称与复制到计算机上文件夹的目录 [!DNL Profiles] 的名称相 [!DNL Insight Server] 对应。

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
      >在文 *件中为“公用名称”指定的serverCommonName* ，与要处理并运行数据集配置文件的计算机的服务器公 [!DNL profile.cfg][!DNL Insight Server] 用名称相对应。 有关更新以使 [!DNL profile.cfg] 数据集配置文件在群集上运行的说 [!DNL Insight Server] 明，请参阅 [Insight Server Clusters](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)。

1. 保存文件。请务必将文件保存为 [!DNL profile.cfg] 以不同的名称。

**为Adobe应用程序安装查找文件**

1. 从Adobe [!DNL Lookups] 提供给您的 [!DNL .zip] 文件中打开文件夹。

1. 将文件中文件夹内的所 [!DNL Lookups] 有文件夹复 [!DNL .zip] 制到安装目 [!DNL Lookups] 录中的 [!DNL Insight Server] 文件夹。 您最终想得到[!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>您上的*[!DNL Insight Server] 文件夹，如以下示例所示。 您的实际配置文件名称可能不同。

   ![](assets/win_installLookups.png)

