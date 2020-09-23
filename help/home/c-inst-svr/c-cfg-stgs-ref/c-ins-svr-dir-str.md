---
description: 列表随Insight Server安装的文件以及注册后存在的文件，并首次运行。
solution: Analytics
title: Insight Server 目录结构
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---


# Insight Server 目录结构{#insight-server-directory-structure}

列表随Insight Server安装的文件以及注册后存在的文件，并首次运行。

## 安装程序包中包含的文件 {#section-daec17dab3e34c3c9e1ef65842cb91f1}

安装包中包含以下 [!DNL Insight Server] 目录：

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
   <td colname="col2"> <span class="keyword"> Insight Server配 </span> 置文件，它指定访问组的列表。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> 用于与Insight Server通信 <span class="keyword"> 的地 </span>址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 审核 </td> 
   <td colname="col2"> 每日访问日志，其中包含与所有尝试连接到Insight Server的 <span class="keyword"> 相关的详 </span>细信息。 </td> 
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
   <td colname="col1"> 处理服务器的组件 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server组 </span> 件配置文件，用 <span class="keyword"> 于处理Insight </span> Server群集中 <span class="keyword"> 的Insight </span> Server。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 每日事件日志包含详细的事件状态消息，包括错误消息。 Insight Server捕获和记 <span class="keyword"> 录的事件 </span> 也会在Windows事件查看器中显示。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日志 </td> 
   <td colname="col2"> <p>传感器生 <span class="wintitle"> 成 </span>的日志文件。 </p> <p>“Logs”是默认的日志记录目录，但可能已在communications.cfg文件中指 <span class="filepath"> 定了替代 </span> 目录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代码 </td> 
   <td colname="col2"> 查找文件，如自动机和搜索引擎列表。 <span class="keyword"> Insight Server必须 </span> 将所有查找文件加载到内存中。 组件配置文件中引用的所有查找文件的总大小以及开销（例如，FlatFileLookup文件每行12字节） <span class="filepath"></span> 不得超过加载所有其他软件应用程序后可用的物理或虚拟内存。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 配置文件 </td> 
   <td colname="col2"> <p>与每个用户档案（配置、工作区和可视化文件）相关的文件。 用户档案由数据集中的数据填充。 数据集包括事件数据（“日志数据”）;此类数据可以由安装的传感器 <span class="wintitle"> 捕 </span>获，由网络信标或页面标签传输，或从data warehouse输入。 <span class="keyword"> 具有 </span> 特定用户档案访问权限的Insight用户可以使用该用户档案的已处理数据集以及在该用户档案中定义的工作区和可视化。 </p> <p>工作区是系统管理或分析的工作区。 工作区可包含多个界面，其中显示有关系统性能的不同详细信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 软件 </td> 
   <td colname="col2"> <span class="keyword"> Insight软 </span> 件更新。 报告软件更新也存储在此处。 </td> 
  </tr> 
 </tbody> 
</table>

## Directories and Files Created after Startup {#section-ef7408e8fae64454b326ec07453d4628}

以下列出的目录在注册 [!DNL Insight Server] 后创建并首次运行：

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
   <td colname="col2"> 处理由Insight Server生 <span class="keyword"> 成的信 </span>息。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 临时 </td> 
   <td colname="col2"> <p>重新处理和操作过程中Insight Server <span class="keyword"> 使用的 </span> 临时文件的位置。 每个物理驱动器通常有 <span class="filepath"> 一个文件( </span> 默认名为temp.db)。 </p> <p> <span class="keyword"> 必须将 </span> Insight Server配置为写入此目录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 跟踪 </td> 
   <td colname="col2"> 有关Insight Server的日志 <span class="keyword"> 和事件 </span>数据。 对于疑难解答有用。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 用户 </td> 
   <td colname="col2"> 有权访 <span class="keyword"> 问服 </span>务器上用户档案的已命名(Insight)用户。 当用户首次通过Insight访问Insight Server时，将在目录Users\中为每个已授权的 <span class="keyword"> 指定用户 </span> 创建 <span class="keyword"> 目录 </span>。 每个指定用户的目录包含与用户在该Insight Server上访问的所有用户档案对应的 <span class="keyword"> 目录 </span> 及其本地地址文件。 </td> 
  </tr> 
 </tbody> 
</table>

