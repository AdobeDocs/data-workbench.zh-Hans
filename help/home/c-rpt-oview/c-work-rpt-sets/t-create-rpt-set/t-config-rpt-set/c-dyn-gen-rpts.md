---
description: 您可以为您在查找文件中指定的维度元素或特定数量的维度元素（例如，对于最高顺序计数为10的用户）动态生成报表。
title: 动态生成报表
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
exl-id: c14d93cd-212d-44a1-aff9-652e5c4fbda0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 1%

---

# 动态生成报表{#dynamically-generating-reports}

{{eol}}

您可以为您在查找文件中指定的维度元素或特定数量的维度元素（例如，对于最高顺序计数为10的用户）动态生成报表。

>[!NOTE]
>
>Adobe建议不要创建动态报表集，以便每天（或更频繁地）生成报表。 如果您使用大型或复杂查询配置报表，则生成动态报表可能会占用大量资源。

* [查找文件Dimension元素报表](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [热门Dimension元素报表](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## 查找文件Dimension元素报表 {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

要将报表集配置为动态生成和（可选）分发查找文件中指定维度元素的报表，请在 [!DNL Report.cfg] 文件：

* [!DNL Dimension Name]
* [!DNL Lookup File]

有关这些参数的详细描述，请参阅 [Report.cfg参数](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**使用查找文件创建动态报告集**

1. 为给定维度创建两列查找文件。 此文件必须包含两个以制表符分隔的列，且不带标题行。

   * 列1应包含维度元素列表。
   * 列2应包含报表收件人的电子邮件地址。 第1列中给定元素的报表将发送到第2列中同一行的电子邮件地址。 您可以输入多个电子邮件地址，方法是使用逗号分隔这些地址（无空格）。

      >[!NOTE]
      >
      >
      >    
      >    
      >    * 如果不通过电子邮件发送报表，则第2列可为空，但必须存在。
      >    * 此文件可能包含空行。


1. 可选。要启用报表的电子邮件发送，您必须在 [!DNL Mail Report] 部分 [!DNL Report.cfg] 文件：

   * 在“SMTP服务器”参数中，列出用于通过电子邮件分发报表的相应SMTP服务器。
   * 在“收件人”参数中，至少列出一个电子邮件地址，以允许通过电子邮件分发报表。 报表不会邮寄到列出的地址，您只需设置此参数，即可通过电子邮件发送报表。 这可能是一个伪地址，但必须是允许的格式(例如， [!DNL jsmith@company.com])。

1. 将查找文件保存到报表集的文件夹中。
1. 打开 [!DNL Report.cfg] 文件。
1. 在Dimension名称参数中，键入要动态生成报表的维度名称。
1. 在“查找文件”参数中，键入查找文件的位置和名称，该查找文件包含您希望在报表中使用的维度元素以及收件人电子邮件地址。
1. 对其他报表集重复这些步骤。

>[!NOTE]
>
>在完成整个报表集后，才会通过电子邮件将动态报表发送给收件人。

## 热门Dimension元素报表 {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

要配置报表集以动态生成排名最前的维度元素的报表（按指定的量度计数），请在 [!DNL Report.cfg] 文件：

* 维度名称
* 前N个量度
* 前N值
* （可选）预加载查询过滤器

有关这些参数的详细描述，请参阅 [Report.cfg参数](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**为热门元素创建动态报表集**

1. 打开报表集的 [!DNL Report.cfg] 文件。
1. 在Dimension名称参数中，键入要动态生成报表集的维度名称。
1. 在前N个量度参数中，键入要按其对维度进行排序的量度名称。
1. 在前N个值参数中，键入您希望在报表集中使用的维度元素数量。
1. （可选）在“预加载查询过滤器”参数中，键入所需过滤器的名称。
1. 对其他报表集重复这些步骤。
1. 有关在报表中使用动态标题可视化的信息，请参阅 *Data Workbench用户指南*.
