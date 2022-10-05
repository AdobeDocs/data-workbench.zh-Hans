---
description: 有关在Web服务器系列上安装和配置传感器的说明，这些Web服务器系列是从在Linux或Solaris计算机上运行的原始Netscape Enterprise Web Server演变而来的。 包括Linux或Solaris上的Netscape Enterprise 、 iPlanet 、 Sun ONE和Sun Java System Server。
title: Linux 或 Solaris 上的 Netscape Enterprise
uuid: 47ea614c-d45c-4ab4-a8fe-ed9227da4582
exl-id: bd2e50b9-94fe-4f05-b227-11e83eb0a665
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 1%

---

# Linux 或 Solaris 上的 Netscape Enterprise{#netscape-enteprise-on-linux-or-solaris}

{{eol}}

有关在Web服务器系列上安装和配置传感器的说明，这些Web服务器系列是从在Linux或Solaris计算机上运行的原始Netscape Enterprise Web Server演变而来的。 包括Linux或Solaris上的Netscape Enterprise 、 iPlanet 、 Sun ONE和Sun Java System Server。

传感器的程序文件打包在从Adobe下载站点获取的安装文件中。 如果您还没有特定Web服务器的传感器安装文件，请先下载它(或从Adobe代表处获取它)，然后再开始执行以下步骤。

传感器支持在RedHat Linux 7.x或更高版本或Sun Solaris SPARC 2.6或更高版本下运行的以下服务器：

* Netscape Enterprise Server 3.6或更高版本
* iPlanet Web Server 4.0或更高版本

传感器支持在RedHat Linux 7.x或更高版本或Sun Solaris 8.x或更高版本下运行的这些服务器：

* Sun ONE Web Server 6.0或更高版本
* Sun Java System Web Server 6.1或更高版本

传感器支持在Sun Solaris x86 9或更高版本下运行的这些服务器：

* Sun Java System Web Server 6.1或更高版本

>[!NOTE]
>
>此系列Web服务器的安装文件在Adobe下载站点上列为“Netscape Solaris传感器”或“Netscape LINUX传感器”。

要安装和配置传感器，必须执行以下步骤：

## 安装程序文件 {#section-2f3e85083b4f4aa989a85997330e86ae}

提取和安装传感器程序文件的过程。

1. 以根用户或具有根权限的用户身份登录。
1. 使用以下命令解压缩并解压缩安装文件：

   ```
   gunzip installationFilename.tar.gz 
   
       tar -xf installationFilename.tar
   ```

1. 将解压缩的程序文件复制到下表中标识的目录：

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
   <td colname="col1"> aol_visual_sciences.so </td> 
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

**对程序文件的权限**

>[!NOTE]
>
>对程序文件的权限不正确会导致安装传感器时遇到的大多数问题。 请确保您完全按照此部分中的说明设置权限。
>
>默认情况下，tar文件中的程序文件具有以下权限。 根据您的系统配置方式，在提取文件时，可能会更改（未屏蔽）这些设置。 要将权限重置为建议的默认设置，请使用下面的chmod命令。 检查已安装文件的目录是否至少允许此级别的访问。

| 文件 | 默认权限 | chmod命令 |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx -x -x | chmod 711 |
| txlogd.conf | rw- r— r. | chmod 664 |
| trust_ca_cert.pem | rw- r— r. | chmod 664 |

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

1. 如果磁盘队列所在的目录不存在，请创建该目录。 确保目录为收集器模块和发送器程序提供对文件的读/写访问权限。

   有关磁盘队列文件所需权限的详细信息，请参阅传感器UNIX文件权限。
1. 在安装传感器的计算机上，执行以下命令以启动发送器：

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * 此命令中的“i”选项以“交互模式”启动发送器。 此模式在屏幕上显示发送器消息，还允许您使用键盘命令与发送器进行交互。
   * “c”选项将指导发送器创建磁盘队列。
   * “f”选项指定配置文件的位置。

   有关启动发射器时可使用的选项的其他信息，请参阅传感器发射器命令行选项。

1. 验证发送器是否已在QueueFile参数中指定的位置和QueueSize参数中指定的大小中创建磁盘队列。
1. 如果队列未正确创建，请按Ctrl+C终止发送器，然后执行以下操作：

   1. 检查txtlogd.conf文件，并验证QueueFile和QueueSize参数是否已正确设置。
   1. 检查为其分配磁盘队列的设备是否运行正常，并有足够的空间来存放QueueSize参数中指定大小的文件。
   1. 进行任何必要的更正并重复此过程。

## 将收集器添加到AOL服务器 {#section-c5b83ae4ebce430aa764f951e849b333}

对于AOLServer，收集器是一个动态共享对象，可加载到Web服务器进程中。

要将收集器添加到AOL服务器，您必须按如下所述编辑服务器的配置文件，然后重新启动AOL服务器。 通常，服务器的配置文件名为nsd.tcl，位于安装AOL Server的目录中。

1. 在文本编辑器中打开配置文件，并找到以下部分：

   ```
   ns_section "ns/server/${servername}/modules" 
   ```

1. 添加以下行。 (添加为单个语句。 忽略下面显示的自动换行。)

   ```
   ns_param aol_visual_sciences /usr/local/aolserver/visual_sciences/aol_visual_sciences.so 
   ```

1. 按如下方式创建新部分。

   ```
   ns_section "ns/server/${servername}/module/aol_visual_sciences"
   ```

1. 要添加此新部分，请添加以下行：

   ```
   ns_param    VisualSciencesConfig    /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >这些行区分大小写。 完全按上面显示的方式键入它们。

1. 重新启动AOL服务器。 收集器已加载，并将开始收集事件数据并将其写入磁盘队列。

## 测试传感器 {#section-0dae181ef8884f10a57f6cfda8500969}

验证收集器是否正在收集事件数据，以及发送器是否正在将其传输到目标Insight Server。

>[!NOTE]
>
>要验证发送器是否可以将事件数据成功发送到Insight Server，请确保目标Insight Server已安装并正在运行，然后才能开始进行以下测试。

1. 如果发送器尚未运行，请使用以下命令重新启动它：

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. 打开浏览器（在任何计算机上），并从运行传感器的Web服务器中请求一个页面（确保选择传感器正在监视的页面）。
1. 发出请求后，检查发送器的控制台中是否有消息，指示发送器正在向目标Insight Server发送事件数据。
1. 如果传感器未成功传输数据，请验证：

   * 目标Insight Server正在运行。
   * 在txtlogd.conf中正确设置了ServerAddress和ServerPort参数。 如果您使用服务器名称指定了ServerAddress ，请尝试改用其数字IP地址。
   * CertName参数的值与目标Insight Server的数字证书上显示的通用名称完全匹配。

## 将发送器添加到系统启动脚本 {#section-19a38f27c9f44adf88f8910f5ed483a3}

有关自动将发送器加载到系统启动脚本的信息。

要确保发送器在重新启动Web服务器计算机时自动加载，请将以下命令（即启动发送器）添加到系统启动脚本中：

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

此命令将发送器作为守护程序启动。 发送器生成的操作和错误消息被写入 [!DNL syslog].

默认的Solaris设置为60。 根据使用传感器（每个实例使用三个信号）进行的测试，Adobe建议您使用1024作为设置。 此数字足够高，传感器可以与服务器上任何其他可能需要信号但不会影响性能的应用程序一起运行。 为支持这一建议，请注意，Adrian Cockcroft在其《太阳表演与调谐》（Prentice Hall，1994年10月）一书中指出：“数据库往往使用大量共享内存和信号量设置。 这不会影响性能；只要它们足够大，计划就会运行。”
