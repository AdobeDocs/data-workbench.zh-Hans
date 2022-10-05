---
description: 有关在RedHat Linux 7.x或更高版本、SUSE Linux 9.x或更高版本、Sun Solaris SPARC 2.6或更高版本、Sun Solaris x86 9或更高版本、FreeBSD 4或更高版本或Mac OS X PowerPC上为Apache Server 1.3.x安装和配置传感器的详细说明。
title: Linux、Sun Solaris、FreeBSD 或 Mac OS X 上的 Apache Server 1.3.x
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
exl-id: 087494fb-c8f0-457c-b3db-d9147a739998
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---

# Linux、Sun Solaris、FreeBSD 或 Mac OS X 上的 Apache Server 1.3.x{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

{{eol}}

有关在RedHat Linux 7.x或更高版本、SUSE Linux 9.x或更高版本、Sun Solaris SPARC 2.6或更高版本、Sun Solaris x86 9或更高版本、FreeBSD 4或更高版本或Mac OS X PowerPC上为Apache Server 1.3.x安装和配置传感器的详细说明。

传感器的程序文件打包在从Adobe下载站点获取的安装文件中。 如果您还没有特定Web服务器的传感器安装文件，请先下载它(或从Adobe代表处获取它)，然后再开始执行以下步骤。

要安装和配置传感器，必须执行以下高级步骤：

## 安装程序文件 {#section-aae323e252394212bf4096d65fdd280c}

将传感器程序文件解压缩并安装到服务器计算机的说明。

1. 以根用户或具有根权限的用户身份登录。
1. 使用以下命令解压缩并解压缩安装文件：

   * 在Linux上：

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * 在Solaris上：

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. 将解压缩的程序文件复制到下表中标识的目录：

<table id="table_A97CF630633C4543A742D96C302D1138"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文件 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 目标目录 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> 集电器负载模块 </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> 发射机程序 </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--或者-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 传感器配置文件 </td> 
   <td colname="col3"> /等 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用于验证Insight Server在连接过程中显示的数字证书的证书 </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安装包包含一个名为TestExperience.xls的电子表格文件。 此电子表格是一种用于架构师配置受控实验的工具。 传感器本身不使用此文件，因此不必在运行传感器的计算机上安装该文件（尽管您可以选择这样做）。 您可能希望将文件复制到架构师可以访问的位置，或者根据需要从安装包中提取文件。 有关对照实验的更多信息，请参阅《Insight对照实验指南》。

**对程序文件的权限**

对程序文件的权限不正确会导致安装传感器时遇到的大多数问题。

请确保您完全按照此部分中的说明设置权限。

默认情况下，tar文件中的程序文件具有以下权限。 根据您的系统配置方式，在提取文件时，可能会更改（未屏蔽）这些设置。 要将权限重置为建议的默认设置，请使用下面的chmod命令。 检查已安装文件的目录是否至少允许此级别的访问。

| 文件 | 默认权限 | chmod命令 |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx -x -x | chmod 711 |
| txlogd.conf | rw-rw-r— | chmod 664 |
| trust_ca_cert.pem | rw-rw-r— | chmod 664 |

## 编辑传感器配置文件 {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

的 [!DNL txlogd.conf] 文件包含传感器的配置参数。

您必须编辑文件以指定磁盘队列的大小、Insight Server的地址以及将附加到此传感器生成数据的ID等内容。

配置文件包含必需的参数和可选参数。

* 必需参数是安装传感器时必须指定的设置。 如果没有这些设置，传感器将无法成功运行。
* 可选参数是默认设置，用于预定义值（您可以修改）或启用可选功能。

编辑传感器配置文件

1. 在文本编辑器中打开/etc/txlogd.conf文件，并设置所需参数以及任何所需的可选参数。
1. 保存并关闭该文件。

## 启动发送器并创建磁盘队列 {#section-a453d912ec3d47aa8e40ccacf527119d}

配置txlogd.conf文件后创建磁盘队列的说明。

1. 如果磁盘队列所在的目录不存在，请创建该目录。 确保目录为收集器模块和发送器程序提供对文件的读/写访问权限。
1. 在安装传感器的计算机上，执行以下命令以启动发送器：

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * 此命令中的“i”选项以交互模式启动发送器。 此模式在屏幕上显示发送器消息，还允许您使用键盘命令与发送器进行交互。
   * “c”选项将指导发送器创建磁盘队列。
   * “f”选项指定配置文件的位置。

1. 验证发送器是否已在QueueFile参数中指定的位置和QueueSize参数中指定的大小中创建磁盘队列。
1. 如果队列未正确创建，请按Ctrl+C终止发送器，然后执行以下操作：

   1. 检查txtlogd.conf文件，并验证QueueFile和QueueSize参数是否已正确设置。
   1. 检查为其分配磁盘队列的设备是否运行正常，并有足够的空间来存放QueueSize参数中指定大小的文件。
   1. 进行任何必要的更正并重复此过程。

## 将收集器添加到Web服务器 {#section-a7fb6425956f4f518ae3a7db091b33d2}

对于Apache服务器，收集器是您加载到Web服务器进程中的动态共享对象。

要将收集器添加到Web服务器，必须按如下所述编辑httpd.conf文件，然后重新启动Web服务器。

如果传感器正在为服务器计算机上的多个Web服务器捕获数据，则必须对每个Web服务器执行以下过程。

1. 使用文本编辑器，打开 [!DNL httpd.conf] 文件，其事件由传感器捕获。
1. 在文件末尾添加以下行：

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >这些行区分大小写。 完全按上面显示的方式键入它们。

1. 重新启动Web服务器。 收集器随Web服务器一起加载，并将开始收集事件数据并将其写入磁盘队列。

## 测试传感器 {#section-83d9f60b39a6474f9c76bee3e19b2575}

启动发送器，并验证它是否可以成功连接到Insight Server并将事件数据发送到该服务器。

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
   * 的 [!DNL ServerAddress] 和 [!DNL ServerPort] 参数在 [!DNL txtlogd.conf].

   * 如果您指定 [!DNL ServerAddress] 请使用服务器名称，尝试改用其数字IP地址。 的值 [!DNL CertName] 参数与目标Insight Server的数字证书上显示的通用名称完全匹配。

## 将发送器添加到系统启动脚本 {#section-4e1ffa6e043941ab91411d91d596477a}

此信息可确保在重新启动Web服务器计算机时自动加载发送器。

将以下命令（用于启动发送器）添加到系统启动脚本。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

此命令将发送器作为守护程序启动。 发送器生成的操作和错误消息将写入系统日志。

>[!NOTE]
>
>某些Solaris用户可能会遇到“无法获取互斥锁”错误。 要使传感器在这些系统上正常工作，需要在文件/etc/system中添加或编辑以下行：
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>默认的Solaris设置为60。 根据使用传感器（每个实例使用三个信号）进行的测试，Adobe建议您使用1024作为设置。 此数字足够高，传感器可以与服务器上任何其他可能需要信号但不会影响性能的应用程序一起运行。 为支持这一建议，请注意，Adrian Cockcroft在其《太阳表演与调谐》（Prentice Hall，1994年10月）一书中指出：“数据库往往使用大量共享内存和信号量设置。 这不会影响性能；只要它们足够大，计划就会运行。”
