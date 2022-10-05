---
description: 如果网络防火墙不阻止从Insight计算机访问中继器服务器，则可以在中继器服务器与Insight之间创建连接，以便您可以使用Insight管理中继器服务器。
title: 在 Insight 与中继器之间创建连接
uuid: dccce83a-8708-4763-a19a-64d905a9f624
exl-id: 81e81db5-0517-41d4-a958-d08cd3975096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 9%

---

# 在 Insight 与中继器之间创建连接{#creating-a-connection-between-insight-and-repeater}

{{eol}}

如果网络防火墙不阻止从Insight计算机访问中继器服务器，则可以在中继器服务器与Insight之间创建连接，以便您可以使用Insight管理中继器服务器。

**在 [!DNL Insight] 和中继服务器**

1. 在 [!DNL Insight]，在 [!DNL Admin] ，单击 **[!UICONTROL Configure Connections to Servers]** 缩略图以打开“配置与服务器的连接”工作区。
1. 在 [!DNL Insight.cfg] 窗口，右键单击 **[!UICONTROL Servers]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. 对于新服务器，请完成以下参数：

<table id="table_DD79587255134B5A888A0F57CF10E5B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 对于该参数... </th> 
   <th colname="col2" class="entry"> 在“管理工具”中指定分类的... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2">（可选）您希望此名称的名称 <span class="keyword"> Insight</span> 用于在其用户界面中表示中继服务器。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> <p>中继器服务器的主机名或数字IP地址。 </p> <p>示例： <span class="filepath"> Repeater.mycompany.com</span> 或192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate（SSL 客户端证书） </td> 
   <td colname="col2"> <p>可选参数，除非您拥有多个证书。包含此副本的数字证书的文件名 <span class="keyword"> Insight</span>. (这是您在安装时下载的文件 <span class="keyword"> Insight</span>.) </p> <p>示例：<span class="filepath">Samantha Smith.pem</span></p> <p>如果将此参数留空， <span class="keyword"> Insight</span> 使用任何存在的证书。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL服务器 </p> <p>通用名称 </p> </td> 
   <td colname="col2">分配给中继服务器的通用名称。 此名称必须与许可证证书中分配给中继服务器的通用名称匹配。 如果您有权访问中继器的证书文件(<span class="filepath"> Certificates\server_cert.pem</span>)，则可以通过使用文本编辑器（如记事本）打开文件来找到通用名称。 公用名称在证书的CN字段中标识。 </td> 
  </tr> 
 </tbody> 
</table>

1. 通过右键单击保存文件 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**. [!DNL Insight] 将尝试使用您指定的设置连接到中继服务器。 如果已建立连接，则会在 [!DNL Servers Manager] 界面。 如果无法建立连接，则会显示一个红色图标。

   有关 [!DNL Servers Manager] 界面，请参见* [!DNL Insight] 用户指南*。
