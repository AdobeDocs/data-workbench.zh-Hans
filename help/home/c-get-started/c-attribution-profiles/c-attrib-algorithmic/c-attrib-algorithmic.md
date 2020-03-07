---
description: 最适合归因是一种机器学习方法，用于在一个成功转化事件的不同渠道之间分配归因值。Data Workbench 会自动评估每个渠道在一个时间窗口内对成功的贡献，然后根据您的客户的实际交互模式构建归因模型。
title: 最适合归因
uuid: 0c51beb3-8f74-4f8e-9722-0c885140c8ce
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 最适合归因{#best-fit-attribution}

最适合归因是一种机器学习方法，用于在一个成功转化事件的不同渠道之间分配归因值。Data Workbench 会自动评估每个渠道在一个时间窗口内对成功的贡献，然后根据您的客户的实际交互模式构建归因模型。

**[!UICONTROL Best Fit Attribution]** 允许您比较促成成功销售、电子邮件注册或其他绩效指标的交互或接触。 这种归因分析可自动向最重要的接触分配权重，并根据您的数据以及客户对您的市场和内部协议做出的响应，提供每个渠道的归因模型。

![](assets/attrib_windows_5.png)

例如，如果某位客户通过自然搜索访问了您的网站，然后参与了营销活动并注册电子邮件，那么[基于规则的归因](/help/home/c-get-started/c-attribution-profiles/c-rules-attrib/c-rules-attrib.md)会标识第一次接触或最后一次接触，或者使用预设归因模型在所有接触点之间平均分配成功归因。当基于规则的归因由用户定义时，最适合归因会通过一个算法来设置值，该算法将某项转化的可能性计算作为观察到的接触点的函数。

>[!NOTE]
>
>To run **Best Fit Attribution** in Data Workbench, you need to update your server certificate ( [!DNL .pem file]) to support Adobe Analytics Premium. 您还需要向客户端的自定义 **添加**&#x200B;高级[!DNL Profile.cfg]，并从 Adobe ClientCare for Server 和报表服务器中接收新的证书。

## 基本设置 {#section-db597eaee462412ea7280d1426366c61}

See [Build a Best Fit Attribution](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-building.md#concept-fede6fc4f592475fa8b351b1765a522d) for step-by-step instructions.

**设置成功量度**&#x200B;定义表示成功事件的量度。

![](assets/attrib_windows_1.png)

成功量度通常是&#x200B;*订购*，尽管您可以利用 Data Workbench 定义一个与成功窗口相结合的、非常复杂的成功量度。

**设置接触量度**（可选）

识别要跟踪的交互（会导致成功转化），然后设置将会计算归因的接触量度。

>[!NOTE]
>
>只有在您使用触控量度从拖放维度元素中派生渠道量度，而不是使用现有渠道量度时，才需要设置触控量度。

如果您没有针对营销活动或渠道定义的量度，但却拥有表示渠道的维度，则最适合归因可基于接触量度为您自动构建它们。

For example, with the Touch Metric set as *Hits*, and given a dimension called *Media Type* with elements that include *Email*, *Press Release*, *Print Ad*, and *Social Media*, the visualization will generate Channel metrics of the form [!DNL Hits where Media Type = Email] when you drag and drop the element(s) onto the visualization.

![](assets/attrib_windows_2.png)

随后，接触量度会决定归因分数的分配，以识别市场营销交互对成功的影响，从而允许您确定在成功窗口中识别的人群的营销接触。您可以设置&#x200B;*页面查看次数*&#x200B;或&#x200B;*点击量*&#x200B;之类的量度，或使用特定于自身需求的自定义接触量度。

在许多情况下，接触窗口应包含成功窗口，以便评估销售周期中较长的交付周期。

**设置收入量度。**

您可以通过设置合适的收入量度来识别多个接触点间的收入。经指定，模型将显示多个输入渠道间的收入分配。 ![](assets/attrib_windows_6.png)

您可以设置一个具有货币数据类型的收入量度，以便在所有经过定义和分析的顶级接触点间分配成功。此量度可划分最终销售收入，并根据由算法分配的权重进行分配。

**设置成功和接触窗口。**

成功窗口可定义要检查的人群以及成功事件的时段，从而允许您指示在通过工作区选项进行分析时要考虑的时间窗口和人群范围。**成功**&#x200B;窗口可为成功事件定义要检查的时段和人群。**接触**&#x200B;窗口可为导致成功事件的渠道交互指定要检查的历史时段。

>[!NOTE]
>
>仅当您尝试通过将维元素拖动到可视化中来自动构建成功量度时，才需要设置触控量度。

您可以设置日、月、年、或任何可用的时间段，以在销售周期内或针对访问您网站的特定受众，限制您的成功事件和接触事件的评估。创建用于限制归因的窗口，可让您集中分析与您的特定需求相关的时段。

![](assets/attrib_windows_4.png)

在许多情况下，您都需要让接触窗口包含成功窗口，以便您能够根据销售窗口在一段较长的交付周期内扩展您的分析。或者，您还可以跟踪和分析与成功事件无关的接触。

**选择渠道。**

输入渠道时，您有两个选项。

**向渠道添加“接触量度”以及添加“维度元素”**

在许多情况下，您需要按维度元素来划分顶级接触点，以便定义特定的渠道。基于元素值，最适合归因将自动选择顶级执行程序，并根据百分比对它们进行排名，然后在图表可视化中显示它们。

![](assets/attrib_windows_7.png)

通过绘制在您的成功窗口期间交互的访客，并检查接触窗口期间的渠道接触（无论是否导致了成功事件），可构建一个归因模型。

## 按渠道划分 {#section-a30592b84bc84f57bd2b988824e852d4}

输入渠道时，您有两个选项：

* 向渠道添加&#x200B;**接触量度**，然后添加&#x200B;**维度元素**。

   **或**

* 创建可过滤您希望评估的渠道元素的量度。

**选项 1：向渠道添加“接触量度”以及添加“维度元素”**。

这是一个比较简单的方法。“最适合归因”可自动创建量度，以评估归因。In the example below the Touch Metric is ***Hits*** and Channels are: ***Display Campaigns***, ***Email Campaigns***, and ***SEM Campaigns***.

通过这种方法，“最适合归因”可在后台创建一个量度以用于评估渠道中的归因（不过，您看不到自动生成的量度，而且系统不会保存这些量度）。在下面的示例中，创建了三个量度，其中，为三个渠道中的每一个渠道（例如，*显示营销活动*、*电子邮件营销活动*&#x200B;以及 *SEM 营销活动*）都过滤了“点击量”。这是最简单的方法，因为您让“最适合归因”为您创建了量度。

![](assets/attrib_touch_add_dims.png)

**选项 2：创建量度**。

在第二个选项中，您可以通过过滤特定的渠道，为您希望评估的渠道创建并保存量度。下面显示了一个类似量度的示例。

![](assets/attrib_create_metric.png)

接下来，不同于输入渠道的“接触量度”和“维度元素”，您可以单击可视化中的菜单栏，然后选择&#x200B;**输入** > **添加渠道**，接着，请选择您创建的量度。

![](assets/attrib_results_2.png)

请参阅下面第二种方法的示例。您会发现，这两个选项的结果完全相同。
