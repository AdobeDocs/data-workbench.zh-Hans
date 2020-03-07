---
description: 借助具备新式采样和可视化功能的回归树选项，对决策树进行评估。
title: 决策树的回归树选项
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Regression tree option for decision tree{#regression-tree-option-for-decision-tree}

借助具备新式采样和可视化功能的回归树选项，对决策树进行评估。

在决策树可视化中右键单击并选择“选项”> **回归树**，借助回归树选项对决策树进行评估。

**更新后的决策树生成器**：引入新算法用于构建[决策树](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html)。它可以处理更多的常规数据，并提供信息更丰富的可视化，进而提高预测精度。

**改进后的数据采样模型**：采用已更新且具备适应性的采样方法，有助于决策树和倾向得分获得更加准确的结果。

![](assets/CART-RegressionTreeOptions.jpg)

绿色和红色分别表示真或假。色彩饱和度 - 例如深红色和浅红色 - 用于表示可能性。例如，深红色的节点为假的可能性非常高，而浅红色的节点为假的可能性较低。深绿色的节点为真的可能性非常高。

各个决策树的分支宽度各异，用于表示相应分支的流量水平。

在决策树可视化中，右键单击并选择“选项”> **回归树**。选择后，就会提供其他设置：

<table id="table_39E025A3E0B549B4BEDCE0D30A499211"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 回归设置 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>每个功能限用一次</b> </p> </td> 
   <td colname="col2"> <p>选择此选项便不能再多次使用各个功能（类似于原始决策树）- 所以，如果您有五个输入，则树不能多于五层，而且树的结构类似于决策树（但是更加复杂）。此选项通过每个功能限用一次（类似于原始决策树）的限制，能够加快树的构建。默认设置为使用此功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>回归树层数设置</b> </p> </td> 
   <td colname="col2"> <p>此选项能够控制回归树的复杂度。您可能需要根据自己的数据构建一棵<i>优良</i>的树（结构复杂，节点较多），从而实现更加有意义的树分类。如果您拥有大量数据，则可以选用相对<i>粗略</i>的树（复杂度较低，树节点较少）。 </p> <p> <p>注意：<i>默认设置为典型</i>。某些极端情况下，<i>典型</i>设置的效果不及<i>粗略</i>或<i>优良</i>设置，但是可以提供更好的数据研究视角。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>优良</i>：复杂度最高、报告粒度级别最高、分支最多的树。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>典型</i>：粒度级别和分支数量居平均水平。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>粗略</i>：复杂度最低、定义的类别最少、分支最少的树。 </p> </td> 
  </tr> 
 </tbody> 
</table>

