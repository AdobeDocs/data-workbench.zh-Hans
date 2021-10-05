---
description: 在规划和实施系统之前，确定Data Workbench（以前称为 [!DNL Insight]）服务器组件的最低要求和建议。
title: 服务器系统要求
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# 服务器系统要求{#server-system-requirements}

在规划和实施系统之前，确定Data Workbench服务器组件的最低要求和建议。

## DPU要求{#dpu-requirements}

服务器数据处理单元(DPU)是Data Workbench的主要数据处理组件。 它监听来自Data Workbench的网络连接，从文件服务器单元(FSU)读取原始源数据，并使用大量计算和存储资源。

### 许可容量 {#section-71850e13783443798b3df9eb22cc63dc}

有关许可证容量信息，请参阅&#x200B;*Adobe[!DNL Data Workbench (Insight)]服务协议*&#x200B;中的服务说明。

>[!NOTE]
>
>对于Windows 2012服务器中的&#x200B;*MS System Center端点保护*，需要将这些可执行文件添加到&#x200B;***排除的进程：*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]

>


### DPU系统Recommendations和要求 {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe提供有关满足您业务需求的Data Workbench设计的建议。 但是，以下准则在选择操作系统(OS)和硬件时非常有用，因为DPU软件的优化性质对OS/硬件平台提出了特定要求。

如果单个数据集受单个DPU的容量或速度限制，则可以对其进行聚类。 例如，假定您有三个DPU软件的授权副本，这些副本可一起使用，以更快地运行更大的数据集。 由于数据被平均分割到两台计算机之间，因此数据集的许可容量将乘以三。 此外，每行处理速度比单个DPU快3倍。

为了从您的DPU投资中获得最佳性能，Adobe建议使用下表中描述的以下高性能组件：

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> </th>
   <th colname="col2" class="entry"> 必需 </th>
   <th colname="col3" class="entry"> 建议 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>操作系统 </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td>
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>CPU </p> </td>
   <td colname="col2"> <p>请参阅推荐。 </p> </td>
   <td colname="col3"> 推荐采用英特尔或AMD最新一代4核+处理器。 为获得最佳性能，共8枚；为了在速度和成本之间取得平衡，建议使用4个内核。 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>内存 </p> </td>
   <td colname="col2"> <p>8 GB </p> </td>
   <td colname="col3"> <p>12 GB </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>工作数据存储 </p> </td>
   <td colname="col2"> <p>总逻辑临时存储容量为1 TB。 </p> <p>对磁盘子系统的低延迟访问 </p> </td>
   <td colname="col3"> <p>对于临时存储Adobe，建议执行以下任一操作： </p>
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283">
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">（4到8）*（750GB或更高）SATA硬盘（3.5英寸主轴）。 </li>
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">（6到10）*（300GB或更高）SATA硬盘（2.5英寸主轴） </li>
    </ul> <p>应在JBOD阵列中配置这些参数。 或者，当总磁盘容量超过2TB时，可以使用2磁盘RAID1卷阵列。 例如，将六个磁盘配置为一个3*（2*750GB RAID 1对）。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>系统数据存储 </p> </td>
   <td colname="col2"> <p>此外，Adobe还要求对操作系统、DPU软件和其他系统软件以适中大小(20GB)的高可用性存储。 </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>群集硬件 </p> </td>
   <td colname="col2"> <p>请参阅推荐。 </p> </td>
   <td colname="col3"> <p>使用一组同构的服务器。 在DPU群集中，运行速度最慢的服务器会降低整个数据集的性能。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 群集网络性能 </td>
   <td colname="col2"> 交换千兆位以太网连接或更高连接。 </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

### 备用磁盘子系统 {#section-6f984eabe8074759aa9deaf17e3a68b7}

考虑临时存储的替代磁盘子系统时，请考虑以下因素和准则：

* DPU对高性能磁盘系统的要求异常高，因此设置不充分的磁盘子系统可能会导致性能瓶颈。
* DPU软件在一组JBOD磁盘上执行其自身面向性能的数据条带化。 请勿使用RAID来提高速度。
* Adobe建议DPU为磁盘聚合400 MB/s以上的持续带宽。
* 平均读取大小非常高（2MB以上）。 因此，15K或10K SAS磁盘通常比SATA磁盘性能稍好（或更差），而成本和容量却大大降低。
* 避免使用SAN体系结构。 经验表明，使SAN在所需级别上执行的成本通常是极高的。
* 本地磁盘子系统用作暂存空间 — 不会因HDD故障而永久丢失数据，因此请考虑避免成本高昂、速度较慢、高可用性系统。

