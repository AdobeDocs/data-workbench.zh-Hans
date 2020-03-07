---
description: 本节介绍不同类型的维以及如何在DWB中设置维。
title: 维设置
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# 维设置{#dimension-setup}

本节介绍不同类型的维以及如何在DWB中设置维。

## 什么是维度 {#section-dac631943df24706827cedc6f0641543}

在最基本的级别，维是可以细分数据集中数据的类别。

最佳实践：可以为数据架构中的维提供任何名称。 本课程中使用和解释的维度名称被视为最佳实践。 维可以以不同的方式命名。 当您接触到其他数据集时，您将开始看到数据集中的差异。 了解维的用途（而非其名称）非常重要。 例如，无论它叫作“访客”、“客户”、“人”、“消费者”还是“用户”，了解这些术语通常用于引用用于收集单个人信息的最高级别的可计数维度非常重要。

有关完整信息，请参阅《数据 [集配置指南](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html) 》。

## DWB中的维类型 {#section-a4fbb7bf2bde44528ac0f94a96465862}

Data Workbench中有两种类型的维：扩展维和派生维。

扩展维是从“原始”数据文件中的字段创建的。 扩展维用于对“原始”数据分类并指定数据之间的关系。 扩展维由Data Workbench Architects创建。

派生维度由用户“在客户端”使用现有扩展维定义处理数据集后创建。 例如，根据现有URI维，用户可以选择创建派生的页面名称维，该维显示更易用的页面名称来代替给定的URI。 所有维都由元素或项目组成，这些元素或项目已分类（分组）到一起以构成维。 以下是三维及其元素。

许多派生维度是自动创建的，用来派生不同类型的可视化。例如，当用户构建站点或进程映射时，DWB服务器会创建前缀维。 其他维度（如报表时间维度）由配置文件的“维度”目录中的文件定义。

>[!NOTE]
>
>任何给定维度中显示的元素将仅反映那些在记录中存在的值，这些记录已被选择加载到数据集中。 例如，如果没有“5月12日”的数据，那么该月将不会显示在“月”维中。

## 扩展维度 {#section-5fc51fa539034941a30a2df606f7d727}

扩展维度的类型

**1)可数维**

在最高级别是可计数的维。 可数维有两个主要功能。 首先，它们是要计算其元素的维。 换句话说，可数可回答如下问题：

* “有多少访客访问过您的主页？”
* “有多少次访问来自google.com?”

因此，计数通常用作创建度量的基本构建块。

可数表的第二个主要功能是它们构成了数据集架构结构的骨干。 您的数据架构和所有其他维将被组织到某个可计数的下方，并归其所有。 换句话说，如果我们将维视为“类别”，那么可计数就是我们将这些“类别”组织成组的方式。

当维在可数维下进行分组时，它们据说位于可数维的“级别”。 例如，“电子邮件地址”可以位于访客级别，“浏览器”可以位于访问级别。 “父项”和“子项”指可计数与其下分组的维之间的关系。 例如，访客是电子邮件地址的“父项”。 相反，电子邮件地址是访客的“子级”。

**2)简单尺寸**

所有尺寸中最常见的是简单尺寸。 简单维与父可数维具有一对多关系，通常用于可视化，因此您可以查看其元素。 这意味着可计数维对于简单维可以有一个值，但简单维可以属于一个或多个可计数。 例如，客户的名称为“John”-该客户只能有一个名字，但是，许多其他客户的名字可以是“John;”。 作为另一个示例，只有一个浏览器（如Firefox）可用于对网站的任何特定访问，但该浏览器可用于许多不同的访问。

如果可计维回答“多少？”，则简单维回答“哪些？”。 使用上述可计数维部分中使用的示例；页面名称是简单的维。 使用表和简单的维度“页面名称”，我们可以回答如下问题：

* “哪个页面的查看次数最多？”
* “在所有购物车页面中，哪个页面的访问次数最多？”

**3)多对多维度**

多对多维与父可计数维具有多对多关系。 例如，如果名为“外部搜索词”的维在“访问”级别；给定外部搜索词可用于一次或多次访问，而给定的访问可能包括一个或多个外部搜索词。 因此，外部搜索词是多对多维度。

**4)数字维度**

数字维是具有数值的简单维的类型。 数字维度通常创建为用于度量。 数字维的示例包括“收入”、“订单”和“件数”。 在上例中，“客户订单”是数字维。
**5)非正规维** “非正规”维是与父可数维具有一对一关系的维。 非正规维度通常与标识数据等基数较高（许多独特元素）的维一起使用。 例如，访客只能有一个用户ID，而用户ID只能属于一个访客。 因此，这是一对一关系，可以是非正规维。

例如，Geometrixx Web用户ID是客户级别的非正规维度。 由于它是非正规的，因此它与其父维度具有一对一关系，这意味着每个Web用户ID有一个客户，每个客户只有一个Web用户ID。 因此，“客户”量度只能对于Geometrixx Web用户ID的每个元素为“1”。

**6)时间维度**

时间维允许您基于指定的时间戳字段创建一组周期或绝对本地时间维。 时间维度的示例包括“天”、“小时”、“周”和“小时（天）”。 在上面的示例中，“每日小时”表显示在几天的不同时间内收到的访问次数和页面查看次数。

>[!NOTE]
>
>用于显示格式的%转义与标准C库strftime相同 **。

## 定义扩展维度 {#section-38ee124ec74b43fb95f13194a9582b97}

定义扩展维的步骤：

1. 在处理数据集配置文件时，打开配置文件管理器，然后单击数据集以显示其内容。
1. 打开您要在其中定义扩展维度的 Transformation.cfg 文件或转换数据集包含文件。
1. 右键单击“转换”，然后单击“新增”>“ `<Extended dimension type>`”。
1. 为扩展维度输入相应信息。有关转换类型的描述及其参数的信息，请参阅以下各节：

   * [可计数维度](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [简单维度](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [多对多维度](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [数值维度](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [非正规维度](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [时间维度](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. 对于您定义的任何扩展维度，可以向 Comments（备注）参数中添加一个或多个备注行以进一步描述维度，也可以添加有关其用法的说明。To add a comment, right-click the *Comments* label and click* Add new > Comment Line*.

1. 在配置文件中定义扩展维度后，将文件保存在本地，并将其保存到DWB服务器上的数据集配置文件中。

## 隐藏扩展维度 {#section-02339fb51658418eabc10186cd5957d7}

可隐藏扩展维，以便它们不会显示在DWB的维菜单中。 要隐藏维，请在维定义中将“隐藏”属性设置为“True”。
