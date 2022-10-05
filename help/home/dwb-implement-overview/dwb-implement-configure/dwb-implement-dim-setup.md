---
description: 本节介绍不同类型的Dimension以及如何在DWB中设置它们。
title: 维度设置
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
exl-id: 04afd773-e938-49f7-83c9-1d706a6dc525
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 11%

---

# 维度设置{#dimension-setup}

{{eol}}

本节介绍不同类型的Dimension以及如何在DWB中设置它们。

## 什么是Dimension {#section-dac631943df24706827cedc6f0641543}

在最基本的级别，维度是数据集中的数据可划分到的类别。

最佳实践：Dimension架构中的数据可以提供任何名称。 本课程中使用和说明的Dimension名称被视为最佳实践。 Dimension的名称可以不同。 随着您接触到其他数据集，您会开始看到数据集中的差异。 了解维度的用途而不是其名称非常重要。 例如，无论它叫作“访客”、“客户”、“人员”、“消费者”还是“用户”，请务必了解这些术语通常用于指代用于收集有关单个人员信息的最高级别可计数维度。

有关完整信息，请参阅 [数据集配置](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-dataset-constr.html) 的双曲余切值。

## DWB中的Dimension类型 {#section-a4fbb7bf2bde44528ac0f94a96465862}

Data Workbench中有两种类型的维度：扩展Dimension和派生Dimension。

扩展Dimension是从“原始”数据文件的字段创建的。 扩展维度用于对“原始”数据进行分类，并指定数据之间存在的关系。 扩展维度由Data Workbench架构师创建。

派生Dimension由用户“在客户端”上使用现有的扩展维度定义处理数据集后创建。 例如，根据现有的URI维度，用户可以选择创建派生的“页面名称”维度，该维度显示更易用的页面名称来代替给定的URI。 所有维度都由已分类（分组）以形成维度的元素或项目组成。 以下是三个维度及其元素。

许多派生维度是自动创建的，用来派生不同类型的可视化。例如，当用户构建网站或流程图时，DWB服务器会创建前缀维度。 其他维度（如报表时间维度）由配置文件的“维度”目录中的文件定义。

>[!NOTE]
>
>任何给定维度中显示的元素将仅反映那些存在于选定要加载到数据集中的记录中的值。 例如，如果没有“12年5月”的数据，则该月份将不会显示在“月”维度中。

## 扩展维度 {#section-5fc51fa539034941a30a2df606f7d727}

扩展维度的类型

**1)可计数Dimension**

最高级别是可计数维度。 可计数维提供两个主要函数。 首先，它们是要对其元素进行计数的维度。 换言之，可计数器会回答如下问题：

* “有多少访客访问了您的主页？”
* “有多少次访问来自google.com？”

因此，计数通常用作创建量度的基本基本构建块。

可计数的第二项主要功能是它们构成数据集架构结构的骨干。 您的数据架构和所有其他维度将组织在下分组，并属于可计数的。 换句话说，如果我们将维度视为“类别”，那么可计数就是我们将这些“类别”组织成组的方式。

在可计数维度下对维度进行分组时，这些维度据说位于可计数维度的“级别”。 例如，“电子邮件地址”可以位于访客级别，“浏览器”位于访问级别。 “父项”和“子项”是指可计数维度与其下面分组的维度之间的关系。 例如，“访客”是电子邮件地址的“父项”。 相反，电子邮件地址是访客的“子级”。

**2)简单Dimension**

所有维中最常见的是简单维。 简单维度与父可计数维度具有一对多关系，通常用于可视化，以便您查看其元素。 这表示可计数维度对于简单维度可以具有一个值，但简单维度可以属于一个或多个可计数维度。 例如，客户的名称为“John” — 该客户只能有一个名字，但是，许多其他客户的名字可以为“John；”。 作为另一个示例，只能将一个浏览器（如Firefox）用于对网站的任何特定访问，但该浏览器可用于许多不同的访问。

如果可计数维度回答“多少？”，则简单维度回答“哪些维度？”。 使用上述可计数维度部分中使用的相同示例；“页面名称”是一个简单的维度。 通过使用表和简单维度“页面名称”，我们可以回答以下问题：

* “哪个页面的页面查看次数最多？”
* “在所有购物车页面中，哪个页面的访问次数最多？”

**3)多对多Dimension**

多对多维度与父可计数维度具有多对多关系。 例如，如果名为“外部搜索词”的维度位于访问级别；给定外部搜索词可用于一个或多个访问，并且给定的访问可能包含一个或多个外部搜索词。 因此，外部搜索词是一个多对多维度。

**4)数字Dimension**

数值维度是一种具有数值的简单维度类型。 数值维度通常创建为用于量度。 数值维度的示例包括“收入”、“订单数”和“件数”。 在以上示例中，“客户订单”是一个数字维度。
**5)非正规Dimension** 非正规维度是与父可计数维度具有一对一关系的维度。 非正规维度通常与基数较高的维度（许多唯一元素）一起使用，如标识数据。 例如，访客只能有一个用户ID，而用户ID只能属于一个访客。 因此，这是一对一关系，可以是非正规维度。

例如，GeometrixxWeb用户ID是客户级别的非正规维度。 由于它是非正规的，因此它与其父维度之间存在一对一的关系，这意味着每个Web用户ID都有一个客户，而每个客户只有一个Web用户ID。 因此，“客户”量度对于GeometrixxWeb用户ID的每个元素只能为“1”。

**6)时间Dimension**

时间维度允许您根据您指定的时间戳字段创建一组周期性或绝对本地时间维度。 时间维度的示例包括“日”、“小时”、“周”和“小时”。 在以上示例中，“每日时间”表显示在一天的不同时间内收到的访问和页面查看次数。

>[!NOTE]
>
>用于显示格式的%转义与标准C库相同 *strftime*.

## 定义扩展维度 {#section-38ee124ec74b43fb95f13194a9582b97}

定义扩展Dimension的步骤：

1. 在处理数据集配置文件时，打开配置文件管理器，然后单击数据集以显示其内容。
1. 打开您要在其中定义扩展维度的 Transformation.cfg 文件或转换数据集包含文件。
1. 右键单击转换，然后单击新增> `<Extended dimension type>`.
1. 为扩展维度输入相应信息。有关转换类型的描述及其参数的信息，请参阅以下各节：

   * [可计数维度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [简单维度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [多对多维度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [数值维度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [非正规维度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [时间维度](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. 对于您定义的任何扩展维度，可以向 Comments（备注）参数中添加一个或多个备注行以进一步描述维度，也可以添加有关其用法的说明。要添加评论，请右键单击 *评论* 标签，然后单击*新建>注释行*。

1. 在配置文件中定义扩展维度后，将文件保存在本地，然后将其保存到DWB服务器上的数据集配置文件中。

## 隐藏扩展维度 {#section-02339fb51658418eabc10186cd5957d7}

可以隐藏扩展Dimension，以便它们不会显示在DWB的Dimension菜单中。 要隐藏维度，请在维度定义中将Hidden属性设置为“True”。
