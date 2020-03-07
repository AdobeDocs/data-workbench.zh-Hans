---
description: “决策树”菜单包含各项功能，可以设置正类用例、过滤器、叶分配选项、混淆矩阵及其他高级选项。
title: 决策树选项
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 决策树选项{#decision-tree-options}

“决策树”菜单包含各项功能，可以设置正类用例、过滤器、叶分配选项、混淆矩阵及其他高级选项。

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 工具栏按钮 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 开始 </td> 
   <td colname="col2"> 单击以运行决策树算法并显示可视化。此选项处于灰显状态，直到存在输入的情况。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重置 </td> 
   <td colname="col2"> 清除输入和决策树模型并重置流程。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 保存 </td> 
   <td colname="col2"><b>保存决策树</b>。您可以将决策树保存为不同的格式： 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">预测标记语言 (<b>PMML</b>)，它是基于 XML 的文件格式，被应用程序用于描述和交换决策树模型。 </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>文本</b>，它显示简单列和行，其中包含 true 或 false、百分数、成员数和输入值。 </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57"><b>维度</b>以及与预测结果元素对应的分支。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 选项 </td> 
   <td colname="col2"> 请参阅下表了解“选项”菜单。 </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_24D84440D0354C70928E8927624DB255"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> “选项”菜单 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 设置正类用例 </td> 
   <td colname="col2"> 定义当前工作区选项作为模型的正类用例。如果没有选项存在，则清除用例。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 设置人群过滤器 </td> 
   <td colname="col2"> 定义当前工作区选项作为模型的人群过滤器，并从满足此条件的访客中进行选择。默认为“每个人”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 显示复杂过滤器说明 </td> 
   <td colname="col2"> 显示定义的过滤器的说明。单击可查看正类用例和人群过滤器的过滤脚本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隐藏节点 </td> 
   <td colname="col2"> 隐藏只有很少一部分人群的节点。仅当决策树显示时，才会显示此菜单命令。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 混淆矩阵 </td> 
   <td colname="col2"> <p>单击<span class="uicontrol">选项</span> &gt; <span class="uicontrol">混淆矩阵</span>以查看准确度、取消、精度和 F 得分值。越接近 100%，分数越高。 </p> <p>混淆矩阵使用值的组合提供了模型的四项准确度： 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">实际正值 (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">预测正值 (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">实际负值 (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">预测负值 (PN) </li> 
     </ul> </p> <p>提示：这些数字的获取，是通过对保留的 20% 测试数据和已知为正确的答案应用结果评分模型得来。如果得分高于 50%，则预测为正类用例（与定义的过滤器匹配）。准确度 = (TP + TN)/(TP + FP + TN + FN)，取消 = TP / (TP + FN)，精度 = TP / (TP + FP)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 显示图例 </td> 
   <td colname="col2">允许您在决策树中切换图例键开关。<img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />仅当决策树显示时，才会显示此菜单命令。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 高级 </td> 
   <td colname="col2"> 单击可打开“高级”菜单以深入使用决策树。请参阅下表以了解菜单选项。 </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 高级菜单 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 培训集大小 </td> 
   <td colname="col2"> <p>控制用于构建模型的培训集大小。较大的集合需要的培训时间较长，较小的集合需要的时间较短。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 输入正规化 </td> 
   <td colname="col2"> <p> 允许用户指定使用最低-最高还是使用 Z 评分技术来正规化模型中的输入。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMOTE 过采样因子 </td> 
   <td colname="col2"> 当培训采样中正类用例不经常发生（小于 10%）时，使用 SMOTE 可以提供更多采样。此选项允许用户指示使用 SMOTE 多创建多少采样。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 叶类分配阈值 </td> 
   <td colname="col2"> 允许您设置在树构建过程中叶的假定阈值。默认情况下，节点的所有成员必须一致，因为该节点将作为一个叶（修剪阶段前）。 </td> 
  </tr> 
 </tbody> 
</table>

