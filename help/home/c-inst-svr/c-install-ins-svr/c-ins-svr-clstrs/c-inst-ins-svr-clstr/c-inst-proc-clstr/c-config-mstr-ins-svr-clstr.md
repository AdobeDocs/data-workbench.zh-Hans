---
description: 有关在主控Insight Server上配置群集、更新群集的访问控制文件等信息。
title: 配置聚类的主 Insight Server
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# 配置聚类的主 Insight Server{#configuring-the-master-insight-server-for-clustering}

有关在主控Insight Server上配置群集、更新群集的访问控制文件等信息。

要配置群集，请对主控[!DNL Insight Server]执行以下步骤：

* 将处理[!DNL Insight Servers’]的常用名称和地址添加到地址文件。
* 将所有[!DNL Insight Servers]添加到[!DNL Access Control.cfg]文件中的群集服务器组。

* 更新“Components for Processing Servers”（处理服务器组件）目录中的[!DNL Synchronize.cfg]文件以指向主控[!DNL Insight Server]。

* 如有必要，请修改“Components for Processing Servers”（处理服务器组件）目录中的[!DNL Disk Files.cfg]文件，以指定处理[!DNL Insight Servers]中[!DNL temp.db]文件的位置。

要完成这些步骤，您需要了解群集中每个[!DNL Insight Server]的公用名称（如单个[!DNL Insight Server]的数字证书中指定）和IP地址。 如果您尚未获得此信息，请在继续之前获取该信息。

>[!NOTE]
>
>本节中描述的过程需要[!DNL Insight]。 如果尚未安装[!DNL Insight]，请按照&#x200B;**[!DNL Insight]用户指南**&#x200B;中的说明继续操作。

## 将Processing Insight Server添加到地址文件{#section-2fe5298180164e8dbaa59ea6b6ff682d}

请按照以下过程将处理[!DNL Insight Servers’]公用名称和IP地址添加到主控[!DNL Insight Server]的地址文件中。 (尽管在主控[!DNL Insight Server]上维护和管理地址文件，但群集中的所有[!DNL Insight Servers]都使用它。)

>[!NOTE]
>
>以下假设已为主控[!DNL Insight Server]配置了地址文件。 如果尚未将主控的[!DNL Insight Server’s] IP地址添加到地址文件，请在开始之前完成[定义服务器的网络位置](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)中所述的过程。

**将处理添加 [!DNL Insight Servers] 到地址文件**

1. 开始[!DNL Insight]并加载配置用户档案（如果尚未打开），方法是右键单击标题栏，然后单击&#x200B;**[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**。

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开Servers Manager工作区。

1. 右键单击主控&#x200B;**[!UICONTROL Insight Server]**&#x200B;的图标，然后单击&#x200B;**[!UICONTROL Server Files]**。

1. 在[!DNL Server Files Manager]中，打开Addresses目录，然后执行以下操作以打开[!DNL Insight Server’s]地址文件：

   1. 右键单击&#x200B;*服务器名称*&#x200B;列中的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。

   1. 右键单击[!DNL Temp]列中的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 展开[!DNL Locations]结构的内容，然后展开NetworkLocation 0、Address和AddressDefinition。
1. 请执行以下操作，为群集中的每个处理[!DNL Insight Server]添加一个AddressDefinition到NetworkLocation 0:

   1. 右键单击&#x200B;**[!UICONTROL AddressDefinition]** ，然后单击&#x200B;**[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**。

   1. 在“名称”参数中，指定处理[!DNL Insight Server’s]公用名称。
   1. 在“地址”参数中，指定处理的[!DNL Insight Server’s] IP地址。

      您可以在地址字段中使用星号作为通配符，如10.10.116。*，简化群集。 请参阅[了解访问级别](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a)。

      下面的示例定义包含两个[!DNL Insight Servers]的群集：

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. 如果服务器已连接到多个网络，请重复步骤6，将处理[!DNL Insight Servers]添加到这些网络的NetworkLocations中。

   以下示例显示了一个群集，该群集由四个[!DNL Insight Servers]连接到两个网络（“公司内部网”和“Internet”）。

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，右键单击[!DNL Temp]列中文件的复选标记，然后选择&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

## 更新群集{#section-fce1367d92a445168c35e9ca506e7d6b}的访问控制文件

要在群集中使用[!DNL Insight Servers]，群集中的每个[!DNL Insight Server](包括主控[!DNL Insight Server])必须属于群集服务器访问控制组。 群集服务器组标识允许参加群集的服务器（按IP地址）。 虽然此文件在主控[!DNL Insight Server]上进行维护和管理，但群集中的所有[!DNL Insight Servers]都使用它。

**编辑访问控制文件**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开Servers Manager工作区。

1. 右键单击主控[!DNL Insight Server]的图标，然后单击&#x200B;**[!UICONTROL Server Files]**。

