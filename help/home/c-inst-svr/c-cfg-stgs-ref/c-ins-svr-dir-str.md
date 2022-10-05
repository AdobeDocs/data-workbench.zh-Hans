---
description: 随Insight Server一起安装的文件列表以及在注册后存在的文件，并首次运行。
title: Insight Server 目录结构
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---

# Insight Server 目录结构{#insight-server-directory-structure}

{{eol}}

随Insight Server一起安装的文件列表以及在注册后存在的文件，并首次运行。

## 安装程序包中包含的文件 {#section-daec17dab3e34c3c9e1ef65842cb91f1}

以下目录包含在 [!DNL Insight Server] 安装包：

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
   <td colname="col2"> <span class="keyword"> Insight Server </span> 配置文件，指定访问组列表。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> 用于与通信的地址 <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 审核 </td> 
   <td colname="col2"> 每日访问日志，其中包含与的所有尝试连接有关的详细信息 <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 宾 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> 可执行程序文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificates </td> 
   <td colname="col2"> SSL数字证书。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 组件 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> 组件配置文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 用于处理服务器的组件 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> 组件配置文件用于处理 <span class="keyword"> Insight Server </span> 在 <span class="keyword"> Insight Server </span> 群集。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 活动 </td> 
   <td colname="col2"> 每日事件日志，其中包含详细的事件状态消息，包括错误消息。 捕获和记录的事件 <span class="keyword"> Insight Server </span> 也会在Windows事件查看器中显示。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日志 </td> 
   <td colname="col2"> <p>生成的日志文件 <span class="wintitle"> 传感器 </span>(s)。 </p> <p>“Logs”是默认的日志记录目录，但可能已在 <span class="filepath"> communications.cfg </span> 文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 查找 </td> 
   <td colname="col2"> 查找文件，如自动机和搜索引擎列表。 <span class="keyword"> Insight Server </span> 必须将所有查找文件加载到内存中。 组件配置文件中引用的所有查找文件的总大小，外加开销(例如，每行12个字节 <span class="filepath"> FlatFileLookup </span> 文件)，不得超过所有其他软件应用程序加载后可用的可用物理或虚拟内存。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 配置文件 </td> 
   <td colname="col2"> <p>与每个配置文件相关的文件（配置、工作区和可视化文件）。 用户档案由数据集中的数据填充。 数据集包括事件数据（“日志数据”）；这种数据可通过安装来捕获 <span class="wintitle"> 传感器 </span>、由网络信标或页面标记传输，或从data warehouse输入。 <span class="keyword"> Insight </span> 有权访问给定配置文件的用户可以使用该配置文件的一组已处理数据，以及该配置文件中定义的工作区和可视化图表。 </p> <p>工作区是用于系统管理或分析的工作区。 工作区可以包含多个界面，其中显示了有关系统性能的不同详细信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 软件 </td> 
   <td colname="col2"> <span class="keyword"> Insight </span> 软件更新。 此处还存储了报表软件更新。 </td> 
  </tr> 
 </tbody> 
</table>

## 启动后创建的目录和文件 {#section-ef7408e8fae64454b326ec07453d4628}

下面列出的目录在 [!DNL Insight Server] 首次注册并运行：

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
   <td colname="col2"> 处理信息 <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 临时 </td> 
   <td colname="col2"> <p>使用的临时文件的位置 <span class="keyword"> Insight Server </span> 在重新处理和操作期间。 通常有一个文件(名为 <span class="filepath"> temp.db </span> 默认)。 </p> <p> <span class="keyword"> Insight Server </span> 必须配置为写入此目录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 跟踪 </td> 
   <td colname="col2"> 日志和事件数据关于 <span class="keyword"> Insight Server </span>. 对于疑难解答非常有用。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 用户 </td> 
   <td colname="col2"> 已命名( <span class="keyword"> Insight </span>)用户。 当用户首次访问时，将在目录Users\中为每个已授权的指定用户创建一个目录 <span class="keyword"> Insight Server </span> 通过 <span class="keyword"> Insight </span>. 每个指定用户的目录包含对应于用户在该页面上访问的所有配置文件的目录 <span class="keyword"> Insight Server </span> 以及本地地址文件。 </td> 
  </tr> 
 </tbody> 
</table>
