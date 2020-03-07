---
description: 有关 Insight Server 文件服务器单元和文件服务器配置过程的信息。
solution: Analytics
title: 配置 Data Workbench Server 文件服务器单元
topic: Data workbench
uuid: ccb65952-f017-4434-b2f8-74c274450834
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# 配置 Data Workbench Server 文件服务器单元{#configuring-a-data-workbench-server-file-server-unit}

有关 Insight Server 文件服务器单元和文件服务器配置过程的信息。

<!--
c_abt_file_svr_units.xml
-->

You can configure the data workbench server (InsightServer64.exe) to run as a File Server Unit (FSU) by completing the parameters in the **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** node of the [!DNL Log Processing.cfg] file. When the data workbench server is configured to run as an FSU, it stores source files ( [!DNL .vsl] files, text files, or XML files) that can be accessed quickly by multiple processing servers (DPUs). 当 Data Workbench Server 群集中的 DPU 访问 FSU 以读取日志文件时，它们会彼此划分日志文件，并保证同一个文件不会被多次处理。

>[!NOTE]
>
>在设置FSU（它为由5到10个DPU组成的Data Workbench Server群集提供服务）时，应将群集的主服务器设置为FSU。

有关安装 Data Workbench Server 群集的信息，请参阅《服务器产品安装和管理指南》**。

<!--
c_file_svr_config_proc.xml
-->

如果该位置为远程位置，则正在处理数据的 Data Workbench Server 计算机会连接到指定的远程计算机以读取日志。

在指定作为 FSU 运行的 Data Workbench Server 计算机上，[!DNL Access Control.cfg] 文件可让 DPU 连接到 FSU，并且 [!DNL Communications.cfg] 文件会映射远程数据文件的位置。配置 FSU 的过程步骤如下所示：

1. 在主 Data Workbench Server 上的 [!DNL Log Processing.cfg] 文件中，指定数据源的类型和源的位置。请参阅[指定数据源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383)。

1. 在 FSU 上的 [!DNL Access Control.cfg] 文件中，编辑权限以允许 DPU 连接到 FSU 读取日志数据。请参阅[编辑对文件服务器单元的权限](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef)。

1. 在 FSU 上的 [!DNL Communications.cfg] 文件中，编辑 [!DNL LoggingServer] 和 [!DNL FileServer] 条目的设置来指定日志文件的位置。请参阅[指定日志文件的位置](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0)。

1. 如果您要将数据集配置文件配置为在 Data Workbench Server 群集上运行，则还必须使群集的 FSU 成为构建配置文件所有维度的服务器。（仅限 Data Workbench Server 群集）在 FSU 上的 [!DNL Communications.cfg] 和 [!DNL cluster.cfg] 文件中，添加“normalize server”对应的条目，使 FSU 成为群集中构建所有维度的服务器。请参阅[为群集创建集中标准化服务器](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28)。

有关配置数据集配置文件以供 Data Workbench Server 群集处理的说明，请参阅《服务器产品安装和管理指南》**。

>[!NOTE]
>
>以下说明假定所有日志文件都位于默认目录中。 如果要在其他目录中存储日志或创建多个日志路径，请联系 Adobe 咨询服务部门来讨论您的具体配置。

## 指定数据源 {#section-d2b545db7ab142ffb4be32e040395383}

在为数据集指定远程数据源时，您必须指定数据源的类型以及日志文件在主 Data Workbench Server 上的位置。

**指定数据源及其位置**