### 速度注意事项 {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe无法提供与已配置Data Workbench处理数据的速度有关的担保或表示，因为各种因素会影响数据处理速度，包括但不限于：

* 数据行数
* 数据的维度（列）数
* 自定义处理步骤的数量和复杂性
* 聚类的使用
* 硬件速度

## 文件服务器单元要求{#file-server-unit-requirements}

服务器的文件服务单元(FSU)是Data Workbench的主要数据存储和管理组件。 FSU充当文件服务器，用于将原始源数据发送到DPU，并在适当时协调DPU的聚类。 每个FSU都获得提供源数据的许可，最多可提供五(5)个DPU。

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E">
 <thead>
  <tr>
   <th colname="col1" class="entry"> FSU组件 </th>
   <th colname="col2" class="entry"> 推荐 </th>
   <th colname="col3" class="entry"> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>操作系统、CPU、RAM </p> </td>
   <td colname="col2"> <p>这些要求与DPU的要求相同。 但是，对于FSU，Adobe建议使用最低要求，而不是遵循建议。 </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>磁盘系统 </p> <p>FSU需要高可用、冗余的存储，以用于大量数据。 Adobe将与您一起确定您的确切要求。 </p> </td>
   <td colname="col1"> <p>Adobe建议： </p>
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539">
     <li id="li_F98750D509D640C68885D53FC691ED43">（12个或更多）*（750GB或更高）RAID 5/6配置中的SATA硬盘。 </li>
     <li id="li_3F84F63F9541476987015C27FDE8251B">支持100MB/s+持续带宽的高性能SAN连接。 </li>
    </ul> <p>由于FSU保留原始源数据，因此任何损失都将无法恢复，因此Adobe建议定期备份此数据。 </p> </td>
   <td colname="col2"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>网络性能 </p> </td>
   <td colname="col2"> <p>Adobe要求FSU和DPU之间使用交换千兆位以太网连接。 </p> </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

## 传感器要求{#sensor-requirements}

Data Workbench传感器从Web、应用程序和数据收集服务器收集事件数据，以将其传输到任何服务器。 [!DNL Sensor’s] 该工具可确保始终如一地准确测量Internet渠道中发生的事件。[!DNL Sensor] 支持Web服务器软件和操作系统的多种组合。

### 传感器系统Recommendations {#section-0a981c3a47b644c1a1a56974ba033b9c}

下表介绍了[!DNL Sensor]的系统建议：

<table id="table_A132E06D6B8146C1B199B82464EA0898">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 功能 </th>
   <th colname="col2" class="entry"> 建议 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>磁盘存储器 </p> </td>
   <td colname="col2"> <p>最少512 MB。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>内存 </p> </td>
   <td colname="col2"> <p>HTTP或其主机的其他服务器计算机上的<span class="wintitle">传感器</span>必须有32 MB的RAM。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>网络性能 </p> </td>
   <td colname="col2"> <p>与中继服务器或<span class="keyword"> Data Workbench Server </span>的1 Mbps或更高网络连接。 <span class="wintitle"> 传感 </span> 器消耗的带宽通常比一(1)Mbps要少得多。您的Adobe顾问将帮助您估算日常所需的实际带宽量。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>网络端口和防火墙 </p> </td>
   <td colname="col2"> <p> <span class="wintitle"> 传感 </span> 器使用 <span class="keyword"> HTTPS(通 </span> 常为端口443，但可以配置)或HTTP（通常为端口80，但可以配置）连接到Data Workbench Server。 </p> <p>位于<span class="wintitle">传感器</span>和目标<span class="keyword"> Data Workbench Server </span>或中继服务器之间的防火墙上的相应端口应仅在相应的<span class="wintitle">传感器</span>托管计算机和<span class="keyword"> Data Workbench Server </span>或中继服务器之间打开，然后才开始<span class="wintitle">传感器</span>安装过程。 <span class="wintitle"> 传感 </span> 器与Data Workbench Server或中继器服务器建立单 <span class="keyword"> 向HTTPS </span> 或HTTP连接。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>网络管理系统 </p> </td>
   <td colname="col2"> <p>现有的网络管理系统应监视底层计算机硬件（例如磁盘空间、网络服务）和网络连接以及Windows事件日志或UNIX系统日志的运行状况。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>服务器时间同步 </p> </td>
   <td colname="col2"> <p>确保计算机系统时间在每台承载<span class="wintitle">传感器</span>的计算机上持续同步。 <span class="wintitle">传感器</span>监视的Web服务器应用程序和计算机必须具有同步的系统时间，才能从这些应用程序和计算机收集的事件数据准确。 请参阅操作系统的文档，了解如何持续将系统时间与NTP或其他此类时间同步工具同步的步骤。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>DNS名称用法 </p> </td>
   <td colname="col2"> <p>Adobe建议<span class="wintitle">传感器</span>使用DNS名称（而不是IP地址）来解析<span class="keyword"> Data Workbench Server </span>或中继服务器的网络地址。 当<span class="wintitle">传感器</span>使用DNS名称时，需要配置主机Web服务器的DNS或本地主机文件，以解析<span class="keyword"> Data Workbench Server </span>或中继服务器的名称。 </p> </td>
  </tr>
 </tbody>
