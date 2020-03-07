---
description: 您可以为查找文件中指定的维元素或特定数量的维元素动态生成报表，例如为最高10个订单计数的用户生成报表。
solution: Analytics
title: 动态生成报告
topic: Data workbench
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 动态生成报告{#dynamically-generating-reports}

您可以为查找文件中指定的维元素或特定数量的维元素动态生成报表，例如为最高10个订单计数的用户生成报表。

>[!NOTE]
>
>Adobe不鼓励创建动态报表集以生成每日（或更频繁）的报表。 如果配置具有大型或复杂查询的报表，动态报表生成可能会占用大量资源。

* [查找文件维元素报表](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [顶级维元素报表](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## 查找文件维元素报表 {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

要将报表集配置为动态生成和（可选）分发查找文件中指定的维元素的报表，请在文件中指定以下参 [!DNL Report.cfg] 数：

* [!DNL Dimension Name]
* [!DNL Lookup File]

有关这些参数的详细说明，请参 [阅Report.cfg参数](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

**使用查找文件创建动态报表集**

1. 为给定维度创建两列查找文件。 此文件必须包含两个制表符分隔的列，不含标题行。

   * 第1列应包含维元素列表。
   * 第2列应包含报告收件人的电子邮件地址。 第1列中给定元素的报告将发送到第2列中同一行的电子邮件地址。 您可以通过用逗号（无空格）分隔多个电子邮件地址来输入它们。

      >[!NOTE]
      >
      >
      >    
      >    
      >    * 如果不通过电子邮件发送报告，则第2列可为空，但必须存在。
      >    * 此文件可能包含空行。




1. 可选。要启用报告的电子邮件发送，您必须在该特定报告集的 [!DNL Mail Report] 文件部分 [!DNL Report.cfg] 中执行以下操作：

   * 在“SMTP服务器”参数中，列出用于通过电子邮件分发报告的相应SMTP服务器。
   * 在“收件人”参数中，列出至少一个电子邮件地址，以便通过电子邮件分发报告。 报告不会通过电子邮件发送到列出的地址——您仅设置此参数以允许通过电子邮件发送报告。 这可以是伪地址，但必须采用允许的格式(例如 [!DNL jsmith@company.com])。

1. 将查找文件保存到报表集的文件夹。
1. 打开报 [!DNL Report.cfg] 告集的文件。
1. 在维名称参数中，键入要动态生成报表的维的名称。
1. 在“查找文件”参数中，键入查找文件的位置和名称，查找文件包含您希望在报表中显示的维元素以及收件人电子邮件地址。
1. 对其他报告集重复这些步骤。

>[!NOTE]
>
>在整个报告集完成之前，动态报告不会通过电子邮件发送给收件人。

## 顶级维元素报表 {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

要配置报表集以动态生成顶级维元素的报表（按指定的度量计数），请在文件中指定以下参 [!DNL Report.cfg] 数：

* 维度名称
* 前N个指标
* 前N个值
* （可选）预载查询筛选器

有关这些参数的详细说明，请参 [阅Report.cfg参数](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

**为顶级元素创建动态报表集**

1. 打开报表集的文 [!DNL Report.cfg] 件。
1. 在维名称参数中，键入要动态生成报表集的维的名称。
1. 在前N个量度参数中，键入要对维排序的量度的名称。
1. 在前N个值参数中，键入要在报表集中显示的维元素数。
1. （可选）在“预加载查询筛选器”参数中，键入所需筛选器的名称。
1. 对其他报告集重复这些步骤。
1. 有关在报表中使用动态标题可视化的信息，请参阅《 *Data Workbench用户指南》*。

