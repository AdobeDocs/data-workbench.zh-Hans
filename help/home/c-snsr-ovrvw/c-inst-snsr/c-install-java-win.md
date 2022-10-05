---
description: 在Windows Server 2000或更高版本下运行的Sun Java System Application Server Standard Edition 7传感器安装和配置说明。
title: Windows Server 2000 或更高版本上的 Sun Java 服务器
uuid: 43f3eee0-2633-4bda-af6c-6c15433dd539
exl-id: 33f24073-8eff-4bf6-8f83-7a122d1505d8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 3%

---

# Windows Server 2000 或更高版本上的 Sun Java 服务器{#sun-java-server-on-windows-server-or-later}

{{eol}}

在Windows Server 2000或更高版本下运行的Sun Java System Application Server Standard Edition 7传感器安装和配置说明。

传感器的程序文件打包在从Adobe下载站点获取的安装文件中。 如果您还没有特定Web服务器的传感器安装文件，请先下载它(或从Adobe代表处获取它)，然后再开始执行以下步骤。

传感器支持在RedHat Linux 7.x或更高版本或Sun Solaris SPARC 2.6或更高版本下运行的以下服务器：

要安装和配置传感器，必须执行以下步骤：

## 安装程序文件 {#section-2f3e85083b4f4aa989a85997330e86ae}

将传感器的程序文件解压缩并安装到服务器的过程。

1. 在Netscape Enterprise、iPlanet、Sun ONE或Sun Java System Server上，创建一个目录以在其中安装传感器程序文件。 请记住，您的磁盘队列位于此目录中，因此请确保您选择的设备有足够的空间容纳所需大小的队列。

   ```
   C:\VisualSensor
   ```

1. 将安装文件的内容解压缩到刚刚创建的目录中。 在此步骤中，传感器安装以下文件：

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 目标目录 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> saf_visual_sciences.dll </td> 
   <td colname="col2"> 收集器负载模块。 </td> 
   <td colname="col3"> <i>/usr/local/aolserver/ visual sciences</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> 发送程序。 </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--或者--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 传感器配置文件。 </td> 
   <td colname="col3"> <i>/等</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用于验证Insight Server在连接过程中显示的数字证书的证书 </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安装包包含一个名为TestExperience.xls的电子表格文件。 此电子表格是一种用于架构师配置受控实验的工具。 传感器本身不使用此文件，因此不必在运行传感器的计算机上安装该文件（尽管您可以选择这样做）。 您可能希望将文件复制到架构师可以访问的位置，或者根据需要从安装包中提取文件。 有关对照实验的更多信息，请参阅《Insight对照实验指南》。

## 编辑传感器配置文件 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

的 [!DNL txlogd.conf] 文件包含传感器的配置参数。

您必须编辑此文件以指定磁盘队列文件的大小和位置、 Insight Server的地址以及将附加到此传感器生成的事件数据的ID等内容。

配置文件包含必需的参数和可选参数。

* **必需的参数** 是安装传感器时必须指定的设置。 如果没有这些设置，传感器将无法成功运行。
* **可选参数** 是默认设置，用于预定义值（您可以对其进行修改）或启用可选功能。

**编辑传感器配置文件**

* 打开 [!DNL /etc/txlogd.conf] 文件，并设置所需的参数以及任何所需的可选参数。
* 保存并关闭该文件。

**编辑传感器配置文件**

1. 打开 [!DNL /etc/txlogd.conf] 文件，并设置所需的参数以及任何所需的可选参数。
1. 保存并关闭该文件。

## 启动发送器并创建磁盘队列 {#section-55630de65f264274aefd771da2002852}

配置txlogd.conf文件后，可以启动发送器程序，将其注册为Windows服务，然后创建磁盘队列。

1. 从Windows的“开始”菜单中，选择“附件”>“命令提示符”。
1. 在命令提示符窗口中，导航到安装传感器的目录并执行以下命令：

   ```
   txlog /regserver
   ```

   此命令启动发送器，创建磁盘队列，并将传感器注册为Windows服务。

1. 要确认发送器运行正确，请单击开始>控制面板>管理工具>服务。 在服务列表中，找到传感器的条目，并确认其状态为“已启动”且其启动类型为“自动”。 然后，关闭“服务”控制面板。
1. 要检查发送器在启动过程中是否遇到任何错误，请单击开始>控制面板>管理工具>事件查看器以打开事件查看器。

   1. 在事件查看器窗口的左窗格中，选择应用程序日志。
   1. 在右侧窗格中，查找“源”列中包含“Adobe”的事件。
   1. 如果从“Adobe”中找到错误，请双击该错误以显示“事件属性”窗口。 此窗口提供有关错误的详细信息。

1. 检查完应用程序日志后，关闭事件查看器。
1. 确认发送器已在安装传感器程序文件的目录中创建了磁盘队列(Diskq2000.log)，并且该磁盘队列的大小是您在txlogd.conf文件的QueueSize参数中指定的大小。

   如果队列未正确创建：

   1. 检查txtlogd.conf文件，并验证QueueSize参数是否已正确设置。
   1. 检查安装传感器的设备是否有足够的空间来存放QueueSize参数中指定大小的文件。
   1. 在Windows中使用“服务”控制面板，停止发送器。
   1. 删除队列文件。
   1. 将传感器重新注册为Windows服务：从Windows的“开始”菜单中，选择“附件”>“命令提示符”。 在命令提示符窗口中，导航到安装传感器的目录并执行以下命令：

      ```
      txlog /regserver
      ```

发射机设计为连续运行。 如果重新启动计算机，则发送器会自动重新启动。 如果需要手动启动和停止发送器，可以使用Windows中的“服务”控制面板执行此操作。

## 修改启动脚本 {#section-19a38f27c9f44adf88f8910f5ed483a3}

在init.conf文件(例如C:\Sun\AppServer7\domains\domain1\server1\config\ init.conf)中，在文件末尾添加以下行：

```
Init fn="load-modules" shlib="C:/VisualSciences/saf_visual_sciences.dll" 
funcs="vys-cookie,vys-log,vys-init,vys-content-type" 
Init fn="vys-init" config-file="C:/VisualSciences/txlogd.conf"
```

在obj.conf文件(例如C:\Sun\AppServer7\domains\domain1\server1\config\ server1-obj.conf)中，将以下行添加到现有 `<Object name="default">` 行：

```
NameTrans fn="vys-cookie" 
ObjectType fn="vys-content-type" 
AddLog fn="vys-log"
```
