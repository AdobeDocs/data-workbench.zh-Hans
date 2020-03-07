---
description: 有关如何在IBM AIX 5.1或更高版本上安装和配置IBM HTTP服务器的说明，这些服务器在Microsoft Windows Server 2000或更高版本下运行。
title: AIX 5.1或更高版本上的IBM HTTP Server
uuid: d4a37ab2-514a-4afb-905b-420159c4ef0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# AIX 5.1或更高版本上的IBM HTTP Server{#ibm-http-server-on-aix-or-later}

有关如何在IBM AIX 5.1或更高版本上安装和配置IBM HTTP服务器的说明，这些服务器在Microsoft Windows Server 2000或更高版本下运行。

传感器的程序文件打包在您从Adobe下载站点获得的安装文件中。 如果您还没有特定Web服务器的传感器安装文件，请在开始以下步骤之前先下载它（或从Adobe代表处获得它）。

要安装和配置传感器，必须执行以下高级步骤：

## 安装程序文件 {#section-2f3e85083b4f4aa989a85997330e86ae}

在IBM AIX服务器上，创建一个用于安装传感器程序文件的目录。 请记住，您的磁盘队列也位于此目录中，因此，请确保您选择的设备有足够的空间容纳所需大小的队列。

1. 以根用户或具有根权限的用户身份登录。
1. 使用以下命令解压缩并解压缩安装文件：

   ```
   tar -zxf installationFilename
   ```

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

<table id="table_F4A46DBDE0874133B616235C32B6D9F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File（文件） </th> 
   <th colname="col2" class="entry"> 默认权限 </th> 
   <th colname="col3" class="entry"> chmod命令 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> rwx —x —x </td> 
   <td colname="col3"> <p>chmod 711 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> rw-rw-r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> rwx —x —x </td> 
   <td colname="col3"> chmod 711 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> rw-rw-r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> rw-rw-r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
 </tbody> 
</table>

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

## 将收集器添加到Web应用程序 {#section-c5b83ae4ebce430aa764f951e849b333}

对于WebSphere服务器，收集器在servlet容器中作为过滤器运行。

要将收集器添加到Web应用程序，请打开Sensor捕获其事件的Web服务器的web.xml文件。

如果传感器正在为服务器计算机上的多台Web服务器捕获数据，则必须对每台Web服务器执行以下过程。

1. 使用文本编辑器，打开Sensor捕获其事件的Web服务器的httpd.conf文件。
1. 将以下元素 `<filter>` 和元 `<filter-mapping>` 素添加到描述符文件。 如果未在/etc目录中安装txlogd.conf，则需要在元素中输入此文件的正确路 `<param-value>` 径。

   ```
   <filter> 
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>C:/VisualSensor/txlogd.conf</param-value> 
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

1. 重新启动Web应用程序。 收集器随应用程序一起加载，并将开始收集事件数据并将其写入磁盘队列。

## 声明收集器和共享对象文件的位置 {#section-b9c298fa645f4670b2503647d967846f}

编辑Websphere启动脚本以声明J2EECollector.jar和libvisual_sciences.so文件的位置。

1. 打开Websphere /bin目录中的setupCmdLine.sh文件。
1. 在定义$WAS_CLASSPATH变量的行之后，添加以下行：

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. 在定义$WAS_LIBPATH变量的大小写块之后，添加以下行：

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. 保存setupCmdLine.sh文件。

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

## 捕获其他数据 {#section-bb1c2bccba9b4bc0b52abdbb4f9d42d7}

所有平台的传感器都可以收集HTTP请求和响应标头中可用的任何数据。

J2EE平台的传感器提供了收集其他平台上不可用的数据的机制。 J2EE平台（J2EE收集器）的收集器位于应用程序层上，这使其能够收集仅对应用程序可用的敏感数据，并且不应通过页面标记或标题来公开这些数据。

>[!NOTE]
>
>虽然页面标记和标题修改可以隐藏数据，但那些使用浏览器插件工具检查页面源代码或查看标题的用户仍可使用该功能。

例如，J2EE收集器可用于捕获页面上显示的链接的每次点击成本(CPC)数据、页面上的敏感合作伙伴信息以及许多其他数据点。 J2EE环境使您能够轻松地修改WEBAPP，以使用我们的收集器类捕获此自定义数据。

当J2EE平台的传感器收到请求时，它调用一个导入appendToLog函数的收集器类。 appendToLog函数会将在appendToLog函数中指定的查询字符串参数附加到初始请求中。 这会导致初始请求的URI中包含与所捕获数据的名称和值相对应的附加查询字符串名称——值对。 例如，当特定广告投放或点进链接的值为20美分时，CPC=20将附加到初始请求中。 Insight Server将这些值处理到数据集中以进行分析。 此收集方法的另一个好处是它允许收集其他数据，而不创建额外的日志条目，这可能是使用页面标记方法创建的。

有关处理的详细信息，请参阅《数据集配置指南》。

要从页面捕获其他数据，请执行以下操作：

1. 将以下代码添加到要从中捕获数据的。jsp页的顶部：

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. 使用收集器对象的appendToLog()方法将所需的名称——值对追加到所请求的。jsp页的查询字符串中。 以下示例将“A=1”和“B=2”附加到/index.jsp页面所请求的。jsp页面的查询字符串中：

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

1. 对要从中捕获其他数据的每个。jsp页重复此过程。