1. 在[!DNL Server Files Manager]中，打开访问控制目录。
1. 执行以下操作以打开[!DNL Access Control.cfg]文件：

   1. 右键单击&#x200B;*服务器名称*&#x200B;列中的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。

   1. 右键单击[!DNL Temp]列中的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 展开“访问控制组”结构，然后展开AccessGroup（群集服务器）。
1. 对于群集中的每个[!DNL Insight Server](包括主控[!DNL Insight Server])，执行以下操作：

   1. 右键单击&#x200B;**[!UICONTROL Members]** ，然后单击&#x200B;**[!UICONTROL Add New]** > **[!UICONTROL New Member]**。

   1. 指定[!DNL Insight Server’s] IP地址（其数字IP地址，而非名称）。 如果[!DNL Insight Servers]连接到多个网络，则此AccessGroup应仅包含[!DNL Insight Servers]在群集中用于服务器间通信的内部地址。

      下面显示了四个[!DNL Insight Servers]群集的AccessGroup（群集服务器）。

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，右键单击[!DNL Temp]列中文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

## 配置同步文件{#section-d23e751771c84da6bab6a34a8db867bc}

可以按照以下过程配置[!DNL Synchronize.cfg]文件的中心副本。 此文件的中心副本将保留在主控[!DNL Insight Server]上。 群集中的处理[!DNL Insight Servers]将启动与主控[!DNL Insight Server]的通信，以检索此文件的更新副本。

[!DNL Synchronize.cfg]文件指定主控[!DNL Insight Server]的位置。 它还标识群集中每个处理[!DNL Insight Servers]都从主控[!DNL Insight Server]检索的管理文件集。 处理[!DNL Insight Servers]会在文件开始时从主控[!DNL Insight Server]自动下载这些文件。 当文件发生更改时，他们还会从主控[!DNL Insight Server]中动态检索这些文件的更新副本。

>[!NOTE]
>
>尽管在主控[!DNL Insight Server]上配置了[!DNL Synchronize.cfg]文件，但主控[!DNL Insight Server]本身不使用此文件。 在主控[!DNL Insight Server]上更新此文件，以便在处理[!DNL Insight Servers]检索文件时正确配置它。

**在主控上更新Synchronize.cfg文件[!DNL Insight Server]**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开Servers Manager工作区。

1. 右键单击主控[!DNL Insight Server]的图标，然后单击&#x200B;**[!UICONTROL Server Files]**。

1. 在[!DNL Server Files Manager]中，打开“处理服务器”目录的&#x200B;**[!UICONTROL Components]**。

1. 执行以下操作以打开[!DNL Synchronize.cfg]:

   1. 右键单击&#x200B;*服务器名称*&#x200B;列中的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。

   1. 右键单击[!DNL Temp]复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 展开组件结构。
1. 在“群集主服务器地址”参数中，指定主控（主）**[!UICONTROL Insight Server]**&#x200B;的IP地址。

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   要创建记录每次在主控[!DNL Insight Server]和处理[!DNL Insight Servers]之间进行同步时的日志，请确保将“启用同步日志”参数设置为“true”。

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，右键单击[!DNL Temp]列中文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

## 配置数据集 (temp.db) 的位置{#section-5ec257a4b4c64fb58baec1f12119a822}

如果希望处理[!DNL Insight Servers]将[!DNL temp.db]（数据集）维护在不同于默认位置的目录或驱动器中，或者希望将[!DNL temp.db]分发到多个驱动器，请执行以下过程。

>[!NOTE]
>
>由于处理[!DNL Insight Servers]都共享相同的[!DNL Disk Files.cfg]，它们都必须支持您在此文件中指定的文件位置。 例如，如果将[!DNL temp.db]分配给E:驱动器，群集中的每个处理[!DNL Insight Server]都必须具有E:开车。

**配置temp.db的位置**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开Servers Manager工作区。

1. 右键单击主控[!DNL Insight Server]的图标，然后单击&#x200B;**[!UICONTROL Server Files]**。

1. 在[!DNL Server Files Manager]中，打开&#x200B;**[!UICONTROL Components for Processing Servers]**&#x200B;目录。

1. 执行以下操作以打开[!DNL Disk Files.cfg]:

   1. 右键单击&#x200B;*服务器名称*&#x200B;列中的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。

   1. 右键单击[!DNL Temp]列中的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 展开DiskSpaceManagerComponent结构，然后展开“Disk Files”列表。
1. 编辑条目0以更改[!DNL temp.db]文件的位置。
1. 如果要跨多个驱动器分发[!DNL temp.db]，请使用以下步骤为每个额外的驱动器创建一个额外的条目。

   1. 右键单击&#x200B;**[!UICONTROL Disk Files]** ，然后单击&#x200B;**[!UICONTROL Add New]** > **[!UICONTROL Disk File]**。

   1. 在新条目中，指定要写入[!DNL temp.db]的位置。
   下面显示了跨四个驱动器写入的[!DNL temp.db]。

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，右键单击[!DNL Temp]列中文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。
