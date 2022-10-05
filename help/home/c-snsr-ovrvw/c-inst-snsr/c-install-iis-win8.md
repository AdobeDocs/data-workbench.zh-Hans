---
description: 安装并配置在Microsoft Windows Server 2008或更高版本下运行的Microsoft IIS 7.x或8.x传感器。
title: Windows Server 2008 或更高版本上的 Microsoft IIS
uuid: 7fd8da68-1553-4395-b13e-b08a6ee1948e
exl-id: cc909daa-60c0-4188-8e90-035c41bf3105
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 1%

---

# Windows Server 2008 或更高版本上的 Microsoft IIS{#microsoft-iis-on-windows-server-or-later}

{{eol}}

安装并配置在Microsoft Windows Server 2008或更高版本下运行的Microsoft IIS 7.x或8.x传感器。

传感器的程序文件打包在从Adobe下载站点获取的安装文件中。 如果您还没有特定Web服务器的传感器安装文件，请先下载它(或从Adobe代表处获取它)，然后再开始执行以下步骤。

要安装和配置传感器，必须执行以下高级步骤：

1. [安装程序文件](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-cb51e5932a6d40c5b00758a7a51b7578)
1. [编辑传感器配置文件](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-1e1590a92222430e92066292512ae0df)
1. [启动发送器并创建磁盘队列](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-2b8dfd06996d4ab49998eeb99bd9f5f0)
1. [将收集器添加到Web服务器](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-088960c986cf449cb712152298b3518d)
1. [捕获其他数据](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-98db9625efdc4b60bfd76f7adf4af74d)

## 安装程序文件 {#section-cb51e5932a6d40c5b00758a7a51b7578}

在Windows IIS上运行传感器时，程序文件和磁盘队列文件必须位于同一目录中。

在安装程序文件之前，首先确定要在何处维护磁盘队列，因为必须在何处安装程序文件。

请按照以下步骤为传感器提取并安装程序文件。

1. 在Windows计算机上，创建一个目录以在其中安装传感器程序文件。 请记住，磁盘队列也位于此目录中，因此请确保您选择的设备有足够的空间容纳所需大小的队列。

   例如：C:\VisualSensor

1. 将安装文件的内容解压缩到刚刚创建的目录中。 在此步骤中，传感器安装以下文件：

<table id="table_C9E8803E51D046FD8FCCA38F8DAC04D1">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 文件 </th>
   <th colname="col2" class="entry"> 描述 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> EventMessages.dll </td>
   <td colname="col2"> 事件查看器消息。 </td>
  </tr>
  <tr>
   <td colname="col1"> qlog.dll </td>
   <td colname="col2"> 收集器模块（ISAPI过滤器）。 </td>
  </tr>
  <tr>
   <td colname="col1"> TestExperiment.xls </td>
   <td colname="col2"> <p>一种Excel电子表格文件，架构师可以使用该文件来配置受控实验。 </p> <p>传感器不使用此文件。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> trust_ca_cert.pem </td>
   <td colname="col2"> 用于验证Insight Server在连接过程中显示的数字证书的证书。 </td>
  </tr>
  <tr>
   <td colname="col1"> TXLog.exe </td>
   <td colname="col2"> 发送程序。 </td>
  </tr>
  <tr>
   <td colname="col1"> txlogd.conf </td>
   <td colname="col2"> 传感器配置文件。 </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>安装包包含一个名为TestExperience.xls的电子表格文件。 此电子表格是一种用于架构师配置受控实验的工具。 传感器本身不使用此文件，因此不必在运行传感器的计算机上安装该文件（尽管您可以选择这样做）。 您可能希望将文件复制到架构师可以访问的位置，或者根据需要从安装包中提取文件。 有关对照实验的更多信息，请参阅《Insight对照实验指南》。

## 编辑传感器配置文件 {#section-1e1590a92222430e92066292512ae0df}

txlogd.conf文件包含传感器的配置参数。

您必须编辑文件以指定磁盘队列的大小、Insight Server的地址以及将附加到此传感器生成数据的ID等内容。 配置文件包含必需的参数和可选参数。

* **必需的参数** 是安装传感器时必须指定的设置。 如果没有这些设置，传感器将无法成功运行。
* **可选参数** 是默认设置，用于预定义值（您可以对其进行修改）或启用可选功能。

**编辑传感器配置文件**

