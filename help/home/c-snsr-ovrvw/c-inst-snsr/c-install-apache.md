---
description: 关于如何在Linux、Sun Solaris或FreeBSD上安装和配置Apache Server 2.0.40、2.0.42或更高版本、Apache Server 2.2或Apache Server 2.4的说明。
title: Linux、Solaris或FreeBSD上的Apache Server 2.0.40、2.0.42或更高版本以及Apache Server 2.2或2.4
uuid: 3703e2c1-5b8d-4def-b146-49e59d78a669
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Linux、Solaris或FreeBSD上的Apache Server 2.0.40、2.0.42或更高版本以及Apache Server 2.2或2.4{#apache-server-or-later-and-apache-server-or-on-linux-solaris-or-freebsd}

关于如何在Linux、Sun Solaris或FreeBSD上安装和配置Apache Server 2.0.40、2.0.42或更高版本、Apache Server 2.2或Apache Server 2.4的说明。

传感器的程序文件打包在您从Adobe下载站点获得的安装文件中。 如果您还没有特定Web服务器的传感器安装文件，请在开始以下步骤之前先下载它（或从Adobe代表处获得它）。

要安装和配置传感器，必须执行以下高级步骤：

支持以下Apache服务器：

* 在RedHat Linux 7.x或更高版本或Sun Solaris SPARC 2.6或更高版本下运行的Apache Server 2.0.40。
* Linux、Sun Solaris或FreeBSD上的Apache Server 2.0.40、2.0.42或更高版本、Apache Server 2.2或Apache Server 2.4
* 在RedHat Linux 7.x或更高版本、Sun Solaris SPARC 2.6或更高版本、SUSE Linux 9.x或更高版本或FreeBSD 5.3下运行的Apache Server 2.0.42或更高版本。
* 运行于64位版本的RedHat Linux ES 4和ES 5下的Apache Server 2.0.42或更高版本。
* 在RedHat Linux 7.x或更高版本或Sun Solaris SPARC 2.6或更高版本下运行的Apache Server 2.2。
* 在RedHat Linux 7.x或更高版本、Sun Solaris x86_64或FreeBSD下运行的Apache Server 2.4

>[!NOTE]
>
>尽管在运行Apache Server 2.0.40、2.0.42或更高版本（32位和64位）或2.2的Web服务器上安装传感器的说明相同（以下步骤中说明的除外），但各个版本的安装文件不同。 在安装传感器之前，请确保您已收到正在运行的Apache Server和操作系统版本的正确安装文件。

## 安装程序文件 {#section-2f3e85083b4f4aa989a85997330e86ae}

解压并安装传感器程序文件的过程。

1. 以根用户或具有根权限的用户身份登录。
1. 使用以下命令解压缩并解压缩安装文件：

   * 在Linux上：

      ```
      tar -zxf installationFilename
      ```

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

   * 在Solaris上：

1. 将解压缩的程序文件复制到下表中标识的目录：

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File（文件） </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 目标目录 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> 收集器负载模块。 </td> 
   <td colname="col3"> <i> IBMHttpServer/模块</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> 发射机程序。 </td> 
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
>安装包中包含一个名为TestExperice.xls的电子表格文件。 此电子表格是架构师用来配置受控实验的工具。 传感器本身不使用此文件，因此不必在运行传感器的计算机上安装该文件（尽管您可以选择这样做）。 您可能希望将文件复制到架构师可以访问的位置，或根据需要从安装包中提取文件。 有关受控实验的详细信息，请参阅《Insight Controlled Experies Guide》（Insight控制实验指南）。

**对程序文件的权限**

>[!NOTE]
>
>对程序文件的权限不正确会导致安装传感器时遇到的大多数问题。 请确保您设置的权限完全符合本条所述的要求。
>
>默认情况下，tar文件中的程序文件具有以下权限。 根据系统的配置方式，在解压文件时，这些设置可能会被更改（未遮住）。 要将权限重置为建议的默认设置，请使用下面的chmod命令。 检查您已安装文件的目录是否至少允许此级别的访问。

| File（文件） | 默认权限 | chmod命令 |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-r— r— | chmod 664 |
| trust_ca_cert.pem | rw-r— r— | chmod 664 |

## 在Sametime Server上启用登录 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

允许您登录到Sametime Server的步骤。

1. 使用Lotus Domino Administrator客户端连接到运行Sametime的Lotus Domino服务器。
1. 在Lotus Domino Administrator中，单击“文件”选项卡，然后双击“Sametime Configuration - stconfig.nsf”以打开“Sametime配置”文件。
1. 在“同时配置”文件中，打开“社区服务”表单，双击表单上的任意位置以进入编辑模式。
1. 将“聊天记录标记”设置为“strict”，将“捕获服务类型”设置为“0x1000”。
1. 保存并关闭“社区服务”表单，然后关闭“同时配置”文件。
1. 重新启动Sametime服务器。

## 编辑传感器配置文件 {#section-de0eb4a646394b61abb6cd5a2b706de0}

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

对于IBM HTTP服务器，收集器是一个动态共享对象，加载到Web服务器进程中。

要将收集器添加到Web服务器，必须按照下面所述编辑httpd.conf文件，然后重新启动Web服务器。

如果传感器正在为服务器计算机上的多台Web服务器捕获数据，则必须对每台Web服务器执行以下过程。

1. 使用文本编辑器，打开Sensor捕获其事件的Web服务器的httpd.conf文件。
1. 在文件末尾添加以下两行：

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >这些行区分大小写。 完全按上面显示的方式键入它们。

1. 重新启动Web服务器进程（您不必重新启动整个服务器计算机，只需重新启动Web服务器进程）。 收集器加载了Web服务器，开始收集事件数据并将其写入磁盘队列。

## 测试传感器 {#section-0dae181ef8884f10a57f6cfda8500969}

验证收集器是否正在收集事件数据，以及发射器是否正在将其传输到目标Insight Server。

>[!NOTE]
>
>要验证发射器是否可以将事件数据成功发送到Insight Server，请确保目标Insight Server已安装并正在运行，然后开始以下测试。

1. 如果发射器尚未运行，请使用以下命令重新启动它：

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. 打开浏览器（在任何计算机上），并从运行传感器的Web服务器请求页面（请务必选择传感器监视的页面）。
1. 发出请求后，检查发射器的控制台中是否有消息，指明它正在向目标Insight Server发送事件数据。
1. 如果传感器未成功传输数据，请验证：

   * 目标Insight Server正在运行。
   * 在txtlogd.conf中正确设置ServerAddress和ServerPort参数。 如果您使用服务器名指定了ServerAddress，请尝试改用其数字IP地址。
   * CertName参数的值与目标Insight Server的数字证书上显示的公用名称完全匹配。

## 将发射器添加到系统启动脚本 {#section-19a38f27c9f44adf88f8910f5ed483a3}

有关将发射器自动加载到系统启动脚本的信息。

要确保在重新启动Web服务器计算机时发射器自动加载，请将以下命令（该命令将启动发射器）添加到系统启动脚本中：

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

此命令将发射器作为守护程序启动。 发射机生成的操作和错误消息将写入syslog。
