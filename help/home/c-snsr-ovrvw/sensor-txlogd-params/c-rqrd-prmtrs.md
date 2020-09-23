---
description: 有关所需传感器txlogd.conf参数的信息。
solution: Analytics
title: 必需的参数
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---


# 必需的参数{#required-parameters}

有关所需传感器txlogd.conf参数的信息。

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
   <td colname="col2"> <p>唯一标识此传感器的字符 <span class="wintitle"> 串</span>。 </p> <p> <span class="wintitle"> 传感器</span> 将SensorID附加到它发送到Data Workbench Server的每个事件 <span class="keyword"> 记录中</span>。 SensorID使来自此Web服务器的事件数据能够与其他传感器捕获的事件数据 <span class="wintitle"> 区别</span>。 </p> <p>尽管SensorID可以由任意字符串组成，但按惯例，Web服务器的名称会使用其捕获的事件 <span class="wintitle"> 的Web</span> 服务器的名称。 使用服务器名称作为传感器ID，可以在分析阶段轻松确定事件源。 它还确保传感器ID在实现中是唯一的。 </p> <p>示例： <span class="filepath"> 传感器ID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器地址 </td> 
   <td colname="col2"> <p>此传感器向 <span class="keyword"> 其发送事件</span> ,Data Workbench Server的 <span class="wintitle"> 地址</span> 。 </p> <p>注释：  <p>When working in a clustered environment, <span class="wintitle"> Sensor</span> should be configured to access the master <span class="keyword"> data workbench server</span> to avoid synchronization issues. In Data Workbench you can view information about the processing <span class="keyword"> data workbench servers</span> in your cluster using the Related Servers menu item in the <span class="wintitle"> Servers Manager</span>. 有关“Servers Manager(服务器 <span class="wintitle"> 管理器</span>)”的详细信 <i><span class="keyword"> 息</span><span class="wintitle"> ，请参</span> 阅《Data Workbench传感器指南</i>》。 </p> <p>如果Web服务器可以通过DNS解析服务器名称，则可以按名称指定服务器的地址。 否则，必须指定服务器的数字IP地址。 </p> <p>示例： <span class="filepath"> 服务器地址10.1.0.7</span> 或 </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>传感器 <span class="wintitle"> 是使用</span> HTTP还是HTTPS与Data Workbench Server <span class="keyword"> 进行通信</span> 。 对于HTTPS设置为“on”，对于HTTP设置为“off”。 </p> <p>示例： <span class="filepath"> SSL打开</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器端口 </td> 
   <td colname="col2"> <p>Data Workbench服务器监 <span class="keyword"> 听事件</span> 数据的端口。 </p> <p>示例： <span class="filepath"> 服务器端口443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>仅当SSL参数设置为“on”时才需要。 </p> <p>此传感器向其发送 <span class="keyword"> 事件数据</span> ,Data Workbench服 <span class="wintitle"> 务器的公</span> 用名称。 </p> <p>您指定的值必须与Data Workbench Server许可证证书上显示的公 <span class="keyword"> 用名称</span> 完全匹配。 </p> <p>示例： <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>仅当SSL参数设置为“on”时才需要。 </p> <p>证书颁发机构(trust_ca_cert<span class="filepath"> .pem)文件所在的目录</span>。 </p> <p>示例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 队列文件 </td> 
   <td colname="col2"> <p>在运行Internet <span class="wintitle"> 信息服务</span> (IIS)版本5.x或6.x的Microsoft Windows 2000或2003 Server计算机上安装传感器不需要。 </p> <p>磁盘队列文件的完全限定名称。 </p> <p>尽管可以为此文件指定任何名称，但根据惯例，队列文件名 <span class="filepath"> 为VisualSensor.dat</span>。 </p> <p>对于 <span class="wintitle"> Unix上</span> 的传感器安装，可以将此文件放在任意位置。 在运行Java Web服务器的Windows上，必须将此文件放在与发射器相同的目录中。 对于所有其他Web服务器，此文件应位于/var/queue目录中。 </p> <p>示例： <span class="filepath"> 队列文件/var/queue/VisualSensor.dat</span> </p> <p> <p>注意： 请确保为此文件分配的设备有足够的可用空间来容纳所需大小的队列。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>一个整数，表示磁盘队列文件的大小（以MB为单位）。 </p> <p>对于 <span class="wintitle"> Microsoft</span> Windows上的传感器安装，队列文件本身创建在与发射器相同的目录中，并命名 <span class="filepath"> 为Diskq2000.log</span>。 </p> <p>以下示例将队列大小设置为200 MB: </p> <p>队列大小200 </p> <p>以下示例将队列大小设置为2 GB: </p> <p>队列大小2000 </p> </td> 
  </tr> 
 </tbody> 
</table>