1. 打开 [!DNL Log Processing.cfg] 文件. See [Editing the Log Processing Configuration File](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

1. Add a [!DNL Sensor], log file, or XML data source. See [Log Files](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. 完成“日志路径”参数。 请参 [阅传感器文件](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)、 [日志文件](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)或 [XML日志源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)。 请确保指定有效的 URI。

1. 完成下表中定义的 Log Server（日志服务器）参数：

<table id="table_5881B8DEFF984BC7A620CEEA3A637912"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 标识远程文件服务器的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Server Common Name（SSL 服务器通用名称） </td> 
   <td colname="col2"> <p> 在文件服务器的 SSL 证书上列出的“<span class="wintitle">服务器通用名称</span>”。 </p> <p> 如果 <span class="wintitle">Use SSL</span>（使用 SSL）设为 false，则此参数是可选的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Address（地址） </td> 
   <td colname="col2"> <p>文件服务器计算机的地址。如果 <span class="wintitle">Name</span>（名称）与 <span class="wintitle">SSL Server Common Name</span>（SSL 服务器通用名称）匹配，则此参数可以留空。 </p> <p> 例如：<span class="filepath">visual.mycompany.com</span> 或 192.168.1.90。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port（端口） </td> 
   <td colname="col2"> Data Workbench Server 计算机与文件服务器通信时所用的端口。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate（SSL 客户端证书） </td> 
   <td colname="col2"> Data Workbench Server 的 <span class="wintitle">SSL 证书</span>文件的名称 (<span class="filepath">server_cert.pem</span>)。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use SSL（使用 SSL） </td> 
   <td colname="col2"> true 或 false。true 指示文件服务器使用 <span class="wintitle">SSL</span>。 </td> 
  </tr> 
 </tbody> 
</table>

如果 DPU 需要使用代理服务器才能连接到 FSU，则您需要完成以下参数：

| 参数 | 描述 |
|---|---|
| Proxy Address（代理地址） | Data Workbench Server 访问文件服务器时必须使用的代理服务器的地址。 |
| Proxy Password（代理密码） | 可选。代理服务器的密码。 |
| Proxy Port（代理端口） | 代理服务器的端口。默认值为 8080。 |
| Proxy User Name（代理用户名） | 可选。代理服务器的用户名。 |

Following is an example of a defined [!DNL Log Server] in the [!DNL Log Processing.cfg] file. 日志源 #1 是 LogFile 源，指向名为 FSU01 的计算机上的 Logs 目录（请注意 Log Paths（日志路径）参数中指定的 URI）。

![](assets/cfg_LogProcessing_LogServer.png)

## 编辑对文件服务器单元的权限 {#section-b4a54b591b4e4435a728a67f194057ef}

在上一个过程中，您为给定数据集配置了配置文件以从 FSU 中读取日志文件。现在，您必须编辑对 FSU 的权限才能允许从运行配置文件的 DPU 进行连接。以下步骤将逐步指导您完成编辑权限文件 [!DNL Access Control.cfg] 的过程。

**编辑对 FSU 的权限**

1. Open the [!DNL Server Files Manager] for the data workbench server machine that you are setting up as your FSU and click **[!UICONTROL Access Control]** to show its contents.

   For information about opening and working with the [!DNL Server Files Manager], see the *Data Workbench User Guide*.

1. In the [!DNL Server Files Manager] window, click **[!UICONTROL Access Control]** to show its contents. [!DNL Access Control.cfg] 文件位于此目录中。

1. Right-click the check mark in the server name column for [!DNL Access Control.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Access Control.cfg].

1. 右键单击列下新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**。

1. In the [!DNL Access Control] window, click **[!UICONTROL Access Control Groups]** to show its contents.

1. Right-click the numeric label for the final [!DNL AccessGroup] in the list and click **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. 输入 [!DNL Name] 新字段 [!DNL AccessGroup]。 示例：连接服务器。

1. 右键单击新 **[!UICONTROL Member]** 建的下方 [!DNL AccessGroup]，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Member]**。

1. 输入将连接到此文件服务器的 Data Workbench Server DPU 的 IP 地址。
1. 对任何将连接到此 FSU 的其他 Data Workbench Server DPU（包括群集中必须访问日志文件的 Data Workbench Server DPU）重复执行步骤 4 和 5。
1. 右键单击新 **[!UICONTROL Read-Only Access]** 建的下方 [!DNL AccessGroup]，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL URI]**。

1. 输入日志文件在文件服务器计算机上的存储位置。在指定路径时，请使用正斜杠 (/)。默认位置为 /Logs/。
1. Right-click **[!UICONTROL (modified)]** at the top of the window, then click **[!UICONTROL Save]**.

1. 在窗 [!DNL Server Files Manager] 口中，右键单击列中的复选标记， [!DNL Access Control.cfg] 然后单 [!DNL Temp] 击 **[!UICONTROL Save to]****[!UICONTROL server name]** >以保存对Data Workbench Server的FSU进行的本地更改。

## 指定日志文件的位置 {#section-f9a649bf1b2544feb10ad8820384edb0}

必须编辑 FSU 上的 [!DNL Communications.cfg] 文件以指定日志文件的位置。

**指定日志文件的位置**

1. In the [!DNL Server Files Manager] window, click **[!UICONTROL Components]** to show its contents. [!DNL Communications.cfg] 文件位于此目录中。

1. Right-click the check mark in the server name column for [!DNL Communications.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Communications.cfg].

1. 右键单击列下新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**。

1. In the [!DNL Communications.cfg] window, click **[!UICONTROL component]** to show its contents.

1. In the [!DNL Communications.cfg] window, click **[!UICONTROL Servers]** to show its contents. 可能会显示以下几个服务器：文件服务器、日志记录服务器、初始化服务器、状态服务器、发送服务器或复制服务器。

