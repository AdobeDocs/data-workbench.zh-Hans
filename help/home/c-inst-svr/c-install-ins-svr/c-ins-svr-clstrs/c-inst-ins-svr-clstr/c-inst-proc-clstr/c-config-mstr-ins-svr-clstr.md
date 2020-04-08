---
description: 有关在主Insight Server上配置群集、更新群集的访问控制文件等的信息。
solution: Insight
title: 为群集配置主Insight Server
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
translation-type: tm+mt
source-git-commit: b5a22e7a050d7c01570286dcb54e368f7ecdbcd8

---


# 为群集配置主Insight Server{#configuring-the-master-insight-server-for-clustering}

有关在主Insight Server上配置群集、更新群集的访问控制文件等的信息。

要配置群集，请在主设备上执行以下步骤 [!DNL Insight Server]:

* 将处理公 [!DNL Insight Servers’] 用名称和地址添加到地址文件。
* 将所有群集服 [!DNL Insight Servers] 务器组添加到文件中的群集服 [!DNL Access Control.cfg] 务器组。

* 更新“ [!DNL Synchronize.cfg] Components for Processing Servers”（处理服务器组件）目录中的文件以指向主文件 [!DNL Insight Server]。

* 如有必要，请修 [!DNL Disk Files.cfg] 改“处理服务器组件”目录中的文件，以指定文件在处理 [!DNL temp.db] 过程中的位置 [!DNL Insight Servers]。

要完成这些步骤，您需要知道群集中每个用户的通用名称(在个人的数字证书上指定 [!DNL Insight Server])和IP [!DNL Insight Server] 地址。 如果您尚未获得此信息，请在继续之前获取该信息。

>[!NOTE]
>
>本节所述的过程需要 [!DNL Insight]。 如果尚未安装，请 [!DNL Insight]按照用户指南中的说明操 **[!DNL Insight]作&#x200B;**，然后继续。

## 将Processing Insight Server添加到地址文件 {#section-2fe5298180164e8dbaa59ea6b6ff682d}

请按照以下过程将处理公 [!DNL Insight Servers’] 用名称和IP地址添加到主设备上的地址文件中 [!DNL Insight Server]。 (尽管在主设备上维护和管理地址文 [!DNL Insight Server]件，但群集中的所有用户 [!DNL Insight Servers] 都使用它。)

>[!NOTE]
>
>以下假设地址文件已经为主文件配置 [!DNL Insight Server]。 如果尚未将主 [!DNL Insight Server’s] IP地址添加到地址文件，请在开始之前完成定义服务器网络位置 [中所述的过程](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) 。

**将处理添加到[!DNL Insight Servers]地址文件**

1. 开始 [!DNL Insight] 并加载配置用户档案（如果尚未打开），方法是右键单击标题栏并单击 **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**。

1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。

1. 右键单击主视图的图标，然 **[!UICONTROL Insight Server]** 后单击 **[!UICONTROL Server Files]**。

1. 在中， [!DNL Server Files Manager]打开Addresses目录，然后执行以下操作以打开地 [!DNL Insight Server’s] 址文件：

   1. 右键单击服务器名称列中的复 *选标记* ，然后单击 **[!UICONTROL Make Local]**。

   1. 右键单击列中的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 展开结构的内 [!DNL Locations] 容，然后展开NetworkLocation 0、Address和AddressDefinition。
1. 执行以下操作，为群集中的每个处理将AddressDefinition添 [!DNL Insight Server] 加到NetworkLocation 0:

   1. 右键单击 **[!UICONTROL AddressDefinition]** 并单击 **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**。

   1. 在“名称”参数中，指定处理公 [!DNL Insight Server’s] 用名称。
   1. 在“地址”参数中，指定处理 [!DNL Insight Server’s] IP地址。

      您可以在“地址”字段中使用星号作为通配符，如10.10.116。*，简化群集。 请参阅 [了解访问级别](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a)。

      以下示例定义了包含两个群集的群集 [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. 如果服务器已连接到多个网络，请重复步骤6，将处理添加 [!DNL Insight Servers] 到这些网络的NetworkLocations。

   以下示例展示了一个四个群集， [!DNL Insight Servers] 它们连接到两个网络（“公司内部网”和“因特网”）。

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]右键单击列中文件的复选标记，然 [!DNL Temp] 后选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

## 更新群集的访问控制文件 {#section-fce1367d92a445168c35e9ca506e7d6b}

要在群 [!DNL Insight Servers] 集中使用，群集中 [!DNL Insight Server] 的每个(包括主服务器 [!DNL Insight Server])必须属于群集服务器访问控制组。 群集服务器组标识允许参加群集的服务器（按IP地址）。 尽管此文件在主设备上进行维护和管 [!DNL Insight Server]理，但群集中的所有成员都 [!DNL Insight Servers] 使用它。

**编辑访问控制文件**

1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。

1. 右键单击主视图的图标，然 [!DNL Insight Server] 后单击 **[!UICONTROL Server Files]**。

