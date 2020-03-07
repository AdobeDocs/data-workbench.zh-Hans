---
description: 标注是向工作区中添加的窗口，目的是引起对特定维度元素的注意，添加方法是通过该元素的虚拟选择创建新的可视化。
solution: Analytics
title: 将标注添加到工作区
topic: Data workbench
uuid: fb3dd74d-da20-40cb-bc96-e56d25003e48
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adding callouts to a workspace{#adding-callouts-to-a-workspace}

标注是向工作区中添加的窗口，目的是引起对特定维度元素的注意，添加方法是通过该元素的虚拟选择创建新的可视化。

Data Workbench提供了一组标准的标注类型。 由于您可以完全自定义实施，因此实施中显示的可用标注类型可能与本指南中所述的内容有所不同。

默认情况下，Data Workbench提供以下标注：

* [批注](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-7b6742160b3f4aed872a09c8c023f90d)
* [空白折线图](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [空白散点图](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [空白表格](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [置信度图例](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-386d1293ddc24a0c9cccb332e20db791)
* [量度图例](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-daa6d372c22246d9827880a9d6e804d8)

>[!NOTE]
>
>标注不起选择的作用（即，它们不影响工作区中的其他可视化），除非您在标注中做出选择。

通过配置在 *安装文件夹的*&#x200B;配置文件名称[!DNL Server]\Context\Callout 文件夹中存储的标注文件，可以添加或编辑标注定义。请参阅 [配置标注](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-callouts.md#concept-f6e91e172f5e4c009245c9c549beb76a)。

## To add an annotation callout to a visualization {#section-7b6742160b3f4aed872a09c8c023f90d}

1. 右键单击要为其创建标注的元素，然后单击 **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Image]** or **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Text]**。 随即会显示一个空白窗口，该窗口具有一个到该元素的可见连接。

   ![](assets/client-call.png)

   要向图表可视化添加标注，您需要右键单击可视化底部（基轴）以打开一个菜单。

   ![](assets/visualization_callout_linegraph.png)

1. 根据您的选择，完成相应的步骤：

   * 对于文本批注，将所需文本键入或粘贴到标注中，然后根据需要设置文本的格式。请参阅[使用文本批注](../../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777)。
   * 对于图像批注，通过复制图像，然后右键单击标注来将所需的图像粘贴到标注中。单击 **[!UICONTROL Paste image]**. See [Working with Image Annotations](../../../home/c-get-started/c-analysis-vis/c-annots/c-image-annots.md#concept-02081ed7d91c4fdcb8fc863f2a51c962).

## To add a blank table, line graph, or scatter plot callout to a visualization {#section-5dcc0504bdb64ed4976f880e2f7b277f}

1. Right-click the element for which you want to create a callout and click **[!UICONTROL Add Callout]** > *&lt;**[!UICONTROL callout type]**>*.

   以下示例显示了一个空白表格标注。

   ![](assets/vis_callout_blank_bar_graph.png)

1. 要选择维，请右键单击并 **[!UICONTROL None]** 单击 **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*。

   >[!NOTE]
   >
   >如果在具有标注的可视化中更改维，则标注将从连接到原始维的元素更改为连接到整个可视化。

## To add a confidence legend callout to a visualization {#section-386d1293ddc24a0c9cccb332e20db791}

1. Right-click the element for which you want to create the callout and click **[!UICONTROL Add Callout]** > **[!UICONTROL Confidence Legend]**.

   ![](assets/vis_callout_confidenceLegend.png)

1. 如果需要，请更改字 [!DNL Metric or Formula] 段。

有关表达式语法规则，请参 [阅查询语言语法](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)。 请参阅 [置信度图例](../../../home/c-get-started/c-analysis-vis/c-legends/c-conf-leg.md#concept-73db81c2c218427786c04068aa778efd)。

## To add a metric legend callout to a visualization {#section-daa6d372c22246d9827880a9d6e804d8}

1. Right-click the element for which you want to create the callout and click **[!UICONTROL Add Callout]** > **[!UICONTROL Metric Legend]**.

   ![](assets/vis_callout_metricLegend.png)

1. 如果需要，向量度图例中添加量度或从中删除量度。

请参阅[量度图例](../../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b)。
