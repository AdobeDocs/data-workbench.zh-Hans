---
description: Data Workbench安装包中包含的文件。
title: 安装程序包中包含的文件
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安装程序包中包含的文件{#files-included-in-the-installation-package}

Data Workbench安装包中包含的文件。

Insight包中包含以下目录。

## Program Files {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

工作站可执行文件 (**[!DNL Insight.exe]**) 和支持文件默认安装到此文件夹中。

```
C:\Program Files\Adobe\Adobe Analytics\Data Workbench
```

<table id="table_56BAC85184A04E7680FBB4B36DE73285"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 目录 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span> </b> </td> 
   <td colname="col2"> Data Workbench客户端可执行文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="filepath">insight.ini</span></b> </td> 
   <td colname="col2"> 设置语言和 <span class="filepath">Appdata</span> 文件夹的路径。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span> </b> </td> 
   <td colname="col2"> <p>Data Workbench 现在支持使用输入法编辑器 (IME) 作为辅助文本输入程序，以便使用浮动文本框从键盘输入国际字符。Data Workbench 默认将支持英语，但是也允许您加载其他文件以支持国际语言，例如虚拟中文键盘（拼音 IME）。 </p> <p>客户端应用程序需要一个新的词典文件 (<span class="filepath">Insight.zbin</span>) 才能支持 IME。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> 卸载工作站并删除文件的可执行文件。 </td> 
  </tr> 
 </tbody> 
</table>

## AppData 文件 {#section-afddeedf8d29451f996fa46b2dfe932c}

数据文件（**[!DNL Insight.cfg]**、配置文件、证书、跟踪日志和用户文件）默认保存到以下位置：

```
<filepath>
  C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
</filepath>
```

<table id="table_DBA4DBB54C57409C8EC116C686A08560"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 目录 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span> </b> </td> 
   <td colname="col2"> Data Workbench配置文件。 定义Data Workbench在其中运行的参数。 See <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> Configuring the Connection to Insight Server </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Base </span> </b> </td> 
   <td colname="col2"> <p>包含Data Workbench的程序文件。 </p> <p> <p>注意：您不应该删除或更改这些文件中的任何文件。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Certificates </span> </b> </td> 
   <td colname="col2"> Contains the certificate file, <span class="filepath"> trust_ca_cert.pem </span>, and the named user digital certificate for Data Workbench. See <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Downloading and Installing the Digital Certificate </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> 配置 </span> </b> </td> 
   <td colname="col2"> 包含用于工作站配置的文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Geography </span></b> </td> 
   <td colname="col2"> 用于地理可视化图像呈现的文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Trace </span></b> </td> 
   <td colname="col2"> 从工作站生成的日志文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Profiles </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>、<i>预测分析</i>和其他配置文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> <b><span class="filepath">Software/Insight</span></b> 文件夹中安装其他客户端计算机的安装向导。 </td> 
  </tr> 
 </tbody> 
</table>