1. 在中， [!DNL Server Files Manager]打开访问控制目录。
1. 执行以下操作以打开文 [!DNL Access Control.cfg] 件：

   1. 右键单击服务器名称列中的复 *选标记* ，然后单击 **[!UICONTROL Make Local]**。

   1. 右键单击列中的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 展开访问控制组结构，然后展开AccessGroup（群集服务器）。
1. 对于群 [!DNL Insight Server] 集中的每个(包括主群集 [!DNL Insight Server])，请执行以下操作：

   1. 右键单击 **[!UICONTROL Members]** 并单击 **[!UICONTROL Add New]** > **[!UICONTROL New Member]**。

   1. 指定 [!DNL Insight Server’s] IP地址（其数字IP地址，而非其名称）。 如果连 [!DNL Insight Servers] 接到多个网络，则此AccessGroup应仅包含群集中用于服务器间通 [!DNL Insight Servers] 信的内部地址。

      下面显示了四个群集的AccessGroup（群集服务器） [!DNL Insight Servers]。

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]右键单击列中文件的复选标记，然 [!DNL Temp] 后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

## 配置同步文件 {#section-d23e751771c84da6bab6a34a8db867bc}

您可以使用以下过程配置文件的中心副 [!DNL Synchronize.cfg] 本。 此文件的中心副本将保留在主文件上 [!DNL Insight Server]。 群集中 [!DNL Insight Servers] 的处理会启动与主设备的通信， [!DNL Insight Server] 以检索此文件的更新副本。

文 [!DNL Synchronize.cfg] 件指定主视图的位置 [!DNL Insight Server]。 它还标识群集中每个处理从主设备检索 [!DNL Insight Servers] 的管理文件集 [!DNL Insight Server]。 当这些文 [!DNL Insight Servers] 件开始时，处理过程会自 [!DNL Insight Server] 动从主文件下载。 当文件发生更改时，他们还会从主文件中动态检索 [!DNL Insight Server] 这些文件的更新副本。

>[!NOTE]
>
>尽管在主设备上 [!DNL Synchronize.cfg] 配置了该文件， [!DNL Insight Server]但主设备 [!DNL Insight Server] 本身不使用此文件。 在主设备上更新此文件， [!DNL Insight Server] 以便在处理检索文件时正确配 [!DNL Insight Servers] 置该文件。

**更新主设备上的Synchronize.cfg文件[!DNL Insight Server]**

1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。

1. 右键单击主视图的图标，然 [!DNL Insight Server] 后单击 **[!UICONTROL Server Files]**。

1. 在中， [!DNL Server Files Manager]打开“处理服 **[!UICONTROL Components]** 务器”目录。

1. 执行以下操作以打开 [!DNL Synchronize.cfg]:

   1. 右键单击服务器名称列中的复 *选标记* ，然后单击 **[!UICONTROL Make Local]**。

   1. 右键单击复选 [!DNL Temp] 标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 展开组件结构。
1. 在“群集主服务器地址”参数中，指定主服务器（主服务器）的IP地址 **[!UICONTROL Insight Server]**。

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   要创建记录每次在主设备与处理设备之间进行同 [!DNL Insight Server] 步的日志 [!DNL Insight Servers]，请确保将“启用同步日志”参数设置为“true”。

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在 [!DNL Server Files Manager]中，右键单击列中文件的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

## 配置数据集(temp.db)的位置 {#section-5ec257a4b4c64fb58baec1f12119a822}

如果您希望处理过程在与默认位置不同的 [!DNL Insight Servers] 目录 [!DNL temp.db] 或驱动器中进行维护（数据集），或者如果您希望分发到多个驱动器，请执行以 [!DNL temp.db] 下过程。

>[!NOTE]
>
>由于处理 [!DNL Insight Servers] 都共享相同 [!DNL Disk Files.cfg]的内容，它们都必须支持您在此文件中指定的文件位置。 例如，如果您将E [!DNL temp.db] 分配给：驱动器，群集中 [!DNL Insight Server] 的每个处理都必须具有E:开车。

**配置temp.db的位置**

1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。

1. 右键单击主视图的图标，然 [!DNL Insight Server] 后单击 **[!UICONTROL Server Files]**。

1. 在中， [!DNL Server Files Manager]打开该目 **[!UICONTROL Components for Processing Servers]** 录。

1. 执行以下操作以打开 [!DNL Disk Files.cfg]:

   1. 右键单击服务器名称列中的复 *选标记* ，然后单击 **[!UICONTROL Make Local]**。

   1. 右键单击列中的复选标记， [!DNL Temp]然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 展开DiskSpaceManagerComponent结构，然后展开“磁盘文件”列表。
1. 编辑条目0以更改文件的位 [!DNL temp.db] 置。
1. 如果您希望跨多个驱 [!DNL temp.db] 动器进行分发，请使用以下步骤为每个额外驱动器创建一个额外的条目。

   1. 右键单击 **[!UICONTROL Disk Files]** 并单击 **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**。

   1. 在新条目中，指定要写入的位置 [!DNL temp.db] 。
   以下是跨四个驱 [!DNL temp.db] 动器编写的内容。

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在 [!DNL Server Files Manager]中，右键单击列中文件的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

