---
description: AppendURI 转换提供了一种向默认值中添加信息的方法，该默认值来自用于构建数据集的日志条目。
title: AppendURI
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
exl-id: 0d5901c0-bd13-4499-8e26-44839aeb7413
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 84%

---

# AppendURI{#appenduri}

AppendURI 转换提供了一种向默认值中添加信息的方法，该默认值来自用于构建数据集的日志条目。

该转换将名称-值对放在用于创建 URI 维度的内部字段末尾。名称-值对是使用 Query String Key（查询字符串键）参数作为名称，使用标识的 Input（输入）参数值作为对值构建的。[!DNL AppendURI]命令会添加任何相应的？ 和和符号，用于将名称 — 值对与[!DNL URI]主干以及之前可能已应用于URI的任何[!DNL AppendURI]操作分开。

[!DNL AppendURI]转换仅在[!DNL Transformation.cfg]文件或[!DNL Transformation Dataset Include]文件中定义时才起作用。

| 参数 | 描述 | 默认 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| 评论 | 可选。有关转换的说明。 |  |
| 条件 | 应用此转换的条件。 |  |
| 默认 | 在满足条件但输入值不可用时所使用的默认值。 |  |
| Input（输入） | 其值附加到 URI 后面的字段名称。 |  |
| Query String Key（查询字符串键） | 在创建要附加到后面的名称-值对时使用的名称。 |  |

假定使用传统的模型-视图-控制器方法构建了一个网站。在此类系统中，通常有一个网页作为进入系统的访问点。对于这样的网站，可视化系统中的流量模式毫无意义，并且不能提供对访客使用情况和流量情况的分析。例如，假定网站通过以下形式的 URI 传递所有 Web 请求：

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

modelview ASP 页面接收所有流量并基于查询中 id 字段的值确定其操作。默认情况下，URI 维度将包含单个条目：

* [!DNL modelview.asp]

这将导致毫无意义地映射通过网站的流量，因为所有流量都通过单个 URI 传递。若要解决这一特定情况并对网站的基本结构提供信息更丰富的视图，可使用 [!DNL AppendURI] 将一些唯一的名称-值对从 cs-uri-query 字段移到用于可视化的 URI 维度。下面所示的转换提供了此类转换的详细信息：

![](assets/cfg_TransformationType_AppendURI.png)

在此示例中，系统使用两个页面处理所有请求：[!DNL modelview.asp] 和 [!DNL xmlmodelview.asp]。一个页面用于浏览器流量，另一个页面用于系统到系统的 XML 通信。应用程序服务器进程使用 cs-uri-query 的 id 名称确定要采取的操作。因此，可以从 id 字段提取值并将其附加到 URI 后面。结果是一个 URI 集合，其中包含一系列反映网站访客流量的变体。在此，[!DNL String Match]条件通过搜索cs-uri-stem字段以找到两个感兴趣的网页并忽略所有其他网页来确定应用转换的日志条目。 输入（名称-值对的值）是 cs-uri-query(id) 的结果，即“login”。如 Query String Key（查询字符串键）参数中所指定的，要在后面附加的名称是“id”。因此，对于我们示例的传入cs-uri值，[!DNL URI]维度使用的生成URI是[!DNL /modelview.asp&id=login]。
