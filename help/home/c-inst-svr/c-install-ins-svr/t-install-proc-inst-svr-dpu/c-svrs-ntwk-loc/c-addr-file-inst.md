---
description: Insight Server上安装的地址文件包含四个预定义的网络位置。
title: Insight Server 上安装的地址文件
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
exl-id: 12e9bfa2-99ac-4584-b761-38401d1bc3d1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---

# Insight Server 上安装的地址文件{#the-address-file-installed-on-insight-server}

{{eol}}

Insight Server上安装的地址文件包含四个预定义的网络位置。

下一节中的过程介绍如何配置此文件。

```
Locations = vector: 4 items  
  0 = NetworkLocation:  
    Addresses = vector: 1 items 
      0 = AddressDefinition:  
        Address = string:  
        Name = string:  
    Name = string:  
    Parent = string:  
  1 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight 
    Parent = string:  
  2 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight Server 
    Parent = string: 
  3 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Report Server 
    Parent = string:
```

* NetworkLocation 0是一个空的未命名网络位置，您编辑该位置以关联您的 [!DNL Insight Server] 到其IP地址。 如果服务器具有多个IP地址，则创建其他网络位置。
* NetworkLocation 1是 [!DNL Insight] 网络位置。 如果未明确设置NetworkLocation参数， [!DNL Insight] 通过此网络位置解析通用名称。

* NetworkLocation 2是 [!DNL Insight Server] 网络位置。 When [!DNL Insight Servers] 在群集中运行，它们使用此网络位置来解析服务器间通信的通用名称。

* NetworkLocation 3是 [!DNL Report] 服务器网络位置。 如果未明确设置NetworkLocation参数， [!DNL Report] 通过此网络位置解析通用名称。

## 配置地址文件 {#section-10caab9854a244e39b09071946f7bd27}

以下过程介绍如何配置地址文件以定义您的 [!DNL Insight Server].

1. 导航到 [!DNL Addresses] 文件夹。 [!DNL Insight Server] (例如， [!DNL C:\Adobe\Server\Addresses)].

1. 找到 [!DNL server.address] 文件，并重命名此文件以反映服务器的通用名称。 例如，如果公用名称为 [!DNL server.mycompany.com]，则需要重命名文件 [!DNL server.mycompany.com.address].

1. 在文本编辑器（如记事本）中打开重命名的文件。
1. 编辑NetworkLocation 0 ，以指定 [!DNL Insight Server] 如下所示。 如果您的服务器有多个IP地址，请使用NetworkLocation 0在本地不可路由网络（例如，其内部网络位置）上指定服务器的IP地址。

   ```
   Locations = vector: 3 items 
   0 = NetworkLocation: 
     Addresses = vector: 1 items 
       0 = AddressDefinition: 
         Address = string: IPAddress 
         Name = string: CommonName 
     Name = string: NetworkLocationName 
     Parent = string: 
   ```

<table id="table_02C2A1630CCD40C4A51B314C3CB683F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 对于此值…… </th> 
   <th colname="col2" class="entry"> 在“管理工具”中指定分类的 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>IP 地址</i> </td> 
   <td colname="col2"> <p>的IP地址数字 <span class="keyword"> Insight Server </span> 机器。 </p> <p>示例：192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>通用名称 </i> </td> 
   <td colname="col2"> <p>分配给的数字证书的通用名称 <span class="keyword"> Insight Server </span>. </p> <p>示例： <span class="filepath"> server.mycompany.com </span></p> <p>注意：请确保键入此名称，该名称应与证书上显示的名称完全相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>网络位置名称 </i> </td> 
   <td colname="col2"> <p>要分配给此NetworkLocation表示的通用名称和IP地址集合的名称。 地址文件中的名称必须唯一。 </p> <p>示例：公司内联网 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 如果 [!DNL Insight Server] 具有其他IP地址，请为每个地址创建一个附加的NetworkLocation。 （执行此操作的一种简单方法是制作您在上面创建的NetworkLocation的副本，并更新副本中的IP地址。）

   您可以将新的NetworkLocation添加到地址文件的末尾，或在现有NetworkLocation定义之间插入它。 (NetworkLocation在地址文件中的位置不重要；但是， [!DNL Insight], [!DNL Insight Server]和 [!DNL Report] Server NetworkLocations通常位于文件末尾。)

   在添加了必要的NetworkLocations后，请执行以下操作以重新编号文件中的项目：

   1. 更新“位置”结构的项目计数，以匹配文件中NetworkLocation定义的总数。 例如，如果文件包含四个NetworkLocation定义，则“位置”行将如下所示：

      ```
      Locations = vector: 4 items
      ```

   1. 更新NetworkLocation项编号，以便NetworkLocations连续编号（从0开始）。
   有关定义 [!DNL Insight Server] 包含两个IP地址，请参阅此部分中的示例。