1. (For [!DNL Sensor] log sources only) Find the [!DNL LoggingServer], which is where [!DNL Sensor] writes its log files to be processed by the data workbench server, then click its number to view the menu. 编辑 Log Directory（日志目录）参数以反映日志文件的所需位置。默认的日志目录为 Data Workbench Server 安装目录中的 Logs 文件夹。

   请勿修改 [!DNL LoggingServer] 的其他任何参数。

   ![](assets/cfg_Communications_LoggingServer.png)

1. 找到用于指定日志文件位置的 FileServer。“服务器”下可能列出了多个文件服务器，因此您可能需要查看其中许多服务器的内容（通过单击服务器编号）来找到所需的服务器。
1. 编辑 FileServer 的 [!DNL Local Path]（本地路径）和 URI 参数以反映日志文件的位置。以下示例显示日志文件位于 Data Workbench Server 安装目录内的 Logs 文件夹中：

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >If the [!DNL Local Path] and URI parameters are populated as shown, you can access the log files on the FSU from any data workbench server by clicking [!DNL Logs] in the [!DNL Server Files Manager].

1. Right-click **[!UICONTROL (modified)]** at the top of the configuration window, then click **[!UICONTROL Save]**.

1. 在窗 [!DNL Server Files Manager] 口中，右键单击列中的复选 [!DNL Communications.cfg] 标 [!DNL Temp] 记，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>* 以保存对Data Workbench Server的FSU所做的本地更改。

## 为群集创建集中标准化服务器 {#section-2c1f57b683f94cc193bc069e886bba28}

如果您要将数据集配置文件配置为在 Data Workbench Server 群集上运行，则应当使群集的 FSU 成为构建配置文件所有维度的服务器。

Adobe 强烈建议将群集的 FSU 用作群集的主服务器及其集中标准化服务器。

若要使 FSU 成为集中标准化服务器，您必须打开 FSU 上的 [!DNL Communications.cfg] 和 [!DNL Cluster.cfg] 文件并对它们进行编辑。

**使 FSU 成为集中标准化服务器**

1. Add a [!DNL NormalizeServer] entry to the [!DNL Communications.cfg] file on the FSU.

   >[!NOTE]
   >
   >If you have installed the complete release package for data workbench server v5.0 or later, the [!DNL Communications.cfg] file on your FSU should have a [!DNL NormalizeServer] entry already. 您可以按照下面的步骤操作来确认该条目已存在。

   1. 按照[!DNL Communications.cfg]指定日志文件的位置[中所述，在 Data Workbench 中打开 ](#section-f9a649bf1b2544feb10ad8820384edb0) 文件。

   1. Click **[!UICONTROL component]** to show its contents.
   1. 右键单击 **[!UICONTROL Servers]** 并单击 **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**。

   1. In the URI parameter for the [!DNL NormalizeServer], type [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. In the [!DNL Server Files Manager] window, right-click the check mark for [!DNL Communications.cfg] in the [!DNL Temp] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server]**>* name to save the locally made changes to the data workbench server FSU.

1. 在 Data Workbench Server 群集主服务器上的 [!DNL Cluster.cfg] 文件中定义集中标准化服务器。

   >[!NOTE]
   >
   >If the FSU on which you are setting up your centralized normalization server is not the master data workbench Server in your cluster, you must add the IP addresses of the DPUs in the cluster to the [!DNL Cluster Servers] access group in the FSU&#39;s [!DNL Access Control.cfg] file. For instructions to add servers to the [!DNL Cluster Servers] group, see Updating the Access Control File for a Cluster section in the *Server Products Installation and Administration Guide.*

   1. Open the [!DNL Profile Manager] within your dataset profile, then click **[!UICONTROL Dataset]** to show its contents. [!DNL Cluster.cfg] 文件位于此目录中。

   1. 右键单击旁边的复选标记 [!DNL Cluster.cfg]，然后单击 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.

   1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。

   1. 添加以下文件片段中突出显示的文本：

      [!DNL Cluster = ClusterConfig:]

      [!DNL Normalize Server = serverInfo:]

      [!DNL Address = string:]

      [!DNL Port = int: 80]

      [!DNL SSL Server Common Name = string: server common name]

      [!DNL Use SSL = bool: false]

      >[!NOTE]
      >
      >When you enter the common name of FSU for the SSL Server Common Name parameter, the FSU uses its [!DNL .address] file to resolve the common name. For information about the [!DNL .address] file, see the *Server Products Installation and Administration Guide*.

   1. 保存文件。
   1. 在中， [!DNL Profile Manager]右键单击列中的复选标记， [!DNL Cluster.cfg] 然后单 [!DNL User] 击> **[!UICONTROL Save to]*****[!UICONTROL dataset profile name]*** ，以保存对数据集配置文件进行的本地更改。
