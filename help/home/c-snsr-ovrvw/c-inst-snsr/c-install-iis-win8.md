---
description: 安装并配置在Microsoft Windows Server 2008或更高版本下运行的Microsoft IIS 7.x或8.x传感器。
title: Windows Server 2008或更高版本上的Microsoft IIS
uuid: 7fd8da68-1553-4395-b13e-b08a6ee1948e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Windows Server 2008或更高版本上的Microsoft IIS{#microsoft-iis-on-windows-server-or-later}

安装并配置在Microsoft Windows Server 2008或更高版本下运行的Microsoft IIS 7.x或8.x传感器。

传感器的程序文件打包在您从Adobe下载站点获得的安装文件中。 如果您还没有特定Web服务器的传感器安装文件，请在开始以下步骤之前先下载它（或从Adobe代表处获得它）。

要安装和配置传感器，必须执行以下高级步骤：

1. [安装程序文件](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-cb51e5932a6d40c5b00758a7a51b7578)
1. [编辑传感器配置文件](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-1e1590a92222430e92066292512ae0df)
1. [启动发射器并创建磁盘队列](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-2b8dfd06996d4ab49998eeb99bd9f5f0)
1. [将收集器添加到Web服务器](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-088960c986cf449cb712152298b3518d)
1. [捕获其他数据](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-98db9625efdc4b60bfd76f7adf4af74d)

## 安装程序文件 {#section-cb51e5932a6d40c5b00758a7a51b7578}

在Windows IIS上运行传感器时，程序文件和磁盘队列文件必须位于同一目录中。

在安装程序文件之前，首先确定要维护磁盘队列的位置，因为必须在该位置安装程序文件。

请按照以下过程提取并安装传感器的程序文件。

1. 在Windows计算机上，创建一个用于安装传感器程序文件的目录。 请记住，您的磁盘队列也位于此目录中，因此，请确保您选择的设备有足够的空间容纳所需大小的队列。

   例如：C:\VisualSensor

1. 将安装文件的内容解压缩到刚刚创建的目录中。 在此步骤中，传感器会安装以下文件：

<table id="table_C9E8803E51D046FD8FCCA38F8DAC04D1"> 
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
   <td colname="col1"> qlog.dll </td> 
   <td colname="col2"> 收集器模块（ISAPI过滤器）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TestExperience.xls </td> 
   <td colname="col2"> <p>架构师可用于配置受控实验的Excel电子表格文件。 </p> <p>传感器不使用此文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 用于验证Insight Server在连接过程中显示的数字证书的证书。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> 发射机程序。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> 传感器配置文件。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>安装包中包含一个名为TestExperice.xls的电子表格文件。 此电子表格是架构师用来配置受控实验的工具。 传感器本身不使用此文件，因此不必在运行传感器的计算机上安装该文件（尽管您可以选择这样做）。 您可能希望将文件复制到架构师可以访问的位置，或根据需要从安装包中提取文件。 有关受控实验的详细信息，请参阅《Insight Controlled Experies Guide》（Insight控制实验指南）。

## 编辑传感器配置文件 {#section-1e1590a92222430e92066292512ae0df}

txlogd.conf文件包含传感器的配置参数。

您必须编辑文件以指定磁盘队列的大小、Insight Server的地址以及将附加到此传感器生成的数据的ID等。 配置文件包含必需参数和可选参数。

* **必需参数** ，是安装传感器时必须指定的设置。 如果没有这些设置，传感器将无法成功运行。
* **可选参数** ，是默认为预定义值（您可以修改）或启用可选功能的设置。

**编辑传感器配置文件**

1. 在文本 `<SensorDirectory>/txlogd.conf` 编辑器中打开文件，并设置所需的参数以及任何所需的可选参数。

   有关参数的 [!DNL txlogd.conf] 说明，请参 [阅Sensor Txlogd.conf文件参数](../../../home/c-snsr-ovrvw/sensor-txlogd-params/sensor-txlogd-params.md#concept-4bb629f058894b4abc65a31eb02eebed)。

1. 保存并关闭该文件。

## 启动发射器并创建磁盘队列 {#section-2b8dfd06996d4ab49998eeb99bd9f5f0}

配置文件后， [!DNL txlogd.conf]可以启动发射器程序，将其注册为Windows服务，并创建磁盘队列。

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

   >[!NOTE]
   >
   >此命令序列可能因您所使用的Windows版本而异。

   1. 在“事件查看器”窗口的左窗格中，选择“应用程序”日志。
   1. 在右侧窗格中，查找“源”列中带有“Adobe”的事件。
   1. 如果从“Adobe”中找到错误，请双击该错误以显示“活动属性”窗口。 此窗口提供有关错误的详细信息。

1. 检查完“应用程序”日志后，关闭“事件查看器”。
1. 验证发射器是否已在安装传感器程序文件的目录中创建了磁盘队列(Diskq2008.log)，以及它是您在txlogd.conf文件的QueueSize参数中指定的大小。

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

## 将收集器添加到Web服务器 {#section-088960c986cf449cb712152298b3518d}

对于IIS，收集器是一个ISAPI过滤器，您可以在IIS中将其添加到Web服务器。

1. 使用“开始”>“管 **理工具”>“Internet Information Services(IIS)管理器”打开IIS管理器**。
1. 展开“本 **地计算机** ”和“ **站点** ”节点。
1. 选择网站，在右窗格中双击“ **ISAPI过滤器”**。
1. 在“操 **作** ”窗格下，单 **击添加**。

1. 在“筛 **选器名称** ”字段中，输入筛选器的显示名称。 建议的过滤器名称为“传感器”。
1. 单 **击“浏览**”，选择qlog.dll文件（位于传感器安装目录中），然后单击“确 **定”**。

1. 单击 **确定** ，以添加过滤器。

   添加过滤器后，收集器会立即运行并准备好收集数据。

如果流量流向收集器后不显示绿色箭头，请完成以下步骤：

1. 单击“开始”>“管理工具”>“活动查看器”，以检查活动查看器是否有错误。

   >[!NOTE]
   >
   >此命令序列可能因您所使用的Windows版本而异。

1. 在“事件查看器”窗口的左窗格中，选择“应用程 **序日志** ”。
1. 在右侧窗格中，查找“源”列中带有“Adobe”的 **事件** 。
1. 如果您发现错误，请双击该错误以显示“事件属 **性”窗口** 。

## 捕获其他数据 {#section-98db9625efdc4b60bfd76f7adf4af74d}

网页通常使用ASP(Active Server Pages)编程语言进行结构化。

ASP是一种在IIS中运行的Microsoft技术。 当浏览器请求ASP文件时，IIS会将该请求传递给ASP引擎。 ASP引擎逐行读取ASP文件，并执行文件中的脚本。 最后，ASP文件作为纯HTML返回到浏览器。 ASP提供RESPONSE或REQUEST对象，除了其他实用程序外，还允许对用户查询或从HTML表单提交的数据进行响应或请求。

在某些情况下，您可能不希望将输入到表单中的值附加到用户浏览器地址栏中显示的URL或HTML代码本身中可查看的URL。 简单的服务器端ASP脚本允许您将表单字段名称及其各自的值附加到日志文件中，而无需在用户的浏览器中提供它们或将它们嵌入到HTML文件中。 要捕获在网站中特定表单中输入的实际表单值，必须添加几行代码才能将表单值附加到日志请求中。

在表单的处理页面中，包括以下代码，以将输入的表单值附加到请求数据（除了将提交的表单值写入外部数据库或其他位置之外）:

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

此过程将在“表单处理”页的请求数据后附加定义的表单值。 在日志数据中，附加的值将作为“表单处理”页面的查询字符串可用，如下图所示。 例如，v_1、v_2、v_3和v_4现在将是查询字符串，其中包含输入到相应表单字段中的数据。 您可以对要捕获的任何其他表单字段和值复制上一个示例中描述的语法：

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

如果您希望捕获每个表单字段和值并将其用于分析，则可以使用以下语法：

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues);
```

此示例将采用HTML中存在的所有表单字段及其各自的值，并将它们作为查询字符串附加到“表单处理”页面的日志条目中。 请注意，这将包括表单中存在的所有隐藏字段。

日志数据将增强，如下表所述：

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_1 | 与NAME查询字符串关联的值 | v_1=John Smith |
| v_2 | 与CITY查询字符串关联的值 | v_2=洛杉矶 |
| v_3 | 与STATE查询字符串关联的值 | v_3=加利福尼亚 |
| v_4 | 与ZIP查询字符串关联的值 | v_4=90210 |

<!-- <a id="section_55C623AC973246DC9EBECD48DA1EE0F7"></a> -->

