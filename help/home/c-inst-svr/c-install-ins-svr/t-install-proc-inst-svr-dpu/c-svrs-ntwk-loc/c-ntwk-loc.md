---
description: 从概念上讲，地址文件与联网计算机上的ETC&bsol;HOSTS文件具有相同的用途。
solution: Insight
title: 网络位置
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
translation-type: tm+mt
source-git-commit: e8612fab1c13ca5262816dde7deaa6fd8bedbc62

---


# 网络位置{#network-locations}

从概念上讲，地址文件与联网计算机上的ETC&amp;bsol;HOSTS文件具有相同的用途。

但是，与描述单个名称集合的HOSTS文件不同，地址文件包含多个名称集合（称为网络位置）。

网络位置是地址定义的命名集合。 集合中的每个地址定义都将一个通用名称与一个IP地址相关联。

在地址文件中，网络位置在称为NetworkLocation的结构中定义。 以下示例中的NetworkLocation定义了一个名为“MyCorporate Intranet”的网络位置。它包含一个地址定义，该定义将公 [!DNL VS01.myCompany.com] 用名称映射到IP地址“10.2.1.70”。

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

如上面的示例所示，NetworkLocation结构由三个主要参数组成：

<table id="table_9142A0EFA15E4C37975E7ACE234F6FDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> 定义零个或多个AddressDefinitions。 每个AddressDefinion都将公用名称与IP地址相关联。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 为NetworkLocation指定名称。 分配给NetworkLocation的名称在地址文件中必须是唯一的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父项 </td> 
   <td colname="col2"> <p>指定其成员包含在此NetworkLocation中的另一个NetworkLocation的名称。 此参数使一个NetworkLocation能够扩展另一个。 </p> <p>可以将“Parent（父）”参数设置为“DNS”，以将NetworkLocation扩展到客户端的普通DNS系统。 </p> <p>示例：父项=字符串：DNS </p> <p>当DNS是父代时，当客户端无法通过NetworkLocation解析该名称时，客户端会尝试使用客户端计算机的DNS系统解析公用名称。 </p> </td> 
  </tr> 
 </tbody> 
</table>