1. 在 [!DNL Insight] 和 [!DNL Report] 服务器网络位置，编辑如下所示的父参数，以指定 [!DNL Insight] 和 [!DNL Report] 使用作为其默认网络位置。 （有关配置Parent参数时的样式示例，请参阅此部分中的示例。）

   ```
   1 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight 
     Parent = string: ClientDefaultNetworkLocation 
   
   3 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Report Server 
     Parent = string: ClientDefaultNetworkLocation
   ```

   如果 [!DNL Insight Server] 具有单个IP地址，因此只有一个NetworkLocation ，将父参数指向该NetworkLocation。 如果 [!DNL Insight Server] 具有多个IP地址，请将父参数指向NetworkLocation ，该NetworkLocation定义您的 [!DNL Insight] 和 [!DNL Report] 客户端连接最频繁。

1. 在 [!DNL Insight Server] 网络位置，编辑如下所示的父参数，以指向服务器用来解析其他的通用名称的NetworkLocation [!DNL Insight Servers] 在群集中运行时。 (尽管不使用此网络位置，除非 [!DNL Insight Server] 在群集中运行时，最好将Parent（父项）参数指向标识服务器内部IP地址的网络位置，即使是在单个服务器配置中也是如此。

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

以下示例显示一个已完成的地址文件。 此文件定义了五个网络位置。

* NetworkLocation项目0和1定义名为“MyCorporateIntranet”和“Internet”的网络位置。 这些网络位置为名为 [!DNL VS01.myCompany.com].
* NetworkLocation项目2是 [!DNL Insight] 网络位置。 这是使用的默认网络位置 [!DNL Insight]. 在本例中， [!DNL Insight] 网络位置从“Internet”NetworkLocation继承其AddressDefinitions。

* NetworkLocation项目3是 [!DNL Insight Server] 网络位置。 这是默认的网络位置 [!DNL Insight Server] 在与群集中的其他服务器通信时使用。 在本例中， [!DNL Insight Server] 网络位置从“MyCorporate Intranet”NetworkLocation继承其AddressDefinition。

* NetworkLocation项目4是 [!DNL Report] 服务器网络位置。 这是使用的默认网络位置 [!DNL Report]. 在本例中， [!DNL Report] 服务器网络位置从“Internet”NetworkLocation继承其AddressDefinition。

   ```
   Locations = vector: 5 items 
     0 = NetworkLocation:  
       Addresses = vector: 1 items 
         0 = AddressDefinition:  
           Address = string: 10.2.1.70 
           Name = string: VS01.myCompany.com 
       Name = string: MyCorporateIntranet 
       Parent = string:  
   
     1 = NetworkLocation:  
       Addresses = vector: 1 items 
         0 = AddressDefinition:  
           Address = string: 65.196.125.167 
           Name = string: VS01.myCompany.com 
       Name = string: Internet 
       Parent = string: 
   
     2 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight 
       Parent = string: Internet 
   
     3 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight Server 
       Parent = string: MyCorporateIntranet 
   
     4 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Report Server 
       Parent = string: Internet
   ```
