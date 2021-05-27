---
description: 有关所需传感器txlogd.conf参数的信息。
title: 必需的参数
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
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
   <td colname="col2"> <p>唯一标识此<span class="wintitle">传感器</span>的字符串。 </p> <p> <span class="wintitle"> </span> 传感器将传感器ID附加到它发送到Data Workbench Server的每 <span class="keyword"> 个事件记录</span>。传感器ID允许将来自此Web服务器的事件数据与其他<span class="wintitle">传感器</span>捕获的事件数据区分开来。 </p> <p>尽管传感器ID可以由任意字符串组成，但按惯例，仍会使用Web服务器的名称，该服务器的事件是<span class="wintitle">传感器</span>捕获的。 使用服务器名称作为传感器ID，可以轻松确定分析阶段事件的来源。 它还可确保传感器ID在实施中是唯一的。 </p> <p>示例：<span class="filepath">传感器ID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器地址 </td> 
   <td colname="col2"> <p>此<span class="wintitle">传感器</span>将事件数据发送到的<span class="keyword"> Data Workbench Server</span>的地址。 </p> <p>注释：  <p>在群集环境中工作时，应将<span class="wintitle">传感器</span>配置为访问主控的<span class="keyword"> Data Workbench Server</span>以避免同步问题。 在Data Workbench中，您可以使用<span class="wintitle">服务器管理器</span>中的“相关服务器”菜单项，查看有关群集中处理<span class="keyword"> Data Workbench Server</span>的信息。 有关<span class="wintitle">服务器管理器</span>的详细信息，请参阅<i><span class="keyword">Data Workbench</span><span class="wintitle">传感器</span>指南</i>。 </p> <p>如果您的Web服务器可以通过DNS解析服务器名称，则可以按名称指定服务器的地址。 如果没有，则必须指定服务器的数字IP地址。 </p> <p>示例：<span class="filepath"> ServerAddress 10.1.0.7</span>或 </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p><span class="wintitle">传感器</span>是否使用HTTP或HTTPS与<span class="keyword"> Data Workbench Server</span>通信。 对于HTTPS，设置为“on”；对于HTTP，设置为“off”。 </p> <p>示例：<span class="filepath"></span>上的SSL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p><span class="keyword"> Data Workbench Server</span>侦听事件数据的端口。 </p> <p>示例：<span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>仅当SSL参数设置为“on”时才需要此参数。 </p> <p>此<span class="wintitle">传感器</span>将事件数据发送到的<span class="keyword"> Data Workbench Server</span>的通用名称。 </p> <p>您指定的值必须与<span class="keyword"> Data Workbench Server</span>许可证证书上显示的通用名称完全匹配。 </p> <p>示例：<span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>仅当SSL参数设置为“on”时才需要此参数。 </p> <p>证书颁发机构(<span class="filepath"> trust_ca_cert.pem</span>)文件所在的目录 </p> <p>示例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 队列文件 </td> 
   <td colname="col2"> <p>在运行Internet Information Service(IIS)版本5.x或6.x的Microsoft Windows 2000或2003服务器计算机上安装<span class="wintitle">传感器</span>时，不需要。 </p> <p>磁盘队列文件的完全限定名称。 </p> <p>虽然可以为此文件指定任何名称，但按照惯例，队列文件名为<span class="filepath"> VisualSensor.dat</span>。 </p> <p>对于Unix上的<span class="wintitle">传感器</span>安装，可以将此文件放在任意位置。 在运行Java Web服务器的Windows上，必须将此文件放置在与发送器相同的目录中。 对于所有其他Web服务器，此文件应位于/var/queue目录中。 </p> <p>示例：<span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>注意： 确保为该文件分配的设备有足够的可用空间来容纳所需大小的队列。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>表示磁盘队列文件大小(MB)的整数。 </p> <p>对于Microsoft Windows上的<span class="wintitle">传感器</span>安装，队列文件本身创建在与发送器相同的目录中，名为<span class="filepath"> Diskq2000.log</span>。 </p> <p>以下示例将队列大小设置为200 MB: </p> <p>队列大小200 </p> <p>以下示例将队列大小设置为2 GB: </p> <p>队列大小2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
