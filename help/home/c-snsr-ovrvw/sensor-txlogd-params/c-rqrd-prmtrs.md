---
description: 有关所需传感器txlogd.conf参数的信息。
title: 必需的参数
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
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
   <td colname="col2"> <p>唯一标识此<span class="wintitle">传感器</span>的字符串。 </p> <p> <span class="wintitle"> Sensor</span> 将SensorID附加到它发送到Data Workbench Server的每个事件 <span class="keyword"> 记录中</span>。SensorID使来自此Web服务器的事件数据能够与由其他<span class="wintitle"> Sensors</span>捕获的事件数据区别开来。 </p> <p>尽管SensorID可以由任意字符串组成，但按惯例，会使用Web服务器的名称，该服务器的事件是<span class="wintitle"> Sensor</span>捕获的。 使用服务器名作为传感器ID可轻松确定分析阶段事件的源。 它还确保SensorID在实现中是唯一的。 </p> <p>示例：<span class="filepath">传感器ID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器地址 </td> 
   <td colname="col2"> <p>此<span class="wintitle">传感器</span>向其发送事件数据的<span class="keyword"> Data Workbench Server</span>的地址。 </p> <p>注释：  <p>在群集环境中工作时，应将<span class="wintitle">传感器</span>配置为访问主控<span class="keyword"> Data Workbench Server</span>以避免同步问题。 在Data Workbench中，您可以使用<span class="wintitle"> Servers Manager</span>中的“相关服务器”菜单项来视图有关群集中处理<span class="keyword"> Data Workbench Servers</span>的信息。 有关<span class="wintitle">服务器管理器</span>的详细信息，请参阅<i><span class="keyword">Data Workbench</span><span class="wintitle">传感器</span>指南</i>。 </p> <p>如果Web服务器可以通过DNS解析服务器名称，则可以按名称指定服务器的地址。 否则，必须指定服务器的数字IP地址。 </p> <p>示例：<span class="filepath"> ServerAddress 10.1.0.7</span>或 </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p><span class="wintitle">传感器</span>是否使用HTTP或HTTPS与<span class="keyword"> Data Workbench Server</span>通信。 对于HTTPS设置为“on”，对于HTTP设置为“off”。 </p> <p>示例：<span class="filepath"></span>上的SSL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器端口 </td> 
   <td colname="col2"> <p><span class="keyword"> Data Workbench Server</span>监听事件数据的端口。 </p> <p>示例：<span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>仅当SSL参数设置为“on”时才需要。 </p> <p>此<span class="wintitle">传感器</span>向其发送事件数据的<span class="keyword"> Data Workbench Server</span>的公用名称。 </p> <p>您指定的值必须与<span class="keyword"> Data Workbench Server</span>许可证证书上显示的公用名称完全匹配。 </p> <p>示例：<span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>仅当SSL参数设置为“on”时才需要。 </p> <p>证书颁发机构(<span class="filepath"> trust_ca_cert.pem</span>)文件所在的目录 </p> <p>示例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 队列文件 </td> 
   <td colname="col2"> <p>在运行Internet信息服务(IIS)5.x或6.x版的Microsoft Windows 2000或2003 Server计算机上安装<span class="wintitle">传感器</span>时不需要。 </p> <p>磁盘队列文件的完全限定名。 </p> <p>虽然可以为此文件指定任何名称，但根据约定，队列文件名为<span class="filepath"> VisualSensor.dat</span>。 </p> <p>对于Unix上的<span class="wintitle">传感器</span>安装，可将此文件放置到任何位置。 在运行Java Web服务器的Windows上，必须将此文件放在与发射器相同的目录中。 对于所有其他Web服务器，此文件应位于/var/queue目录中。 </p> <p>示例：<span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>注意： 确保您分配此文件的设备有足够的可用空间以容纳所需的队列。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>一个整数，表示磁盘队列文件的大小（以MB为单位）。 </p> <p>对于Microsoft Windows上的<span class="wintitle">传感器</span>安装，队列文件本身创建在与发射器相同的目录中，名为<span class="filepath"> Diskq2000.log</span>。 </p> <p>下面的示例将队列大小设置为200 MB: </p> <p>队列大小200 </p> <p>下面的示例将队列大小设置为2 GB: </p> <p>队列大小2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
