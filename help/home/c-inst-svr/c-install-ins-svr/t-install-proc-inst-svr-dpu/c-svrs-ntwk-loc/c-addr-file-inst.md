---
description: Insight Server上安装的地址文件包含四个预定义的网络位置。
solution: Analytics
title: Insight Server 上安装的地址文件
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---


# Insight Server 上安装的地址文件{#the-address-file-installed-on-insight-server}

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

* NetworkLocation 0是一个空的、未命名的网络位置，您编辑它以将您的公用名称与 [!DNL Insight Server] 其IP地址关联。 如果服务器有多个IP地址，则创建其他NetworkLocations。
* NetworkLocation 1是网 [!DNL Insight] 络位置。 如果不显式设置NetworkLocation参数，则通过 [!DNL Insight] 此网络位置解析公用名称。

* NetworkLocation 2是网 [!DNL Insight Server] 络位置。 在群 [!DNL Insight Servers] 集中操作时，它们使用此网络位置解析服务器间通信的通用名称。

* NetworkLocation 3是服务 [!DNL Report] 器网络位置。 如果不显式设置NetworkLocation参数，则通过 [!DNL Report] 此网络位置解析公用名称。

## 配置地址文件 {#section-10caab9854a244e39b09071946f7bd27}

以下过程介绍如何配置地址文件以为您定义网络位置（或网络位置） [!DNL Insight Server]。

1. 导览至 [!DNL Addresses] 安装目录中的文 [!DNL Insight Server] 件夹(例如 [!DNL C:\Adobe\Server\Addresses)]。

1. 找到文 [!DNL server.address] 件并重命名此文件以反映服务器的通用名称。 例如，如果通用名称为， [!DNL server.mycompany.com]您将重命名该文件 [!DNL server.mycompany.com.address]。

1. 在文本编辑器（如记事本）中打开重命名的文件。
1. 编辑NetworkLocation 0以指定的公用名称和IP地 [!DNL Insight Server] 址，如下所示。 如果服务器有多个IP地址，请使用NetworkLocation 0在本地不可路由网络（例如，它在内部网络上的位置）上指定服务器的IP地址。

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
   <td colname="col2"> <p>Insight Server计算机的 <span class="keyword"> 数字IP </span> 地址。 </p> <p>例如： 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>通用名称 </i> </td> 
   <td colname="col2"> <p>分配给Insight Server的数字证书的 <span class="keyword"> 通用名 </span>称。 </p> <p>示例： <span class="filepath"> server.mycompany.com </span></p> <p>注意：请务必键入此名称，其显示方式与证书中相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>网络位置名称 </i> </td> 
   <td colname="col2"> <p>要分配给此NetworkLocation表示的公用名称和IP地址集合的名称。 该名称在地址文件中必须唯一。 </p> <p>示例：公司内部网 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 如果您 [!DNL Insight Server] 有其他IP地址，请为每个地址创建一个附加的NetworkLocation。 （执行此操作的一个简单方法是制作您在上面创建的NetworkLocation的副本并更新副本中的IP地址。）

   可以将新的NetworkLocation添加到地址文件的末尾，或在现有NetworkLocation定义之间插入它。 (NetworkLocation在地址文件中的位置不重要；但是， [!DNL Insight]、 [!DNL Insight Server]和 [!DNL Report] Server NetworkLocations通常放在文件末尾。)

   添加必要的NetworkLocations后，请执行以下操作以重新编号文件中的项：

   1. 更新“位置”结构的项计数，使其与文件中的NetworkLocation定义总数匹配。 例如，如果文件包含四个NetworkLocation定义，则“位置”行将如下所示：

      ```
      Locations = vector: 4 items
      ```

   1. 更新NetworkLocation项编号，以便NetworkLocations的编号是连续的（从0开始）。
   有关定义具有两个IP地址的地 [!DNL Insight Server] 址文件的示例，请参阅本节中的示例。

1. 在网络 [!DNL Insight] 和服 [!DNL Report] 务器网络位置中，编辑父参数，如下所示，指定NetworkLocation的名称，并将 [!DNL Insight] 其用作 [!DNL Report] 其默认网络位置。 （有关配置父参数时其外观的示例，请参阅本节中的示例。）

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

   如果 [!DNL Insight Server] 您有单个IP地址，因此只有一个NetworkLocation，请将父参数指向该NetworkLocation。 如果您 [!DNL Insight Server] 有多个IP地址，请将父参数指向NetworkLocation，该NetworkLocation定义您和客户端最 [!DNL Insight] 频繁 [!DNL Report] 连接的地址。

1. 在网 [!DNL Insight Server] 络位置中，编辑父参数，如下所示，指向服务器在群集中运行时用于解析其他名称的 [!DNL Insight Servers] NetworkLocation。 (尽管此网络位置在群集中 [!DNL Insight Server] 不使用，但是，即使在单个服务器配置中，也最好将父参数指向标识服务器内部IP地址的网络位置。)

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

以下示例显示了一个完整的地址文件。 此文件定义五个网络位置。

* NetworkLocation项目0和1定义名为“MyCorporateIntranet”和“Internet”的网络位置。 这些网络位置为名为的服务器定义了两个不同的IP地址 [!DNL VS01.myCompany.com]。
* NetworkLocation项2是网 [!DNL Insight] 络位置。 这是使用的默认网络位置 [!DNL Insight]。 在此示例中，网 [!DNL Insight] 络位置从“Internet” NetworkLocation继承其AddressDefinitions。

* NetworkLocation项3是网 [!DNL Insight Server] 络位置。 这是与群集中的其 [!DNL Insight Server] 他服务器通信时使用的默认网络位置。 在此示例中，网 [!DNL Insight Server] 络位置从“MyCorporate Intranet”NetworkLocation继承其AddressDefinition。

* NetworkLocation项4是服务器 [!DNL Report] 网络位置。 这是使用的默认网络位置 [!DNL Report]。 在此示例中，服 [!DNL Report] 务器网络位置从“Internet” NetworkLocation继承其AddressDefinitions。

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