1. 打开 `<SensorDirectory>/txlogd.conf` 文件，并设置所需的参数以及任何所需的可选参数。

   有关的描述 [!DNL txlogd.conf] 参数，请参阅 [传感器Txlogd.conf文件参数](../../../home/c-snsr-ovrvw/sensor-txlogd-params/sensor-txlogd-params.md#concept-4bb629f058894b4abc65a31eb02eebed).

1. 保存并关闭该文件。

## 启动发送器并创建磁盘队列 {#section-2b8dfd06996d4ab49998eeb99bd9f5f0}

配置 [!DNL txlogd.conf]文件中，可以启动发送程序，将其注册为Windows服务，并创建磁盘队列。

1. 从Windows的“开始”菜单中，选择“附件”>“命令提示符”。
1. 在命令提示符窗口中，导航到安装传感器的目录并执行以下命令：

   ```
   txlog /regserver
   ```

   此命令启动发送器，创建磁盘队列，并将传感器注册为Windows服务。

1. 要确认发送器运行正确，请单击开始>控制面板>管理工具>服务。

   >[!NOTE]
   >
   >此命令序列可能因您使用的Windows版本而异。

   1. 在服务列表中，找到传感器的条目，并确认其状态为“已启动”且其启动类型为“自动”。
   1. 关闭“服务”控制面板。

1. 要检查发送器在启动过程中是否遇到任何错误，请单击开始>控制面板>管理工具>事件查看器以打开事件查看器。

   >[!NOTE]
   >
   >此命令序列可能因您使用的Windows版本而异。

   1. 在事件查看器窗口的左窗格中，选择应用程序日志。
   1. 在右侧窗格中，查找“源”列中包含“Adobe”的事件。
   1. 如果从“Adobe”中找到错误，请双击该错误以显示“事件属性”窗口。 此窗口提供有关错误的详细信息。

1. 检查完应用程序日志后，关闭事件查看器。
1. 确认发送器已在安装传感器程序文件的目录中创建了磁盘队列(Diskq2008.log)，并且该磁盘队列的大小是您在txlogd.conf文件的QueueSize参数中指定的大小。

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

## 将收集器添加到Web服务器 {#section-088960c986cf449cb712152298b3518d}

对于IIS，收集器是IIS中添加到Web服务器的ISAPI过滤器。

1. 使用打开IIS管理器 **开始>管理工具> Internet信息服务(IIS)管理器**.
1. 展开 **本地计算机** 和 **站点** 节点。
1. 选择网站，然后在右窗格中双击 **ISAPI过滤器**.
1. 在 **操作** 窗格，单击 **添加**.

1. 在 **过滤器名称** 字段，输入过滤器的显示名称。 建议的过滤器名称为“传感器”。
1. 单击 **浏览**，选择qlog.dll文件（位于安装传感器的目录中），然后单击 **确定**.

1. 单击 **确定** 添加过滤器。

   添加过滤器后，收集器可立即运行并准备收集数据。

如果流量流向收集器后未显示绿色箭头，请完成以下步骤：

1. 单击开始>管理工具>事件查看器，以检查事件查看器是否存在错误。

   >[!NOTE]
   >
   >此命令序列可能因您使用的Windows版本而异。

1. 在事件查看器窗口的左窗格中，选择 **应用程序** 日志。
1. 在右侧窗格中，查找在 **来源** 列。
1. 如果发现错误，请双击该错误以显示 **事件属性** 窗口。

## 捕获其他数据 {#section-98db9625efdc4b60bfd76f7adf4af74d}

网页通常使用ASP(Active Server Pages)编程语言来构建。

ASP是一种在IIS中运行的Microsoft技术。 当浏览器请求ASP文件时，IIS会将该请求传递到ASP引擎。 ASP引擎逐行读取ASP文件，并执行文件中的脚本。 最后，将ASP文件作为纯HTML返回到浏览器。 ASP提供RESPOND或REQUEST对象，除了其他实用程序外，这些对象还允许用户查询或从HTML表单提交数据的响应或请求。

在某些情况下，您可能不希望将输入到表单中的值附加到显示在用户浏览器地址栏内或在HTML代码中可查看的URL之后。 简单的服务器端ASP脚本允许您将表单字段名称及其各自的值附加到日志文件中，而无需在用户的浏览器中提供或将它们嵌入到HTML文件中。 要捕获在您网站的特定表单中输入的实际表单值，必须添加几行代码以将表单值附加到日志请求中。

在表单的处理页面中，包括以下代码以将输入的表单值附加到请求数据（除了将提交的表单值写入外部数据库或其他位置之外）：

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

此过程会将定义的表单值附加到“表单处理”页面的请求数据中。 在日志数据中，附加的值可用作表单处理页面的查询字符串，如下图所示。 例如，v_1、v_2、v_3和v_4现在将是查询字符串，其中包含输入到相应表单字段中的数据。 您可以对要捕获的任何其他表单字段和值复制上一个示例中描述的语法：

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

如果您希望捕获每个表单字段和值以供分析，可以使用以下语法：

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

此示例将采用HTML内存在的所有表单字段及其各自的值，并将它们作为查询字符串附加到“表单处理”页面的日志条目中。 请注意，这将包括表单中存在的任何隐藏字段。

日志数据将得到增强，如下表所示：

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_1 | 与NAME查询字符串关联的值 | v_1=John Smith |
| v_2 | 与CITY查询字符串关联的值 | v_2=洛杉矶 |
| v_3 | 与STATE查询字符串关联的值 | v_3=California |
| v_4 | 与ZIP查询字符串关联的值 | v_4=90210 |

<!-- <a id="section_55C623AC973246DC9EBECD48DA1EE0F7"></a> -->
