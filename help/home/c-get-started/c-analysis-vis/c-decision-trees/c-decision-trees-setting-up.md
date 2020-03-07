---
description: 通过识别正类用例并添加量度和维度输入的方式来设置决策树，以评估数据和了解决策树。
title: 构建决策树
uuid: 5790d322-5460-444d-95d8-a06696f9a55f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 构建决策树{#building-a-decision-tree}

通过识别正类用例并添加量度和维度输入的方式来设置决策树，以评估数据和了解决策树。

请按照这些步骤构建决策树。

1. 打开新工作区。

   打开一个新工作区后，您需要单击&#x200B;**添加** > **临时解锁**。

1. To open the Decision Tree Builder, right-click **[!UICONTROL Visualization]** > **Predictive Analytics** > **Classification** > **Decision Tree Builder**.

1. 设置&#x200B;**正类用例**。

   您可以为决策树定义正类用例，方法是在“查找器”中选择维度，或在表格中选择维度元素，也可以在“设计过滤器”中设计一个过滤器。实际上，正类用例可以是工作区中多个选项的组合，包括过滤器、维度、元素和 Data Workbench 可视化值的所有类型。

   * **设计和应用过滤器**&#x200B;作为正类用例。Right-click in the workspace and select **[!UICONTROL Tools]** > **[!UICONTROL Filter Editor]** to design and apply a filter.

   * 添加&#x200B;**维度**&#x200B;作为正类用例。In the workspace, right-click and select **Tools** > **Finders** (or select **[!UICONTROL Add]** > **[!UICONTROL Finders]** in the left pane). 在&#x200B;**搜索**&#x200B;字段中输入维度名称，然后选择一个维度。

   * 添加&#x200B;**量度**&#x200B;作为正类用例。右键单击并选择工 **具** >查找器 **，或在左窗格** 中选 **[!UICONTROL Add]****[!UICONTROL Finders]** 择>以打开度量表。 选择一个量度作为正类用例。

   * 添加&#x200B;**维度元素**&#x200B;作为正类用例。Right-click in the workspace and select **[!UICONTROL Table]** to open dimension elements, then select from the dimension elements to set your positive case.

1. 单击 **[!UICONTROL Options]** > **[!UICONTROL Set Positive Case]**.

   此操作将设置正类用例，并且您可以对它进行命名。The name will appear under the **[!UICONTROL Positive Case]** heading in the workspace.

   >[!NOTE]
   >
   >设置正类用例时，决策树将使用当前工作区选择，该选择可以定义为与工作区中当前选择相匹配的访客（或任何顶级可计数的定义，但在大多数情况下为访客）。 一个正类用例的这些元素会合并为一个过滤器（并非针对多个正类用例）。

   Clicking **[!UICONTROL Set Positive Case]** when there is no selection will clear the positive case.

1. (optional) Select **[!UICONTROL Set Population Filters]** to define the visitor population to be classified.

   如果没有应用人群过滤器，培训集会从所有访客（默认为“每个人”）中进行选择。

   >[!NOTE]
   >
   >Click the **[!UICONTROL Show Complex Filter Description]** to view the filtering scripts for the Positive Case and Population Filter.

1. 添加&#x200B;**量度**、**维度**&#x200B;和&#x200B;**维度元素**&#x200B;作为输入。

   您可以从“查找器”面板或各个维度元素的表格以拖放方式选择输入。You can also select from the **[!UICONTROL Metrics]** menu in the toolbar.

   * 添加&#x200B;**量度**&#x200B;作为输入。

      从工具栏中选择量度。按住 **Ctrl** + **Alt** 并将一个或多个量度拖放到决策树生成器。

      该量度会作为一个输入显示在&#x200B;**输入（量度）**&#x200B;列表中，并使用一个唯一的颜色标示。

      ![](assets/decision_tree_add_Metrics_inputs.png)

   * 添加&#x200B;**维度**&#x200B;作为输入。

      在工作区中，右键单击并选择&#x200B;**工具** > **查找器**，然后在&#x200B;**搜索**&#x200B;字段中输入维度名称。按住 **Ctrl** + **Alt**，选择一个维度，并将该维度拖放到决策树生成器。

      该维度将显示在&#x200B;**输入（维度）**&#x200B;列表中，并使用一个唯一的颜色标示。

   * 添加&#x200B;**维度元素**&#x200B;作为输入。

      在工作区中，右键单击并选择一个“维度”表格。选择“维度元素”，按住 **Ctrl** + **Alt**，并将所选元素拖放到决策树生成器。

      维度元素会显示在&#x200B;**输入（元素）**&#x200B;列表中，并使用一个唯一的颜色标示。
   >[!IMPORTANT]
   >
   >最多可以选择14个要评估的输入。 如果添加的输入过多，那么会显示一则错误消息。

1. Select **[!UICONTROL Go]** from the toolbar.

   将根据所选的维度和量度构建决策树。简单量度（例如“购物车加货”）构建速度较快，复杂维度（例如包含多个数据点的“访问持续时间”）构建速度较慢，会在转化时显示完成百分比。然后会对树图进行修剪并打开以供用户交互。维度和量度输入将采用与节点名称相同的颜色标示。

   ![](assets/decision_tree_builder.png)

   如果树已经过修剪，且经过修剪的分支后含有 **True** 或 **False** 预测，则叶节点显示为绿色 (true) 或红色 (false)。

   >[!NOTE]
   >
   >从数据集中提取培训示例，以便树构建器使用。 Data Workbench 使用 80% 的采样来构建树，剩余 20% 用来评估树模型的准确度。

1. 使用验证准确性 **[!UICONTROL Confusion Matrix]**。

   Click **[!UICONTROL Options]** > **[!UICONTROL Confusion Matrix]** to view the Accuracy, Recall, Precision and F-Score values. 越接近 100%，分数越高。

   混淆矩阵使用值的组合提供了模型的四项准确度：

   * 实际正值 (AP)
   * 预测正值 (PP)
   * 实际负值 (AN)
   * 预测负值 (PN)
   >[!TIP]
   >
   >这些数字通过应用所保留的20%测试数据的结果评分模型获得，该模型已被称为真答案。 如果得分高于 50%，则预测为正类用例（与定义的过滤器匹配）。准确度 = (TP + TN)/(TP + FP + TN + FN)，取消 = TP / (TP + FN)，精度 = TP / (TP + FP)。

1. **了解决策树**。

   生成决策树以后，您可以查看预测路径，并识别符合定义条件的所有访客。树会根据位置和颜色标示识别每个分支的输入分割。例如，如果您选择“反向链接域”节点，指向该分割的节点会按颜色标示列在树的左侧。

   您可以选择叶节点以选择决策树的分支（规则集）。

   对于此示例：如果访问持续时间小于 1，没有营销活动，至少有一个页面查看，没有电子邮件注册，则至少有一次访问。满足条件并下订单的推测结果为 **94.73**%。

   ![](assets/decision_tree_explore.png)

   **决策树交互**：您可以选择树上的多个节点：使用标准的 **Ctrl - 单击**&#x200B;进行添加，或 **Shift - 单击**&#x200B;进行删除。

   **颜色标示的节点**：节点的颜色与 Data Workbench 分配的输入维度和量度的颜色匹配。

   已修剪分支上叶级别的节点以亮绿色和红色标示，预测该节点为 True 或 False。

   | ![](assets/decision_tree_node_true.png) 亮绿色 | 表示该节点等于 true，满足所有条件。 |
   |---|---|
   | ![](assets/decision_tree_node_false.png) 亮红色 | 表示该节点等于 false，并非满足所有条件。 |

1. **保存决策树**。

   您可以将决策树保存为不同的格式：

   ![](assets/decison_tree_save.png)

   * 预测标记语言 (**PMML**)，它是基于 XML 的文件格式，被应用程序用于描述和交换决策树模型。
   * **文本**，它显示简单列和行，其中包含 true 或 false、百分数、成员数和输入值。
   * **维度**&#x200B;以及与预测结果元素对应的分支。

