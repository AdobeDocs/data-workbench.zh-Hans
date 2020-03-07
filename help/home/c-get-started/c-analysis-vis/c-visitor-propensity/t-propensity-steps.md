---
description: 按照以下步骤使用“倾向评分”可视化。
solution: Analytics
title: 设置倾向评分
topic: Data workbench
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 设置倾向评分{#setting-up-propensity-scoring}

按照以下步骤使用“倾向评分”可视化。

1. 打开新工作区，然后单 **[!UICONTROL Add]** 击> **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**。

   ![](assets/propensity_visualization.png)

1. Set the **[!UICONTROL Target]** (the dependent variable).

   通过选择以下项设置因变量：

* **维度元素**:在工作区中右键单击并选择 **[!UICONTROL Table]**。 然后选择一个维度元素作为您的因变量。

   或者

* **[!UICONTROL Filter Editor]**。单击 **[!UICONTROL Add]** > **[!UICONTROL Visualization]** >以 **[!UICONTROL Filter Editor]** 打开过滤器编辑器可视化。

   ![](assets/propensity_visualization_filter_editor.png)

   After selecting a Dimension element or Filter as the dependent variable, click **[!UICONTROL Set Target]**, enter a name to describe the dependent variable. Then click **[!UICONTROL OK]** (and make sure the filter box is highlighted) to set the Target.

   ![](assets/propensity_visualization_setTarget.png)

   您为目标提供的名称即是因变量，将显示在左侧窗格中。
1. 添加独立变量。

   使用量度或维度元素添加独立变量。

   ![](assets/propensity_visualization_metrics.png)

* **量度**。From the Propensity Scoring toolbar, select a metric from the **[!UICONTROL Metrics]** menu.

* **维度元素**:在工作区中右键单击并选择 **[!UICONTROL Table]**。 Select one or more Dimension elements and drag to the left column under **[!UICONTROL Independent Variables]** or to the **[!UICONTROL Element]** box using the `<Ctrl>` + `<Alt>` keys.

1. 已设置 **[!UICONTROL Training Filter]**. You can define the set of visitors that you want to score by clicking **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** from the Propensity Scoring toolbar. 这将提供一组数据子集（专门由要进行评分的访客所构建）。例如，在上月进行过访问的访客，在澳大利亚居住的访客，或查看过特定产品的访客。

   默认过滤器是， **[!UICONTROL Train on Everyone]**&#x200B;但您可以通过在表中激活或使用 **[!UICONTROL Dimension Elements]** 构建过滤器来更改它 **[!UICONTROL Filter Editor]**。

   After selecting a Dimension element or building a filter and while activated, click **Options** > **Set Training Filter**, enter a name to describe the filter, and then click **[!UICONTROL OK]**.
1. Once you have identified all your inputs, press **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   多次传递数据，即开始评分过程。随后，它将以条形图的形式，透过一条百分比线显示结果。
1. 保存倾向得分。

   从 6.1 版开始，在使用“保存倾向得分”时为您提供了一个选项：

* 维度
* 维度和量度

   您最终可以保存两个文件：维度和定义的量度。

   >[!NOTE]
   >
   >注意：如果提交“倾向得分”进行处理，您只会得到维度。

   派生的量度是相关的平均得分量度。
1. 检查正确率。

   The system will display **[!UICONTROL Model Complete]** and generate a scoring model when the process is complete.

   Right-clicking on **[!UICONTROL Model Complete]** will identify the accuracy of the scoring model as defined by the system. Values ranging from 0 percent to 100 percent will identify the likelihood of the visitors matching the **[!UICONTROL Target]** variable.

   混淆矩阵提供以下四个计数的组合：实际正值 (AP)、实际负值 (AN)、预测正值 (PP) 和预测负值 (PN)。将生成的评分模型应用于余下 20% 的测试数据（对此我们知道准确答案），可获取这些数值。如果得分高于 50%，则预测为正类情况（与定义的事件匹配）。

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b>正确率</b> </td> 
   <td colname="col2"> 通过识别所有预测中包含的正确预测，来表示模型的正确率。 <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>查全率</b> </td> 
   <td colname="col2"> 识别重新标识评分模型的能力。 <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>查准率</b> </td> 
   <td colname="col2">识别差异级别。 <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Open a [Lift or Gain Chart](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a), or the [Model Viewer](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9).

   右键单击“模型完 **整** ”可视化 **[!UICONTROL Lift Chart]**，然后选 **[!UICONTROL Gain Chart]**&#x200B;择、 **[!UICONTROL Model Viewer.]**
