---
description: Adobe为特定应用程序开发的配置文件和查找文件是内部配置文件，可提供用于分析数据集的量度、维度和工作区。
title: 安装配置文件和查找文件
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 5%

---

# 安装配置文件和查找文件{#installing-profiles-and-lookup-files}

Adobe为特定应用程序开发的配置文件和查找文件是内部配置文件，可提供用于分析数据集的量度、维度和工作区。

与Adobe提供的所有其他内部用户档案一样，不应更改这些用户档案。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

Adobe将应用程序的配置文件和查找文件分发为[!DNL .zip]文件。 每个zip文件都以其配置文件和查找文件所包含的应用程序命名。 （例如，[!DNL Site52.zip]包含Site v5.2的配置文件。） [!DNL .zip]文件包含两个文件夹（[!DNL Lookups]和[!DNL Profiles]）。

>[!NOTE]
>
>如果您还没有包含应用程序配置文件和查找文件的安装文件，请先从AdobeFTP站点下载这些文件，然后再开始。

您必须在处理并运行数据集配置文件的[!DNL Insight Server]计算机上安装配置文件及其查找文件。 如果运行的是[!DNL Insight Server]群集，则必须在主控服务器上安装文件。 有关数据集配置文件的信息，请参阅&#x200B;*《数据集配置指南》*。

**为Adobe应用程序安装配置文件**

1. 从通过Adobe提供给您的[!DNL .zip]文件中打开[!DNL Profiles]文件夹。

1. 将[!DNL .zip]文件[!DNL Profiles]文件夹内的所有文件夹复制到[!DNL Insight Server]安装目录的[!DNL Profiles]文件夹中。 您希望在[!DNL Insight Server]上最终使用&#x200B; [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>*&#x200B;文件夹，如以下示例所示。 您的实际配置文件名称可能会有所不同。

   ![](assets/win_installprofiles.png)

1. 导航到&#x200B; [!DNL Profiles\]*&lt;[!DNL dataset profile name]>*&#x200B;文件夹（位于安装[!DNL Insight Server]的目录中），然后在此目录中找到[!DNL profile.cfg]文件。

   >[!NOTE]
   >
   >如果您是首次安装配置文件，则可以使用提供的示例配置文件作为数据集配置文件。 在[!DNL Insight Server]安装目录的[!DNL Profiles\Sample]文件夹中，可以找到[!DNL profile.cfg]文件（其名称可能类似于[!DNL profile.cfg.offline]）的示例配置文件。

1. 使用文本编辑器（如记事本）打开[!DNL profile.cfg]文件，并执行以下操作：

   1. 在“目录”矢量中添加内部配置文件的条目。 配置文件名称对应于您复制到[!DNL Insight Server]计算机上[!DNL Profiles]文件夹的目录名称。

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
      >您在[!DNL profile.cfg]文件中为“公用名称”指定的&#x200B;*serverCommonName*&#x200B;对应于您正在处理并运行数据集配置文件的[!DNL Insight Server]计算机的服务器通用名称。 有关更新[!DNL profile.cfg]以使数据集配置文件在[!DNL Insight Server]群集上运行的说明，请参阅[Insight Server群集](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)。

1. 保存文件。如果文件的名称不同，请务必将其另存为[!DNL profile.cfg]。

**为Adobe应用程序安装查找文件**

1. 从通过Adobe提供给您的[!DNL .zip]文件中打开[!DNL Lookups]文件夹。

1. 将[!DNL .zip]文件[!DNL Lookups]文件夹内的所有文件夹复制到[!DNL Insight Server]安装目录的[!DNL Lookups]文件夹中。 您希望在[!DNL Insight Server]上最终使用&#x200B; [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>*&#x200B;文件夹，如以下示例所示。 您的实际配置文件名称可能会有所不同。

   ![](assets/win_installLookups.png)
