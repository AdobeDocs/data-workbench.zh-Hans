---
description: 随Insight Server一起安装的文件列表以及注册后显示的文件，并首次运行。
solution: Insight
title: Insight Server目录结构
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insight Server目录结构{#insight-server-directory-structure}

随Insight Server一起安装的文件列表以及注册后显示的文件，并首次运行。

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
   <td colname="col2"> <span class="keyword"> Insight Server配 </span> 置文件，指定访问组列表。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> 用于与 <span class="keyword"> Insight Server通信的地址 </span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 审计 </td> 
   <td colname="col2"> 每日访问日志，其中包含与Insight Server所有尝试连接相关的 <span class="keyword"> 详细信息 </span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 宾 </td> 
   <td colname="col2"> <span class="keyword"> Insight Server可执 </span> 行程序文件。 </td> 
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
   <td colname="col2"> <span class="keyword"> Insight Server组 </span> 件配置文件，用于处 <span class="keyword"> 理 </span> Insight Server群集中的Insight Server <span class="keyword"></span> 。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 包含详细事件状态消息（包括错误消息）的每日事件日志。 Insight Server捕获并记录的 <span class="keyword"> 事件也 </span> 会显示在Windows事件查看器中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日志 </td> 
   <td colname="col2"> <p>传感器生 <span class="wintitle"> 成的 </span>日志文件。 </p> <p>“日志”是默认的日志记录目录，但可能已在communications.cfg文件中指定 <span class="filepath"> 了替代目 </span> 录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代码 </td> 
   <td colname="col2"> 查找文件，如自动机和搜索引擎列表。 <span class="keyword"> Insight Server必须 </span> 将所有查找文件加载到内存中。 组件配置文件中引用的所有查找文件的总大小加上开销(例如， <span class="filepath"></span> FlatFileLookup文件的每行12字节)不得超过在加载所有其他软件应用程序后可用的物理或虚拟内存。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 配置文件 </td> 
   <td colname="col2"> <p>与每个配置文件（配置文件、工作区和可视化文件）相关的文件。 配置文件由数据集中的数据填充。 数据集包括事件数据（“日志数据”）;这些数据可以由安装的传感器 <span class="wintitle"> 捕 </span>获，由网络信标或页面标签传输，或从数据仓库输入。 <span class="keyword"> 有权 </span> 访问给定配置文件的Insight用户可以使用该配置文件的一组已处理数据以及在该配置文件中定义的工作区和可视化。 </p> <p>工作区是系统管理或分析的工作区。 工作区可包含多个界面，其中显示了有关系统性能的不同详细信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 软件 </td> 
   <td colname="col2"> <span class="keyword"> Insight软 </span> 件更新。 报告软件更新也存储在此处。 </td> 
  </tr> 
 </tbody> 
</table>

## Directories and Files Created after Startup {#section-ef7408e8fae64454b326ec07453d4628}

以下列出的目录在注册后 [!DNL Insight Server] 创建并首次运行：

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
   <td colname="col2"> 处理由 <span class="keyword"> Insight Server生成的信 </span>息。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 临时 </td> 
   <td colname="col2"> <p>重新处理和操作过程中 <span class="keyword"> Insight Server使用的 </span> 临时文件的位置。 每个物理驱动器通常有一个 <span class="filepath"> 文件(默 </span> 认名为temp.db)。 </p> <p> <span class="keyword"> 必须将Insight </span> Server配置为写入此目录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 描摹 </td> 
   <td colname="col2"> 记录有关 <span class="keyword"> Insight Server的日志和事件数 </span>据。 用于疑难解答。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 用户 </td> 
   <td colname="col2"> 有权访问服 <span class="keyword"> 务器 </span>上的配置文件的已命名(Insight)用户。 当用户首次通过Insight访问 <span class="keyword"> Insight Server时，将在目录“用户”中为每个授权的指定用户创建 </span> 一个 <span class="keyword"> 目录 </span>。 每个指定用户的目录包含与用户在该 <span class="keyword"> Insight Server上访问的所有配置文件以及其本地 </span> 地址文件相对应的目录。 </td> 
  </tr> 
 </tbody> 
</table>

