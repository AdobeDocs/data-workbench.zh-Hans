---
description: 有关在RedHat Linux 7.x或更高版本、SUSE Linux 9.x或更高版本、Sun Solaris SPARC 2.6或更高版本、Sun Solaris x86 9或更高版本、FreeBSD 4或更高版本或Mac OS X PowerPC上安装和配置传感器的详细说明。
title: Linux、Sun Solaris、FreeBSD 或 Mac OS X 上的 Apache Server 1.3.x
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---


# Linux、Sun Solaris、FreeBSD 或 Mac OS X 上的 Apache Server 1.3.x{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

有关在RedHat Linux 7.x或更高版本、SUSE Linux 9.x或更高版本、Sun Solaris SPARC 2.6或更高版本、Sun Solaris x86 9或更高版本、FreeBSD 4或更高版本或Mac OS X PowerPC上安装和配置传感器的详细说明。

传感器的项目文件打包在从Adobe下载站点获得的安装文件中。 如果您还没有特定Web服务器的传感器安装文件，请先下载它(或从Adobe代表处获取它)，然后开始执行以下步骤。

要安装和配置传感器，必须执行以下高级步骤：

## 安装项目文件 {#section-aae323e252394212bf4096d65fdd280c}

将传感器项目文件解压并安装到服务器计算机的说明。

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

1. 将解压缩的项目文件复制到下表中标识的目录：

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
   <td colname="col2"> 收集器负载模块 </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> 发射器项目 </td> 
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
>安装包中包含一个名为TestExperice.xls的电子表格文件。 此电子表格是架构师用来配置受控实验的工具。 传感器本身不使用此文件，因此不必在运行传感器的计算机上安装该文件（尽管您可以选择安装）。 您可能希望将文件复制到架构师可以访问它的位置，或根据需要从安装包中提取文件。 有关受控实验的更多信息，请参阅《Insight Controlled Experies Guide》（Insight控制实验指南）。

**对项目文件的权限**

对项目文件的权限不正确会导致安装传感器时遇到的大多数问题。

请确保您设置的权限完全符合本条所述。

默认情况下，tar文件中的项目文件具有以下权限。 根据系统的配置方式，在解压文件时，这些设置可能会被更改（未被遮住）。 要将权限重置为推荐的默认设置，请使用下面的chmod命令。 检查已安装文件的目录是否允许至少此级别的访问。

| 文件 | 默认权限 | chmod命令 |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-rw-r— | chmod 664 |
| trust_ca_cert.pem | rw-rw-r— | chmod 664 |

## Edit the Sensor configuration file {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

文 [!DNL txlogd.conf] 件包含传感器的配置参数。

您必须编辑文件，以指定磁盘队列的大小、Insight Server的地址以及将附加到此传感器生成的数据的ID。

配置文件包含必需的参数和可选参数。

* 必需参数是安装传感器时必须指定的设置。 如果没有这些设置，传感器无法成功运行。
* 可选参数是默认为预定义值（您可以修改）或启用可选功能的设置。

编辑传感器配置文件

1. 在文本编辑器中打开/etc/txlogd.conf文件，并设置所需的参数以及任何所需的可选参数。
1. 保存并关闭该文件。

## 开始发射器并创建磁盘队列 {#section-a453d912ec3d47aa8e40ccacf527119d}

配置txlogd.conf文件后创建磁盘队列的说明。

1. 如果磁盘队列所在的目录尚不存在，请创建它。 确保目录为收集器模块和发射器项目提供对文件的读／写访问。
1. 在安装传感器的计算机上，执行以下命令以开始发射器：

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * 此命令中的“i”选项在交互模式下开始发射器。 此模式在屏幕上显示发射器消息，还允许您使用键盘命令与发射器进行交互。
   * “c”选项指示发射器创建磁盘队列。
   * “f”选项指定配置文件的位置。

1. 验证发射器是否已在QueueFile参数中指定的位置和QueueSize参数中指定的大小中创建了磁盘队列。
1. 如果队列创建不正确，请键入Ctrl+C以终止发射器，然后执行以下操作：

   1. 检查txtlogd.conf文件并验证QueueFile和QueueSize参数设置正确。
   1. 检查为其分配磁盘队列的设备是否可操作，并有足够的可用空间来保存QueueSize参数中指定大小的文件。
   1. 请进行必要的更正，并重复此过程。

## 将收集器添加到Web服务器 {#section-a7fb6425956f4f518ae3a7db091b33d2}

对于Apache服务器，收集器是加载到Web服务器进程中的动态共享对象。

要将收集器添加到Web服务器，必须按如下所述编辑httpd.conf文件并重新启动Web服务器。

如果传感器正在为服务器计算机上的多个Web服务器捕获数据，则必须对每个Web服务器执行以下过程。

1. 使用文本编辑器打开Web [!DNL httpd.conf] 服务器的文件，事件传感器会捕获该文件。
1. 在文件末尾添加以下行：

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >这些行区分大小写。 完全按上面显示的方式键入它们。

1. 重新启动Web服务器。 收集器加载了Web服务器，并将开始收集事件数据并将其写入磁盘队列。

## 测试传感器 {#section-83d9f60b39a6474f9c76bee3e19b2575}

开始发射器，并验证它是否可以成功连接到Insight Server，并向其发送事件数据。

>[!NOTE]
>
>要验证发射器是否可以将事件数据成功发送到Insight Server，请确保目标Insight Server已安装并正在运行，然后开始以下测试。

1. 如果发射器尚未运行，请使用以下命令重新启动它：

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. 打开浏览器（在任何计算机上），并从运行传感器的Web服务器请求页面（确保选择传感器正在监视的页面）。
1. 发出请求后，检查发射器的控制台中是否有消息，指明它正在向事件Insight Server发送目标数据。
1. 如果传感器未成功传输数据，请验证：

   * 目标Insight Server正在运行。
   * 和 [!DNL ServerAddress] 参 [!DNL ServerPort] 数在中设置正确 [!DNL txtlogd.conf]。

   * 如果使用服 [!DNL ServerAddress] 务器名称指定，请尝试改用其数字IP地址。 该参数的值 [!DNL CertName] 与目标Insight Server的数字证书上显示的公用名称完全匹配。

## 将发射器添加到系统启动脚本 {#section-4e1ffa6e043941ab91411d91d596477a}

确保在重新启动Web服务器计算机时发射器自动加载的信息。

将以下命令（用于启动发射器）添加到系统启动脚本。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

此命令将发射器开始为守护程序。 发射器生成的操作和错误消息将写入系统日志。

>[!NOTE]
>
>某些Solaris用户可能遇到“无法获取互斥锁”错误。 要使传感器在这些系统上正常工作，需要在文件/etc/system中添加以下代码行或对其进行编辑：
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>默认的Solaris设置为60。 根据使用传感器进行的测试，Adobe建议您使用1024作为设置。 此数量足够高，传感器可以与服务器上任何其他可能需要信号但不会影响性能的应用程序一起工作。 要支持这一建议，请注意，Adrian Coccroft在其书《Sun Performance and Tuning》（Prentice Hall,1994年10月）中指出：“数据库往往使用大量共享内存和信号量设置。 这不会影响性能；只要它们足够大，项目就会跑。”

