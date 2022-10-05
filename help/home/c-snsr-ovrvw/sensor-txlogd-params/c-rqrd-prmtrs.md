---
description: 有关所需传感器txlogd.conf参数的信息。
title: 必需的参数
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# 必需的参数{#required-parameters}

{{eol}}

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
   <td colname="col2"> <p>唯一标识此字符串的字符串 <span class="wintitle"> 传感器</span>. </p> <p> <span class="wintitle"> 传感器</span> 将传感器ID附加到它发送到的每个事件记录 <span class="keyword"> data workbench server</span>. 传感器ID允许将来自此Web服务器的事件数据与其他服务器捕获的事件数据区分开来 <span class="wintitle"> 传感器</span>. </p> <p>尽管传感器ID可以由任意字符串组成（按惯例），但是Web服务器的名称(其事件为 <span class="wintitle"> 传感器</span> 使用捕获。 使用服务器名称作为传感器ID，可以轻松确定分析阶段事件的来源。 它还可确保传感器ID在实施中是唯一的。 </p> <p>示例： <span class="filepath"> 传感器ID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器地址 </td> 
   <td colname="col2"> <p>地址 <span class="keyword"> data workbench server</span> 这 <span class="wintitle"> 传感器</span> 发送事件数据。 </p> <p>注释：  <p>在群集环境中工作时， <span class="wintitle"> 传感器</span> 应配置为访问主控 <span class="keyword"> data workbench server</span> 以避免同步问题。 在Data Workbench中，您可以查看有关处理的信息 <span class="keyword"> data workbench服务器</span> 的“相关服务器”菜单项 <span class="wintitle"> 服务器管理器</span>. 有关 <span class="wintitle"> 服务器管理器</span>，请参阅 <i><span class="keyword"> Data Workbench</span><span class="wintitle"> 传感器</span> 指南</i>. </p> <p>如果您的Web服务器可以通过DNS解析服务器名称，则可以按名称指定服务器的地址。 如果没有，则必须指定服务器的数字IP地址。 </p> <p>示例： <span class="filepath"> ServerAddress 10.1.0.7</span> 或 </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>是否 <span class="wintitle"> 传感器</span> 通信 <span class="keyword"> data workbench server</span> 使用HTTP或HTTPS。 对于HTTPS，设置为“on”；对于HTTP，设置为“off”。 </p> <p>示例： <span class="filepath"> SSL on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>端口 <span class="keyword"> data workbench server</span> 侦听事件数据。 </p> <p>示例： <span class="filepath"> 服务器端口443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>仅当SSL参数设置为“on”时才需要此参数。 </p> <p>的通用名称 <span class="keyword"> data workbench server</span> 这 <span class="wintitle"> 传感器</span> 发送事件数据。 </p> <p>您指定的值必须与 <span class="keyword"> data workbench server</span> 许可证证书。 </p> <p>示例： <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>仅当SSL参数设置为“on”时才需要此参数。 </p> <p>证书颁发机构(<span class="filepath"> trust_ca_cert.pem</span>)文件 </p> <p>示例： </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 队列文件 </td> 
   <td colname="col2"> <p>不需要 <span class="wintitle"> 传感器</span> 在运行Internet Information Service(IIS)版本5.x或6.x的Microsoft Windows 2000或2003 Server计算机上进行安装。 </p> <p>磁盘队列文件的完全限定名称。 </p> <p>虽然可以为此文件指定任何名称，但按照惯例，队列文件将名为 <span class="filepath"> VisualSensor.dat</span>. </p> <p>对于 <span class="wintitle"> 传感器</span> 在Unix上安装时，可以将此文件放在任意位置。 在运行Java Web服务器的Windows上，必须将此文件放置在与发送器相同的目录中。 对于所有其他Web服务器，此文件应位于/var/queue目录中。 </p> <p>示例： <span class="filepath"> 队列文件/var/queue/VisualSensor.dat</span> </p> <p> <p>注意：确保为该文件分配的设备有足够的可用空间来容纳所需大小的队列。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>表示磁盘队列文件大小(MB)的整数。 </p> <p>对于 <span class="wintitle"> 传感器</span> 在Microsoft Windows上安装时，队列文件本身将创建在与发送器相同的目录中，并且名为 <span class="filepath"> Diskq2000.log</span>. </p> <p>以下示例将队列大小设置为200 MB: </p> <p>队列大小200 </p> <p>以下示例将队列大小设置为2 GB: </p> <p>队列大小2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
