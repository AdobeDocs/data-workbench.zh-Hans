---
description: 有关所需的传感器txlogd.conf参数的信息。
solution: Insight
title: 必需参数
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Required Parameters{#required-parameters}

有关所需的传感器txlogd.conf参数的信息。

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 在此参数中…… </th> 
   <th colname="col2" class="entry"> 在“管理工具”中指定分类的... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 传感器ID </td> 
   <td colname="col2"> <p>唯一标识此传感器的字符 <span class="wintitle"> 串</span>。 </p> <p> <span class="wintitle"> 传感器</span> 将SensorID附加到它发送到Data Workbench Server的每个事 <span class="keyword"> 件记录中</span>。 SensorID使来自此Web服务器的事件数据能够与其他传感器捕获的事件数据区 <span class="wintitle"> 分</span>。 </p> <p>尽管SensorID可以由任意字符串组成，但按惯例，Web服务器的名称会使用传感器捕获的 <span class="wintitle"> 事件</span> 。 使用服务器名作为传感器ID可轻松确定分析阶段的事件源。 它还确保SensorID在实现中是唯一的。 </p> <p>示例：传 <span class="filepath"> 感器ID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器地址 </td> 
   <td colname="col2"> <p>此传感器向其 <span class="keyword"> 发送事件数据的Data Workbench</span> Server <span class="wintitle"> 的地</span> 址。 </p> <p>注释:  <p>When working in a clustered environment, <span class="wintitle"> Sensor</span> should be configured to access the master <span class="keyword"> data workbench server</span> to avoid synchronization issues. In Data Workbench you can view information about the processing <span class="keyword"> data workbench servers</span> in your cluster using the Related Servers menu item in the <span class="wintitle"> Servers Manager</span>. 有关“服务器管理器” <span class="wintitle"> 的详细信息</span>，请参阅《Data Workbench <i><span class="keyword"> Sensor</span><span class="wintitle"> Guide》</span></i>。 </p> <p>如果Web服务器可以通过DNS解析服务器名称，则可以按名称指定服务器的地址。 否则，必须指定服务器的数字IP地址。 </p> <p>示例：服 <span class="filepath"> 务器地址10.1.0.7</span> 或 </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>传感器 <span class="wintitle"> 是否使用</span> HTTP或HTTPS与Data Workbench Server <span class="keyword"></span> 通信。 对于HTTPS，设置为“on”，对于HTTP，设置为“off”。 </p> <p>示例： <span class="filepath"> 打开SSL</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器端口 </td> 
   <td colname="col2"> <p>Data Workbench Server监听事 <span class="keyword"> 件数据的端口</span> 。 </p> <p>示例：服 <span class="filepath"> 务器端口443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>仅当SSL参数设置为“on”时才需要。 </p> <p>此传感器向其发送事 <span class="keyword"> 件数据的Data Workbench</span> Server <span class="wintitle"> 的公用名称</span> 。 </p> <p>您指定的值必须与Data Workbench Server许可证证书上显示的公 <span class="keyword"> 用名称完全匹配</span> 。 </p> <p>示例： <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>仅当SSL参数设置为“on”时才需要。 </p> <p>证书颁发机构(<span class="filepath"> trust_ca_cert.pem</span>)文件所在的目录 </p> <p>示例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 队列文件 </td> 
   <td colname="col2"> <p>在运行 <span class="wintitle"></span> Internet Information Service(IIS)5.x或6.x版的Microsoft Windows 2000或2003 Server计算机上安装传感器不需要。 </p> <p>磁盘队列文件的完全限定名称。 </p> <p>尽管可以为此文件指定任何名称，但根据惯例，队列文件名为 <span class="filepath"> VisualSensor.dat</span>。 </p> <p>对于 <span class="wintitle"> Unix上的传感器安装</span> ，您可以将此文件放在任何位置。 在运行Java Web服务器的Windows上，必须将此文件放在与发射器相同的目录中。 对于所有其他Web服务器，此文件应位于/var/queue目录中。 </p> <p>示例：队列文 <span class="filepath"> 件/var/queue/VisualSensor.dat</span> </p> <p> <p>注意： 确保为该文件分配的设备有足够的可用空间以容纳所需大小的队列。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>一个整数，它表示磁盘队列文件的大小（以MB为单位）。 </p> <p>对于 <span class="wintitle"> Microsoft</span> Windows上的传感器安装，队列文件本身创建在与发射器相同的目录中，并命名为 <span class="filepath"> Diskq2000.log</span>。 </p> <p>以下示例将队列大小设置为200 MB: </p> <p>QueueSize 200 </p> <p>以下示例将队列大小设置为2 GB: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>