</table>

### 支持服务器软件 {#section-d6071706539f49d9a861d87b98e6f382}

下表列出了[!DNL Sensor]支持的最常见组合：

<table id="table_99EA23BBC1A148B49643F4B5E4341C08">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Web服务器软件 </th>
   <th colname="col2" class="entry"> 操作系统 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Apache Server / IBM HTTP Server 2.2 </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2003或更高版本；RedHat Enterprise Linux 6.x或更高版本；Sun Solaris 8.x或更高版本；IBM AIX 5.1x或更高版本。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Apache Server 2.4 </p> </td>
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x或更高版本 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Microsoft IIS </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2003或更高版本 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Java应用程序服务器(Tomcat、JBoss、iPlanet、Weblogic) </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2003或更高版本；RedHat Enterprise Linux 6.x或更高版本；Sun Solaris 8.x或更高版本；IBM AIX 5.1x或更高版本。 </p> </td>
  </tr>
 </tbody>
</table>

对于其他服务器和操作系统组合，请咨询Adobe以了解可用性。 [!DNL Sensor]的所有功能并非在Web/应用程序服务器和操作系统的所有组合中都可用。 有关特定[!DNL Sensor]版本的更多信息，请联系Adobe支持。

## 报表服务器要求{#report-server-requirements}

Data Workbench报表服务器是允许输出计划报表的组件。 输出的报表可以是.PNG图像或.XLS电子表格形式（置于文件系统中），也可以是电子邮件形式。 其硬件要求与[Data Workbench客户端](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=zh-Hans)的要求相同。

[!DNL report server]具有以下要求：

* 访问文件系统以输出数据（网络共享或本地驱动器）。
* 访问已配置的SMTP服务器。
* Microsoft Excel 2003或更高版本安装在[!DNL report]服务器上。 有关其他信息，请参阅[Office服务器端自动化注意事项](https://support.microsoft.com/kb/257757)。

## 网络管理{#network-management}

Adobe建议现有网络管理系统监控Data Workbench平台所依赖的硬件和网络。

此外，Adobe还建议监控FSU和DPU的Windows事件日志，当发生错误时，这些日志会写入。

>[!NOTE]
>
>任何托管日志文件的网络存储系统都需要提供每DPU至少10MB的持续带宽。

## 数据可用性{#data-availability}

服务器DPU处理数据并将其重新处理到新数据集或已刷新的数据集中，这是一种正常且必需的做法。

这可能是由于配置更改、数据源更改、硬件更改、不适当配置、硬件故障、软件故障、电源故障等原因而发生的。 在进行此类处理或重新处理时，所有数据集和系统数据都需要立即可供DPU和FSU组件使用。 如果不遵守此要求，则可能导致系统停机时间过长，而且不必要。

## DPU和FSU网络问题{#dpu-and-fsu-network-issues}

使用DPU和FSU网络时应注意的事项。

* 对于网络日志文件分发，任何托管日志文件的网络存储系统都需要提供每DPU至少10MB的持续带宽。
* DPU、FSU和Data Workbench在端口80或443上通过HTTP或HTTPS双向通信(默认情况下；端口也可以进行配置)。
* Data Workbench[!DNL Sensor(s)]必须能够连接到服务器（单向）。
* 要允许DPU通过SMTP发送警报消息，它必须能够联系配置的SMTP服务器。
* Adobe建议为FSU和DPU指定网络名称（如FSU01.CLIENT.COM），以避免在IP地址发生更改时进行重新配置。
