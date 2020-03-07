---
description: 有关安装和配置Sensor for Apache Server 1.3、Apache Server 2.0.42或更高版本或Apache Server 2.2（运行在Microsoft Windows Server 2000或更高版本下）的说明。
title: Windows Server 2000或更高版本上的Apache Server 1.3、2、2.2或2.4
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Windows Server 2000或更高版本上的Apache Server 1.3、2、2.2或2.4{#apache-server-or-on-windows-server-or-later}

有关安装和配置Sensor for Apache Server 1.3、Apache Server 2.0.42或更高版本或Apache Server 2.2（运行在Microsoft Windows Server 2000或更高版本下）的说明。

传感器的程序文件打包在您从Adobe下载站点获得的安装文件中。 如果您还没有特定Web服务器的传感器安装文件，请在开始以下步骤之前先下载它（或从Adobe代表处获得它）。

* Apache Server 1.3
* Apache Server 2.0.42或更高版本
* 在Microsoft Windows Server 2000或更高版本下运行的Apache Server 2.2

## 安装程序文件 {#section-2f3e85083b4f4aa989a85997330e86ae}

在安装程序文件之前，必须确定要维护磁盘队列的位置，因为这也是必须安装程序文件的位置。提取和安装传感器程序文件的过程。

要安装和配置传感器，必须执行以下步骤：

1. 在Windows计算机上，创建一个用于安装传感器程序文件的目录。 请记住，您的磁盘队列也位于此目录中，因此，请确保您选择的设备有足够的空间容纳所需大小的队列。

   ```
   C:\VisualSensor
   ```

1. 将安装文件的内容解压缩到刚刚创建的目录中。 在此步骤中，传感器会安装以下文件：

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File（文件） </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> 活动查看器消息。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> 收集器模块。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperience.xls </p> </td> 
   <td colname="col2"> <p>架构师可用于配置受控实验的Excel电子表格文件。 传感器不使用此文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用于验证Insight Server在连接过程中显示的数字证书的证书。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> 发射机程序 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 传感器配置文件 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安装包中包含一个名为TestExperice.xls的电子表格文件。 此电子表格是架构师用来配置受控实验的工具。 传感器本身不使用此文件，因此不必在运行传感器的计算机上安装该文件（尽管您可以选择这样做）。 您可能希望将文件复制到架构师可以访问的位置，或根据需要从安装包中提取文件。 有关受控实验的详细信息，请参阅《Insight Controlled Experies Guide》（Insight控制实验指南）。

## 编辑传感器配置文件 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

该文 [!DNL txlogd.conf] 件包含传感器的配置参数。

您必须编辑此文件以指定磁盘队列文件的大小和位置、Insight Server的地址以及将附加到此传感器生成的事件数据的ID等。

配置文件包含必需参数和可选参数。

* **必需参数** ，是安装传感器时必须指定的设置。 如果没有这些设置，传感器将无法成功运行。
* **可选参数** ，是默认为预定义值（您可以修改）或启用可选功能的设置。

**编辑传感器配置文件**

* 在文本 [!DNL /etc/txlogd.conf] 编辑器中打开文件，并设置所需的参数以及任何所需的可选参数。
* 保存并关闭该文件。

**编辑传感器配置文件**

1. 在文本 [!DNL /etc/txlogd.conf] 编辑器中打开文件，并设置所需的参数以及任何所需的可选参数。
1. 保存并关闭该文件。

## 启动发射器并创建磁盘队列 {#section-55630de65f264274aefd771da2002852}

配置txlogd.conf文件后，可启动发射器程序，将其注册为Windows服务，并创建磁盘队列。

1. 如果磁盘队列所在的目录尚不存在，请创建它。 确保目录为收集器模块和发射机程序提供对文件的读／写访问。

   有关磁盘队列文件所需权限的详细信息，请参阅传感器UNIX文件权限。
1. 在安装了传感器的计算机上，执行以下命令以启动发射器：

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * 此命令中的“i”选项以“交互模式”启动发射器。此模式在屏幕上显示发射机消息，还允许您使用键盘命令与发射机进行交互。
   * “c”选项指示发射器创建磁盘队列。
   * “f”选项指定配置文件的位置。
   有关启动发射器时可使用的选项的其他信息，请参阅传感器发射器命令行选项。

1. 验证发射器是否已在QueueFile参数中指定的位置和QueueSize参数中指定的大小中创建磁盘队列。
1. 如果未正确创建队列，请键入Ctrl+C以终止发射器，然后执行以下操作：

   1. 检查txtlogd.conf文件并验证QueueFile和QueueSize参数设置是否正确。
   1. 检查为其分配磁盘队列的设备是否可操作，并具有足够的可用空间来容纳QueueSize参数中指定大小的文件。
   1. 请进行任何必要的更正并重复此过程。

## 将收集器添加到Web服务器 {#section-c5b83ae4ebce430aa764f951e849b333}

对于Apache服务器，收集器是加载到Web服务器进程中的动态共享对象。

要将收集器添加到Web服务器，必须按照下面所述编 [!DNL httpd.conf] 辑文件并重新启动Web服务器。

>[!NOTE]
>
>如果传感器正在为服务器计算机上的多台Web服务器捕获数据，则必须对每台Web服务器执行以下过程。

1. 使用文本编辑器，打开Sensor [!DNL httpd.conf]捕获其事件的Web服务器的文件。
1. 在文件末尾添加以下两行：

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >这些行区分大小写。 完全按上面显示的方式键入它们。

1. 重新启动Web服务器进程（您不必重新启动整个服务器计算机，只需重新启动Web服务器进程）。 收集器加载了Web服务器，开始收集事件数据并将其写入磁盘队列。

