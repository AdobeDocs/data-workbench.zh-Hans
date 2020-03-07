---
description: 有关安装和配置Sensor for JBoss Server 4.0.5或更高版本的详细说明，这些传感器在Microsoft Windows Server 2000或更高版本下运行。
title: Windows Server 2000或更高版本上的JBoss Server
uuid: b0501749-9479-484b-8876-fe3001825f8d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Windows Server 2000或更高版本上的JBoss Server{#jboss-server-on-windows-server-or-later}

有关安装和配置Sensor for JBoss Server 4.0.5或更高版本的详细说明，这些传感器在Microsoft Windows Server 2000或更高版本下运行。

传感器的程序文件打包在您从Adobe下载站点获得的安装文件中。 如果您还没有特定Web服务器的传感器安装文件，请在开始以下步骤之前先下载它（或从Adobe代表处获得它）。

支持的J2EE实现包括：

* 在Microsoft Windows Server 2000或更高版本上运行的JBoss Server 4.0.5或更高版本。

要安装和配置传感器，必须执行以下步骤：

## 安装程序文件 {#section-2f3e85083b4f4aa989a85997330e86ae}

解压并安装传感器程序文件的过程。

1. 在JBoss服务器上，创建一个用于安装传感器程序文件的目录。 请记住，您的磁盘队列位于此目录中，因此请确保您选择的设备有足够的空间容纳所需大小的队列。

   ```
   C:\VisualSensor
   ```

1. 将安装文件的内容解压缩到刚刚创建的目录中。 在此步骤中，传感器会安装以下文件：

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
>安装包中包含一个名为的电子表格文件 [!DNL TestExperiment.xls]。 此电子表格是架构师用来配置受控实验的工具。 传感器本身不使用此文件，因此不必在运行传感器的计算机上安装该文件（尽管您可以选择这样做）。 您可能希望将文件复制到架构师可以访问的位置，或根据需要从安装包中提取文件。 有关受控实验的详细信息，请参阅《Insight Controlled Experies Guide》（Insight控制实验指南）。

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

1. 从Windows的“开始”菜单中，选择“附件”>“命令提示符”。
1. 在命令提示符窗口中，导航到安装了传感器的目录并执行以下命令：

   ```
   txlog /regserver
   ```

   此命令启动发射器、创建磁盘队列并将传感器注册为Windows服务。

1. 要确认发射器是否正确运行，请单击“开始”>“控制面板”>“管理工具”>“服务”。

   >[!NOTE]
   >
   >此命令序列可能因您所使用的Windows版本而异。

   1. 在服务列表中，找到传感器条目并确认其状态为“Started（启动）” ，其启动类型为“Automatic（自动）”。
   1. 关闭“服务”控制面板。

1. 要检查发射器在启动过程中是否遇到任何错误，请单击“开始”>“控制面板”>“管理工具”>“事件查看器”以打开事件查看器。

   1. 在“事件查看器”窗口的左窗格中，选择“应用程序”日志。
   1. 在右侧窗格中，查找“源”列中带有“Adobe”的事件。
   1. 如果从“Adobe”中找到错误，请双击该错误以显示“活动属性”窗口。 此窗口提供有关错误的详细信息。

1. 检查完“应用程序”日志后，关闭“事件查看器”。
1. 验证发射器是否已在安装传感器程序文件的目录中创建了磁盘队列(Diskq2000.log)，以及它是您在txlogd.conf文件的QueueSize参数中指定的大小。

   如果队列未正确创建：

   1. 检查txtlogd.conf文件并验证QueueSize参数设置是否正确。
   1. 检查您安装传感器的设备是否有足够的可用空间来容纳QueueSize参数中指定大小的文件。
   1. 使用Windows中的“服务”控制面板，停止发射器。
   1. 删除队列文件。
   1. 将传感器重新注册为Windows服务：从Windows的“开始”菜单中，选择“附件”>“命令提示符”。 在命令提示符窗口中，导航到安装了传感器的目录并执行以下命令：

      ```
      txlog /regserver
      ```

该发射器设计为连续运行。 如果重新启动计算机，则发射器会自动重新启动。 如果需要手动启动和停止发射器，可以使用Windows中的“服务”控制面板执行此操作。

## 将收集器添加到Web服务器 {#section-c5b83ae4ebce430aa764f951e849b333}

对于JBoss服务器，收集器在servlet容器中作为过滤器运行。

要将收集器添加到Web服务器，必须按照下面所述编 [!DNL web.xml] 辑文件并重新启动Web应用程序。

1. 使用文本编辑器，打开Sensor [!DNL web.xml] 捕获其事件的Web服务器的文件。
1. 将以下元素 `<filter>` 和元 `<filter-mapping>` 素添加到描述符文件。 如果未在/etc目录中安装txlogd.conf，则需要在元素中输入此文件的正确路 `<param-value>` 径：

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

1. 重新启动Web服务器进程（您不必重新启动整个服务器计算机，只需重新启动Web服务器进程）。 收集器加载了Web服务器，开始收集事件数据并将其写入磁盘队列。

## 修改启动脚本 {#section-0dae181ef8884f10a57f6cfda8500969}

在修改启动脚本之前，请确保在Windows环境中定义JAVA_HOME变量。

在文 [!DNL run.bat] 件(例如C:\jboss-4.0.5.GA\bin\run.bat)中，在文件末尾附近添加以下行，就在JBoss服务器启动命令之前的“echo”行之前：

```
set JBOSS_CLASSPATH=%JBOSS_CLASSPATH%;C:\jboss-4.0.5.GA\server\default\lib\javax.servlet.jar;C:\VisualSciences\J2EECollector.jar 
set JAVA_OPTS=%JAVA_OPTS% -Djava.library.path=C:\VisualSciences
```

## 捕获其他数据 {#section-9483b663cbd0432daaca50c1089c7fca}

您可以使用appendToLog()功能从基于J2EE的Web应用程序捕获其他测量数据。

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

