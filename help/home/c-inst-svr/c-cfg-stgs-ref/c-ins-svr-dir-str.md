---
description: 列表随Insight Server安装的文件以及注册后存在的文件，并首次运行。
title: Insight Server 目录结构
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---

# Insight Server 目录结构{#insight-server-directory-structure}

列表随Insight Server安装的文件以及注册后存在的文件，并首次运行。

## 安装程序包中包含的文件 {#section-daec17dab3e34c3c9e1ef65842cb91f1}

[!DNL Insight Server]安装包中包含以下目录：

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 目录 </th> 
   <th colname="col2" class="entry"> 描述 目录内容 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 访问控制 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server配 </span> 置文件，指定访问组的列表。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> 用于与<span class="keyword"> Insight Server </span>通信的地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 审计 </td> 
   <td colname="col2"> 每日访问日志，其中包含与<span class="keyword"> Insight Server </span>的所有尝试连接相关的详细信息。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 宾 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server可执 </span> 行项目文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificates </td> 
   <td colname="col2"> SSL数字证书。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 组件 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server组 </span> 件配置文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 用于处理服务器的组件 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server组 </span> 件配置文件，用 <span class="keyword"> 于处 </span> 理Insight Server群 <span class="keyword"> 集中的 </span> Insight Server。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 包含详细事件状态消息（包括错误消息）的每日事件日志。 由<span class="keyword"> Insight Server </span>捕获和记录的事件也会显示在Windows事件查看器中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日志 </td> 
   <td colname="col2"> <p>由<span class="wintitle">传感器</span>生成的日志文件。 </p> <p>"Logs"是默认的日志记录目录，但可能已在<span class="filepath"> communications.cfg </span>文件中指定了替代目录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 查找 </td> 
   <td colname="col2"> 查找文件，如自动机和搜索引擎列表。 <span class="keyword"> Insight Server必须 </span> 将所有查找文件加载到内存中。组件配置文件中引用的所有查找文件的总大小以及开销（例如，<span class="filepath"> FlatFileLookup </span>文件的每行12字节）不得超过加载所有其他软件应用程序后可用的物理或虚拟内存。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 配置文件 </td> 
   <td colname="col2"> <p>与每个用户档案（配置、工作区和可视化文件）相关的文件。 用户档案由数据集中的数据填充。 数据集包括事件数据（“日志数据”）；此类数据可通过安装<span class="wintitle">传感器</span>来捕获，通过网络信标或页面标签来传输，或从data warehouse输入。 <span class="keyword"> 可 </span> 以访问给定用户档案的Insight用户可以使用该用户档案的已处理数据集以及该用户档案中定义的工作区和可视化。 </p> <p>工作区是系统管理或分析的工作区。 Workspace可包含多个界面，其中显示有关系统性能的不同详细信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 软件 </td> 
   <td colname="col2"> <span class="keyword"> Insight软 </span> 件更新。报告软件更新也存储在此处。 </td> 
  </tr> 
 </tbody> 
</table>

## 启动{#section-ef7408e8fae64454b326ec07453d4628}后创建的目录和文件

以下列出的目录是在注册[!DNL Insight Server]后创建的，并首次运行：

<table id="table_89CC9F3E568044C8A0072BF0A6EDCCEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 目录 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 省/州 </td> 
   <td colname="col2"> 处理由<span class="keyword"> Insight Server </span>生成的信息。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 临时 </td> 
   <td colname="col2"> <p>在重新处理和操作过程中由<span class="keyword"> Insight Server </span>使用的临时文件的位置。 每个物理驱动器通常有一个文件（默认情况下名为<span class="filepath"> temp.db </span>）。 </p> <p> <span class="keyword"> 必须将 </span> Insight Server配置为写入此目录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 跟踪 </td> 
   <td colname="col2"> 记录和事件有关<span class="keyword"> Insight Server </span>的数据。 对故障排除很有用。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 用户 </td> 
   <td colname="col2"> 已命名(<span class="keyword"> Insight </span>)用户，可访问服务器上的用户档案。 当用户首次通过<span class="keyword"> Insight </span>访问<span class="keyword"> Insight Server </span>时，将在目录Users\中为每个已授权的指定用户创建一个目录。 每个指定用户的目录包含与用户在该<span class="keyword"> Insight Server </span>上访问的所有用户档案以及其本地地址文件相对应的目录。 </td> 
  </tr> 
 </tbody> 
</table>
