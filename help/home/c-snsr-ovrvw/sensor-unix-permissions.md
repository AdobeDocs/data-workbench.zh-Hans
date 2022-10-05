---
description: 有关传感器UNIX文件权限的信息，如收集器模块、发送器进程、配置文件等。
title: 传感器 UNIX 文件权限
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
exl-id: 07cbc7df-c628-437d-9ca1-b006da8de242
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 5%

---

# 传感器 UNIX 文件权限{#sensor-unix-file-permissions}

{{eol}}

有关传感器UNIX文件权限的信息，如收集器模块、发送器进程、配置文件等。

## 收集器模块 {#section-49c855baece24c4695184bfcbeeddebf}

<table id="table_0B972ABD2A5342CA8A6FE80EB666298A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 质量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>文件名 </p> </td> 
   <td colname="col2"> <p>mod_visual_sciences.so(在Apache Web服务器和IBM HTTP服务器上) </p> <p>libvisual_sciences.so和J2EECollector.jar（在J2EE应用程序服务器上） </p> <p>aol_visual_sciences.so（在AOL Web服务器上） </p> <p>saf_visual_sciences.so（在Sun Java Web服务器上） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>默认权限 </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x(IBM HTTP和Apache 1.3.x) </p> <p>rwx rwx r-x(Apache 2.0.x) </p> <p>rwx —x —x（J2EE、AOL和Sun Java Web服务器） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>阅读者 </p> </td> 
   <td colname="col2"> <p>Web服务器，有时以根用户的身份运行，但经常在特定用户帐户下运行 </p> <p>如果Web服务器在非根帐户下运行，则此文件的权限必须允许该帐户读取它。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>运行方式 </p> </td> 
   <td colname="col2"> <p>Web服务器中的子进程 </p> <p>子进程在Web服务器配置中指定的用户帐户下运行。 在许多服务器上，这是一个特殊帐户，其权限非常有限，称为“无人” — 但并非所有Web服务器都使用此帐户。 检查Web服务器的配置文件以确定设置的用户帐户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>读取自 </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>diskQueue文件 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 写入 </td> 
   <td colname="col2"> diskQueue文件 </td> 
  </tr> 
 </tbody> 
</table>

## 发射机过程 {#section-8af432472e9d4bd9a42270bf27adf33a}

<table id="table_3028CC9640D54016BD8CA7F9CAA34280"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 质量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 文件名 </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>默认权限 </p> </td> 
   <td colname="col2"> <p>rw- r— r—(IBM HTTP、AOL和Sun Java Web服务器) </p> <p>rw-rw- r — （Apache Web服务器和J2EE应用程序服务器） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 阅读者 </td> 
   <td colname="col2"> 发射机程序 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 编写者 </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## 配置文件 {#section-341d85f2abf34a69970a0ff91b7e9123}

<table id="table_79AC614F5435443CB3CFB457B8375704"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 质量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 文件名 </td> 
   <td colname="col2"> txlogd.conf </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>默认权限 </p> </td> 
   <td colname="col2"> <p>rw- r— r—(IBM HTTP、AOL和Sun Java Web服务器) </p> <p>rw-rw- r — （Apache Web服务器和J2EE应用程序服务器） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 阅读者 </td> 
   <td colname="col2"> <p>收集器模块 </p> <p>发射机程序 </p> <p>负责安装、配置和维护传感器的管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 编写者 </td> 
   <td colname="col2"> 负责安装、配置和维护传感器的管理员 </td> 
  </tr> 
 </tbody> 
</table>

## 证书颁发机构文件 {#section-2818dff887b8456992bdc589fd8510f3}

<table id="table_ED8BEEEFA91245C3A6645D27B148A5A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 质量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 文件名 </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>默认权限 </p> </td> 
   <td colname="col2"> <p>rw- r— r—(IBM HTTP、AOL和Sun Java Web服务器) </p> <p>rw-rw- r — （Apache Web服务器和J2EE应用程序服务器） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 阅读者 </td> 
   <td colname="col2"> 发射机程序 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 编写者 </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## 磁盘队列 {#section-0407c52744de41af867d0b7933a69256}

<table id="table_35DB32228E7443FF90BE24AB14CBE54B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 质量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 文件名 </td> 
   <td colname="col2"> 用户定义的 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 默认权限 </td> 
   <td colname="col2"> rw-rw-rw — （所有服务器类型） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>阅读者 </p> </td> 
   <td colname="col2"> <p>收集器模块 </p> <p>发射机程序 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>编写者 </p> </td> 
   <td colname="col2"> <p>收集器模块 </p> <p>发射机程序 </p> </td> 
  </tr> 
 </tbody> 
</table>
