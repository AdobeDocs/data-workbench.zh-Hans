---
description: 您可以为查找文件中指定的维度元素或特定数量的维度元素动态生成报表，例如为最高订购数为10的用户生成报表。
title: 动态生成报表
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
exl-id: c14d93cd-212d-44a1-aff9-652e5c4fbda0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 1%

---

# 动态生成报表{#dynamically-generating-reports}

您可以为查找文件中指定的维度元素或特定数量的维度元素动态生成报表，例如为最高订购数为10的用户生成报表。

>[!NOTE]
>
>Adobe不鼓励创建用于每天（或更频繁）生成报告的动态报告集。 如果配置报表具有大型或复杂的查询，动态报表生成可能会占用大量资源。

* [查找文件Dimension元素报表](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [热门Dimension元素报表](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## 查找文件Dimension元素报表{#section-a5e8f38af06c42b4bfddec4bafbf03d6}

要配置报表集以动态生成和（可选）分发查找文件中指定维度元素的报表，请在[!DNL Report.cfg]文件中指定以下参数：

* [!DNL Dimension Name]
* [!DNL Lookup File]

有关这些参数的详细说明，请参阅[Report.cfg参数](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

**使用查找文件创建动态报表集**

1. 为给定维度创建两列查找文件。 此文件必须包含两个制表符分隔的列，不含标题行。

   * 列1应包含维元素的列表。
   * 第2列应包含报表收件人的电子邮件地址。 第1列中给定元素的报告将发送到第2列中同一行上的电子邮件地址。 您可以输入多个电子邮件地址，方法是用逗号（无空格）分隔它们。

      >[!NOTE]
      >
      >
      >    
      >    
      >    * 如果不能通过电子邮件发送报告，则第2列可为空，但必须存在。
      >    * 此文件可能包含空行。




1. 可选。要启用报表的电子邮件发送，您必须在该特定报表集的[!DNL Report.cfg]文件的[!DNL Mail Report]部分执行以下操作：

   * 在“SMTP服务器”参数中，列表用于通过电子邮件分发报表的相应SMTP服务器。
   * 在“收件人”参数中，列表至少一个电子邮件地址以允许通过电子邮件分发报表。 报告不会通过邮件发送到所列地址 — 您仅设置此参数以允许通过电子邮件发送报告。 这可能是伪地址，但必须采用允许的格式（例如[!DNL jsmith@company.com]）。

1. 将查找文件保存到报表集的文件夹。
1. 打开报表集的[!DNL Report.cfg]文件。
1. 在“Dimension名称”参数中，键入要动态生成报表的维的名称。
1. 在“查找文件”参数中，键入查找文件的位置和名称，查找文件包含您希望在报表中显示的维度元素以及收件人电子邮件地址。
1. 对其他报表集重复这些步骤。

>[!NOTE]
>
>在整个报表集完成之前，不会通过电子邮件将动态报表发送给收件人。

## 热门Dimension元素报表{#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

要配置报表集以动态生成顶级维度元素的报表，请按指定的量度计数，请在[!DNL Report.cfg]文件中指定以下参数：

* 维度名称
* 前N个量度
* 前N值
* （可选）预载查询过滤器

有关这些参数的详细说明，请参阅[Report.cfg参数](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

**为顶层元素创建动态报表集**

1. 打开报表集的[!DNL Report.cfg]文件。
1. 在“Dimension名称”参数中，键入要动态生成报表集的维的名称。
1. 在前N个量度参数中，键入要按哪个维度排序的量度的名称。
1. 在“前N个值”参数中，键入要在报表集中显示的维元素数。
1. （可选）在“预加载查询过滤器”参数中，键入所需过滤器的名称。
1. 对其他报表集重复这些步骤。
1. 有关在报表中使用动态标题可视化的信息，请参阅&#x200B;*《Data Workbench用户指南》*。
