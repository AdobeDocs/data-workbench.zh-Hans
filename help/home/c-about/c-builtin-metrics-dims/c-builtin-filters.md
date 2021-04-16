---
description: 用户档案过滤器限制数据集中可用数据的范围。
title: 内置配置文件过滤器
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
exl-id: bb167487-415d-44a8-9a0a-9a76d90ba5c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 1%

---

# 内置配置文件过滤器{#built-in-profile-filters}

用户档案过滤器限制数据集中可用数据的范围。

除了可以在创建数据集之前或期间应用的日志处理和转换过滤器外，还提供了其他用户档案过滤器，它们会影响可从数据集中进行选择的数据的范围。 本节仅介绍后一种类型的特殊过滤器。

创建用户档案集后，用户可使用以下过滤器:

* 数据子设置筛选器
* 中断的会话筛选器

>[!NOTE]
>
>可通过在用户档案的过滤器目录中显示其他过滤器来创建和应用它们。

## 数据子集{#section-0defb44315d94254ab6e629ec3d6f420}

通过允许您仅选择您感兴趣的数据的维度元素，数据子集充当数据过滤器。

创建数据子集可减少计算准确答案所需的时间。 如果您指定的数据子集足够小，Data Workbench可以从Insight Server检索所有需要的数据，并快速、准确地回答有关该子集的问题。 如果您知道，例如，从特定推荐人分析一天的数据或会话需要几个小时，则此功能特别有用。

用户可以自己创建数据子集，也可以访问在继承或工作用户档案中定义的数据子集。 当用户创建数据集的子集（通过在Insight中选择所需数据，然后在工作区中右键单击并单击“数据”>“子集”）时，将在“用户用户档案”目录的“过滤器”文件夹中创建Data Subset.filter文件。 此过滤器定义您选择的数据子集，并保存该子集供将来使用。

>[!NOTE]
>
>您可以创建多个数据子集，并可以切换这些子集以视图数据的不同部分。 当您要视图所有数据时，请记住关闭“数据子设置”。 否则，您的量度值将不能代表数据集中的所有数据。

## 断开的会话筛选器{#section-1608e97da6464b11aea27cbb7f3160e4}

中断会话筛选器是一个量度公式，可以轻松修改以满足任何筛选要求。 在默认的“站点”用户档案中，“中断会话过滤器”配置为包括所有具有设置为1的“访问标志”的访客。 值1表示存在该访客的跟踪Cookie。

以下是Site用户档案发行包中由Adobe提供的默认Broken Session Filter.filter文件的文本。

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

默认情况下，工作区将“断开的会话”过滤器应用于其选择和基准，并可通过在工作区中右键单击并单击“数据”>“断开的会话过滤器”来切换。

即使未为当前工作区启用Broken_Session_Filter，也可以在筛选器表达式中将Broken_Session_Filter引用。 有关其他信息，请参见[过滤器表达式](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers)。
