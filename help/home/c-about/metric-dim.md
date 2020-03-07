---
description: 使用分步式向导，创建由量度属性（量度维度）定义的维度。然后测试、预览新建的量度维度，并将其保存在“维度”列表中。
title: 量度维度向导
uuid: 411b2e28-0958-43bb-a853-7de7b3063818
translation-type: tm+mt
source-git-commit: d892186621e7acb9504254496b038efc3e9fd8ec

---


# 量度维度向导{#metric-dim-wizard}

使用分步式向导，创建由量度属性（量度维度）定义的维度。然后测试、预览新建的量度维度，并将其保存在“维度”列表中。

量度维度可将量度转换为新的维度。例如，基于“页面查看次数”和“访客级别”量度的量度维度将为每个访客显示基于总页面查看次数的维度元素。它允许您扩展当前基于维度元素定义的量度，以创建并保存为新的维度。

## 步骤 1：选择维度和量度 {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. 打开“量度维度向导”。

   In a workspace, right-click and select **[UICONTROL Tools]** > **[UICONTROL Create Metric Dim]**.

1. 命名量度维度。

   默认情况下，将基于“级别”和“量度”选项来自动填充“名称”字段。

1. 选择一个维度级别。

   维度级别是包含所有组成元素值的父级维度，可过滤输入并定义一个维度类型。

   维度级别包括：

   * 点进率
   * 点击
   * 产品
   * 访问
   * 访客

1. 选择一个量度。

   选择一个要扩展的预置量度，并将其另存为量度维度。

   ![](assets/6_4_workstation_metricdim_metric.png)

1. （可选）创建量度公式。

   单击选框可输入自定义的量度公式。将显示用于验证表达式的计算后的预览值。

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   您可以添加自己的[量度表达式](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)，或者从其他量度编辑器或可视化中剪切并粘贴。向导中可报告语法错误、公式错误、未定义的过滤器以及其他错误。

1. 单击 **[!UICONTROL Next]**.

## 步骤 2：设置格式和存储段 {#section-5bddf3cd306545d7806a501637f80f77}

1. 为新度量维度选择一种格式。

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   格式可用来定义量度在可视化中打开时的显示方式。这些格式是通过 [printf 标准](http://www.cplusplus.com/reference/cstdio/printf/)选定的，其定义方式如下所示：

   ```
   %[flags][width][.precision][length][specifier]
   % 0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   In the **[!UICONTROL Preview]** field, a value will appear based on the metric and format selected.

1. 添加存储段计数表达式。

   您可以定义一个具有各种范围或存储段的量度维度。This returns subsets of elements based on size, such as [0-4], [5-10],...). 维度级别的元素与范围中含有量度值的元素关联。请参阅[维度表达式的语法](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html)中的存储段表达式说明。

1. Click **[!UICONTROL Preview]** to open table of Metric Dim values before saving.

   ![](assets/6_4_workstation_metricdim_preview.png)

   该表按照量度维度详细介绍了量度值。

1. Click **[!UICONTROL Show in Dimension Menu]** to add the newly created dimension to the **Dimension** tab in the **Finder**.

1. 单击 **[!UICONTROL Next]**.

## 步骤 3：完成并保存 {#section-d9043235b18a425f9de0db668d4b1683}

1. 保存后可选择启动“量度维度编辑器”、图形可视化或表格。

   | 字段 | 描述 |
   |---|---|
   | **[!UICONTROL Launch Metric Dim Editor]** | 打开“量度维度编辑器”。 |
   | **[!UICONTROL Launch Graph]** | 启动表格的 PNG 图形。 |
   | **[!UICONTROL Launch Table]** | 在工作区中启动表格，其中，表格的各列中列出了与选定量度的值相比，新量度维度的值。 |

1. 单击 **[!UICONTROL Finish]** 并保存。

   将会打开一个允许您保存该文件的保存对话框。将会在工作区中打开用于查看值的选定选项。
