---
description: 如果网络防火墙不阻止从Insight计算机访问中继器服务器，则可以在中继器服务器与Insight之间创建连接，以便使用Insight管理中继器服务器。
solution: Insight
title: 在Insight和Repeater之间创建连接
uuid: dccce83a-8708-4763-a19a-64d905a9f624
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 在Insight和Repeater之间创建连接{#creating-a-connection-between-insight-and-repeater}

如果网络防火墙不阻止从Insight计算机访问中继器服务器，则可以在中继器服务器与Insight之间创建连接，以便使用Insight管理中继器服务器。

**在中继器服务器之[!DNL Insight]间创建连接**

1. 在选 [!DNL Insight]项卡中，单 [!DNL Admin] 击缩略图以打开“配置与服 **[!UICONTROL Configure Connections to Servers]** 务器的连接”工作区。
1. 在窗 [!DNL Insight.cfg] 口中，右键单击并 **[!UICONTROL Servers]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Server]**。
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
   <td colname="col2">（可选）您希望此Insight用于在其用户界 <span class="keyword"> 面中表示</span> Repeater服务器的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> <p>中继器服务器的主机名或数字IP地址。 </p> <p>示例： <span class="filepath"> Repeater.mycompany.com</span> 或192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate（SSL 客户端证书） </td> 
   <td colname="col2"> <p>可选参数，除非您拥有多个证书。The name of the file that contains the digital certificate for this copy of <span class="keyword"> Insight</span>. (这是您在安装 <span class="keyword"> Insight时下载的文件</span>。) </p> <p>示例：<span class="filepath">Samantha Smith.pem</span></p> <p>If you leave this parameter blank, <span class="keyword"> Insight</span> uses whatever certificate is present. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL服务器 </p> <p>通用名称 </p> </td> 
   <td colname="col2">分配给中继器服务器的通用名称。 此名称必须与为其许可证证书中分配给中继器服务器的通用名称相匹配。 如果您有权访问中继器的证书文件(<span class="filepath"> Certificates\server_cert.pem</span>)，则可以通过使用文本编辑器（如记事本）打开该文件来查找公用名称。 公用名称在证书的CN字段中标识。 </td> 
  </tr> 
 </tbody> 
</table>

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**. [!DNL Insight] 将尝试使用您指定的设置连接到中继服务器。 如果已建立连接，则界面中会显示绿色的服务器 [!DNL Servers Manager] 图标。 如果无法建立连接，则显示红色图标。

   For more information about the [!DNL Servers Manager] interface, see the * [!DNL Insight] User Guide*.

