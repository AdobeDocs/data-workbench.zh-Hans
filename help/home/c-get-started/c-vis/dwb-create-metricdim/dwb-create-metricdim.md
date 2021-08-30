---
description: 使用量度维度向导创建新量度维度。
title: 量度维度向导
uuid: 77b9bc8e-7625-4fef-9de4-f113f9b2debd
exl-id: 109fbefc-5608-493d-aec9-8337f21eaa70
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 90%

---

# 量度维度向导{#metric-dim-wizard}

使用量度维度向导创建新量度维度。

量度维度可将量度转化为新维度。例如，基于“页面查看次数”和“访客级别”量度的量度维度将为每个访客显示基于总页面查看次数的维度元素。它允许您扩展当前基于维度元素定义的量度，以创建并保存为新的维度。

## 步骤1:选择维度和量度 {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. **打开“量度维度向导”**。

   在工作区中，右键单击鼠标，然后选择&#x200B;**工具** > **创建量度维度**。

1. **命名量度维度**。

   默认情况下，将基于“级别”和“量度”选项来自动填充“名称”字段。

1. **选择一个维度级别。**&#x200B;维度级别是包含所有组成元素值的父级维度，可过滤输入并定义一个维度类型。

   维度级别包括：

   * 点进率
   * 点击
   * 产品
   * 访问
   * 访客

1. **选择一个量度**。

   选择一个要扩展的预置量度，并将其另存为量度维度。

   ![](assets/6_4_workstation_metricdim_metric.png)

1. （可选）**创建量度公式**。

   单击选框可输入自定义的量度公式。将显示用于验证表达式的计算后的预览值。

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   您可以添加自己的[量度表达式](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)，或者从其他量度编辑器或可视化中剪切并粘贴。向导中可报告语法错误、公式错误、未定义的过滤器以及其他错误。

1. 单击&#x200B;**下一步**。

## 步骤2:格式和设置存储段 {#section-5bddf3cd306545d7806a501637f80f77}

您可以选择量度格式，并设置维度表达式的存储段值。

1. 选择新量度维度的&#x200B;**格式**。

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   格式可用来定义量度在可视化中打开时的显示方式。这些格式是通过 [printf 标准](http://www.cplusplus.com/reference/cstdio/printf/)选定的，其定义方式如下所示：

   ```
   %[flags][width][.precision][length][specifier]
   %
   0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   在&#x200B;**预览**&#x200B;字段中，值的显示情况取决于量度和选择的格式。

1. 添加&#x200B;**存储段计数**&#x200B;表达式。

   您可以定义一个具有各种范围或存储段的量度维度。这会根据大小返回元素的子集，如[0-4]、[5-10],...)。 维度级别的元素与范围中含有量度值的元素关联。请参阅[维度表达式的语法](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html)中的存储段表达式说明。

1. 在保存前单击&#x200B;**预览**&#x200B;可打开量度维度值表。

   ![](assets/6_4_workstation_metricdim_preview.png)

   该表按照量度维度详细介绍了量度值。

1. 单击&#x200B;**在维度菜单中显示**，可将新创建的维度添加到&#x200B;**查找器**&#x200B;中的&#x200B;**维度**&#x200B;选项卡。
1. 单击&#x200B;**下一步**。

## 步骤3:完成并保存 {#section-d9043235b18a425f9de0db668d4b1683}

1. 保存后可选择启动“量度维度编辑器”、图形可视化或表格。

   | 字段 | 描述 |
   |---|---|
   | 启动量度维度编辑器 | 打开“量度维度编辑器”。 |
   | 启动图形 | 启动表格的 PNG 图形。 |
   | 启动表格 | 在工作区中启动表格，其中，表格的各列中列出了与选定量度的值相比，新量度维度的值。 |

1. 单击&#x200B;**完成**&#x200B;并保存。

   将会打开一个允许您保存该文件的保存对话框。将会在工作区中打开用于查看值的选定选项。
