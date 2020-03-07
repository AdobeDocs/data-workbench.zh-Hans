---
description: 如果客户端可以通过多个网络（例如，通过企业内部网和Internet）访问Insight Server，则地址文件必须为服务器的每个IP地址定义单独的网络位置。
solution: Insight
title: Insight Server的多个IP地址
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insight Server的多个IP地址{#multiple-ip-addresses-for-an-insight-server}

如果客户端可以通过多个网络（例如，通过企业内部网和Internet）访问Insight Server，则地址文件必须为服务器的每个IP地址定义单独的网络位置。

例如，如果服务器在内部网络上的 [!DNL VS01.myCompany.com] IP地址为10.2.1.70，而在Internet上的IP地址为65.196.125.167，则地址文件将包括每个地址的网络位置，如下例所示：

```
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
```

当用户连接到某 [!DNL Insight Server]个服务器时，他们使用NetworkLocation参数（在客户端用户界面中）来指定要解决服务器通用名称的网络位置。 例如，如果给定一个地址文件，并且上面显示两个NetworkLocations，则用户会将NetworkLocation参数设置为“MyCorporate Intranet”，以通过内部网络连接到该网络，并将“Internet”设置为通过Internet连接到服务器。 [!DNL Insight Server]
