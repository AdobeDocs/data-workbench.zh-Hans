---
description: 有关为在RedHat Linux 7.x或更高版本、Sun Solaris SPARC 2.6或更高版本或Sun Solaris x86 9或更高版本上运行的J2EE实现安装和配置传感器的详细说明。
title: RedHat Linux 或 Sun Solaris 上的 JBoss、Tomcat 和 WebLogic 服务器
uuid: 7977fb9b-1737-4e1d-80c6-aabf968974dd
exl-id: 09c2f266-2ecc-42fc-98b6-b91f8883af0c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1823'
ht-degree: 2%

---

# RedHat Linux 或 Sun Solaris 上的 JBoss、Tomcat 和 WebLogic 服务器{#jboss-tomcat-and-weblogic-servers-on-redhat-linux-or-sun-solaris}

{{eol}}

有关为在RedHat Linux 7.x或更高版本、Sun Solaris SPARC 2.6或更高版本或Sun Solaris x86 9或更高版本上运行的J2EE实现安装和配置传感器的详细说明。

传感器的程序文件打包在从Adobe下载站点获取的安装文件中。 如果您还没有特定Web服务器的传感器安装文件，请先下载它(或从Adobe代表处获取它)，然后再开始执行以下步骤。

支持的J2EE实施包括：

* JBoss Server 3.2.x或更高版本
* Apache Jakarta Tomcat Server 4.1或更高版本
* WebLogic Server 6.x或更高版本

要安装和配置传感器，必须执行以下步骤：

## 安装程序文件 {#section-2f3e85083b4f4aa989a85997330e86ae}

提取和安装传感器程序文件的过程。

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
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> 收集器负载模块。 </td> 
   <td colname="col3"> <i> IBMHttpServer/模块</i> </td> 
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

## 将收集器添加到Web服务器 {#section-c5b83ae4ebce430aa764f951e849b333}

对于Apache服务器，收集器是您加载到Web服务器进程中的动态共享对象。

要将收集器添加到Web服务器，您必须编辑 [!DNL httpd.conf] 文件，然后重新启动Web服务器。

>[!NOTE]
>
>如果传感器正在为服务器计算机上的多个Web服务器捕获数据，则必须对每个Web服务器执行以下过程。

1. 使用文本编辑器，打开 [!DNL httpd.conf]文件，其事件由传感器捕获。
1. 添加以下内容 `<filter>` 和 `<filter-mapping>` 元素。 如果您未在/etc目录中安装txlogd.conf，则需要在 `<param-value>` 元素：

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>/etc/txlogd.conf</param-value> 
     <description></description> 
     </init-param> 
   </filter> 
   
   <filter-mapping> 
     <filter-name>VSCollectorFilter</filter-name> 
     <url-pattern>/*</url-pattern> 
   </filter-mapping> 
   ```

   >[!NOTE]
   >
   >这些行区分大小写。 完全按上面显示的方式键入它们。

1. 重新启动Web服务器进程（您不必重新启动整个服务器计算机，只需重新启动Web服务器进程）。 收集器随Web服务器一起加载，并开始收集事件数据并将其写入磁盘队列。

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

## 捕获其他数据 {#section-9483b663cbd0432daaca50c1089c7fca}

所有平台的传感器都可以收集HTTP请求和响应标头中可用的任何数据。

J2EE平台的传感器提供了一种收集其他平台上不可用数据的机制。 J2EE平台（J2EE收集器）的收集器位于应用程序层上，这样它便能够收集仅可用于应用程序且不应通过页面标记或标头公开的敏感数据。

>[!NOTE]
>
>虽然页面标记和标题修改可以隐藏数据，但对于那些检查页面源代码或使用浏览器插件工具查看标题的用户而言，仍然可以使用这些数据。

例如，J2EE收集器可用于捕获页面上显示的链接的每次点击成本(CPC)数据、页面上的敏感合作伙伴信息以及许多其他数据点。 J2EE环境使您能够轻松修改WEBAPP，以便使用我们的收集器类捕获此自定义数据。

当J2EE平台的传感器收到请求时，它将调用一个用于导入appendToLog函数的收集器类。 appendToLog函数将在appendToLog函数中指定的查询字符串参数附加到初始请求。 这会导致初始请求的URI包含与正在捕获的数据的名称和值对应的其他查询字符串名称 — 值对。 例如，当特定广告投放或点进链接的值为20美分时，CPC=20会附加到初始请求中。 Insight Server会将这些值处理到数据集中以进行分析。 此收集方法的另一个好处是它允许收集其他数据，而不会创建额外的日志条目，使用页面标记方法可能会创建这些日志条目。

有关处理的更多信息，请参阅《数据集配置指南》。

**从页面捕获其他数据**

1. 将以下代码添加到要从中捕获数据的.jsp页的顶部：

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. 使用收集器对象的appendToLog()方法将所需的名称 — 值对附加到所请求的.jsp页的查询字符串。 以下示例将“A=1”和“B=2”附加到所请求的.jsp页面的/index.jsp页面查询字符串中：

   ```
   <html> 
   <body> 
     <h1>Hello World</h1> 
     <% 
       VSCollector collector = new VSCollector(request, response); 
       collector.appendToLog("A", "1"); 
       collector.appendToLog("B", "2"); 
     %> 
   </body> 
   </html>
   ```

   生成的请求URI为/index.jsp?A=1&amp;B=2。

1. 对要从中捕获其他数据的每个.jsp页重复此过程。
