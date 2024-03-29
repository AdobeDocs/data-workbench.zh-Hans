---
description: 传感器由三个主要组件组成：数据收集器、磁盘队列和数据发送器。
title: 哪些是基本组件
uuid: 32e6e8d9-90ee-4db1-8883-dbdf245df26f
exl-id: aee6a601-590a-43e0-aeeb-42a4522e55c8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 0%

---

# 哪些是基本组件{#what-are-basic-components}

{{eol}}

传感器由三个主要组件组成：数据收集器、磁盘队列和数据发送器。

![](assets/Visual-Sensor.png)

## 数据收集器 {#section-f970eaff30364a3c8106d5ec9c1b5caa}

数据收集器（收集器）是在Web服务器进程中执行的NSAPI、ISAPI、J2EE筛选器Servlet或Apache模块。

它会捕获有关Web服务器处理的每个HTTP请求的原始事件数据，并将该信息存入磁盘队列。 如果在同一台计算机上运行Web服务器的多个实例，则每个实例加载其自己的收集器模块实例；但是，收集器的所有实例都将其事件数据写入同一磁盘队列。

## 磁盘队列 {#section-41aac77ab30e48478d1b31eac288df05}

磁盘队列（队列）是容错的、FIFO（先入先出）内存映射的队列文件，它缓冲传感器收集的原始事件数据，为安装该数据的Web服务器上收集的事件数据提供临时存储。

为了防止队列在不受约束的情况下扩展（从而消耗所有可用磁盘空间），队列将保留在固定大小的文件中，这意味着队列仅保存给定容量的事件数据。 安装传感器时，队列文件的大小在传感器配置文件txlogd.conf的QueueSize参数中配置。 有关txlogd.conf参数的信息，请参阅传感器Txlogd.conf文件参数。

一旦建立，文件的物理长度就不会增长或收缩。 收集器只是将新事件数据存入队列，并且发送器从队列中提取事件。 如果收集器到达文件的结尾，它将停止写入队列文件。

通常，发送器会像收集器存放事件一样快速地从队列中提取事件。 但是，如果发送器与Insight Server之间的连接缓慢或不可用，则队列可以填充未发送的事件。 在这种情况下，收集器停止收集数据，直到发送器拉下队列。 有关Web服务器在此期间处理的请求的信息将永久丢失。

**确定队列大小**

在安装传感器之前，必须确定队列需要多大。 要防止永久数据丢失，请务必创建一个足够大的队列，以容纳在与Insight Server的连接可能中断的最长时间（即在活动高峰的几天内有足够的存储）期间可能累积的事件数。 必须将队列配置为保存足够的事件数据，以便系统管理员有时间恢复目标Insight Server的网络可访问性，或者修复或替换Insight Server，而不会丢失任何数据。 如果传感器失败，并且无法使用有效且可访问的队列文件来保存事件数据，则后续数据将丢失。

>[!NOTE]
>
>传感器运行的每台计算机的管理员必须了解本地队列文件的独特性质，以确保他们不会将其视为可删除、存档或压缩的普通日志文件。

Adobe建议将队列配置为至少保存安装传感器的服务器生成的10(10)个事件数据峰值天。 即，从去年任何高峰日的事件数据量中，将其乘以十。

本建议假定：

* 贵公司的信息技术团队正在按照本指南的“管理传感器”中详细描述的方式监控每个传感器，并且每天至少进行一次监控。 如果情况不同，则应适当延长此期限。
* 贵公司的信息技术团队能够在72小时内恢复网络无障碍性，或更换或修复任何已安装的Insight Server。 如果情况不同，则应适当延长此期限。
* 传感器的配置保持不变。
* 没有外部事件（例如，大型营销活动）会导致Web服务器生成的事件数据量显着增加。

您选择的队列大小主要取决于根据贵公司关于响应时间和周末/假日系统管理的惯例和策略所需的系统监控级别。 由于队列大小越大越好，因此Adobe建议贵公司尽量增大队列。

>[!NOTE]
>
>队列文件大小越大，性能就越好。

有关调整队列大小的进一步建议，请联系Adobe咨询服务。

## 数据发送器 {#section-2dc03d37d73b4cc6bdd5af6b346350d4}

发送器是与Web服务器在同一台计算机上执行的独立进程（例如，基于UNIX的计算机上的守护程序或Windows计算机上的服务）。

发送器从磁盘队列中读取事件数据，对其进行压缩，然后通过HTTP/S将其发送到您指定的Insight Server，并在其中进行处理和存储 **.vsl** 文件。
