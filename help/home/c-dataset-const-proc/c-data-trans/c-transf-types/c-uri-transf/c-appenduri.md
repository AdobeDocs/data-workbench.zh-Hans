---
description: AppendURI 转换提供了一种向默认值中添加信息的方法，该默认值来自用于构建数据集的日志条目。
solution: Analytics
title: AppendURI
topic: Data workbench
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# AppendURI{#appenduri}

AppendURI 转换提供了一种向默认值中添加信息的方法，该默认值来自用于构建数据集的日志条目。

该转换将名称-值对放在用于创建 URI 维度的内部字段末尾。名称-值对是使用 Query String Key（查询字符串键）参数作为名称，使用标识的 Input（输入）参数值作为对值构建的。该命 [!DNL AppendURI] 令可添加任何相应的？ and &amp; symbols necessary to separate the name-value pairs from the [!DNL URI] stem and from any previous [!DNL AppendURI] operations that may have been applied to the URI.

仅当 [!DNL AppendURI] 在文件或文件中定义 [!DNL Transformation.cfg] 时，转换才 [!DNL Transformation Dataset Include] 有效。

| 参数 | 描述 | 默认值 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| Comments（备注） | 可选。有关转换的说明。 |  |
| Condition（条件） | 应用此转换的条件。 |  |
| Default（默认值） | 在满足条件但输入值不可用时所使用的默认值。 |  |
| Input（输入） | 其值附加到 URI 后面的字段名称。 |  |
| Query String Key（查询字符串键） | 在创建要附加到后面的名称-值对时使用的名称。 |  |

假定使用传统的模型-视图-控制器方法构建了一个网站。在此类系统中，通常有一个网页作为进入系统的访问点。对于这样的网站，可视化系统中的流量模式毫无意义，并且不能提供对访客使用情况和流量情况的分析。例如，假定网站通过以下形式的 URI 传递所有 Web 请求：

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

modelview ASP 页面接收所有流量并基于查询中 id 字段的值确定其操作。默认情况下，URI 维度将包含单个条目：

* [!DNL modelview.asp]

这将导致毫无意义地映射通过网站的流量，因为所有流量都通过单个 URI 传递。若要解决这一特定情况并对网站的基本结构提供信息更丰富的视图，可使用 [!DNL AppendURI] 将一些唯一的名称-值对从 cs-uri-query 字段移到用于可视化的 URI 维度。下面所示的转换提供了此类转换的详细信息：

![](assets/cfg_TransformationType_AppendURI.png)

在此示例中，系统使用两个页面处理所有请求：[!DNL modelview.asp] 和 [!DNL xmlmodelview.asp]。一个页面用于浏览器流量，另一个页面用于系统到系统的 XML 通信。应用程序服务器进程使用 cs-uri-query 的 id 名称确定要采取的操作。因此，可以从 id 字段提取值并将其附加到 URI 后面。结果是一个 URI 集合，其中包含一系列反映网站访客流量的变体。Here, a [!DNL String Match] condition determines the log entries to which the transformation is applied by searching the cs-uri-stem field for the two web pages of interest and ignoring all others. 输入（名称-值对的值）是 cs-uri-query(id) 的结果，即“login”。如 Query String Key（查询字符串键）参数中所指定的，要在后面附加的名称是“id”。Thus, for the incoming cs-uri value of our example, the resulting URI used by the [!DNL URI] dimension is [!DNL /modelview.asp&id=login].
