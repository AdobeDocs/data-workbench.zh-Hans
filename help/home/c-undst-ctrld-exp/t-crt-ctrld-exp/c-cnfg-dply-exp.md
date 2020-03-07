---
description: 定义目标、假设和实验详细信息并创建测试内容后，必须配置传感器以部署受控实验。
solution: Insight,Analytics
title: 配置和部署实验
topic: Data workbench
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置和部署实验{#configuring-and-deploying-the-experiment}

定义目标、假设和实验详细信息并创建测试内容后，必须配置传感器以部署受控实验。

## 配置实验配置文件 {#section-037fe7dea9c94aee9cdc354dafdb7c03}

要配置实验，您必须完成Adobe提供的实验配置电子表格(默认 [!DNL TestExperiment.xls] 命名)。 此文件配 [!DNL Sensor] 置为执行实验，是您在修改ExpFile参数中指定的文本文 [件的Excel版本](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

该文件可以包含有关多个实验的信息，这些实验可以在相同或不同的时间运行，并且使用不同的组和百分比，但这些实验不以任何方式相关。

用户将被放置到组中，用于文件中列出的每个实验，该文件配置为当前正在运行。

>[!NOTE]
>
>每个实验都与所有其他实验无关。 您对一个实验所做的更改不会影响任何其他实验，尽管访客可能在多个实验中，但结果彼此不相关。 如果您认为多个实验中的更改之间存在关联，则必须创建一个新实验，以共同测试这些更改。

**配置实验**

应在实验开始前完成此文件，而不要在实验运行时修改信息。

>[!NOTE]
>
>如果实验开始后实验的定义发生变化，任何实验都会立即失效。

1. 如果您对Web或应用程序服务器具有管理员访问权限，请导览至Web群集中 [!DNL Sensor] 任何计算机上的安 [!DNL Sensor] 装文件夹以访问该文 [!DNL TestExperiment.xls] 件。 如果您没有管理员访问权限，请与您的Adobe客户经理联系以请求该 [!DNL TestExperiment.xls] 文件。

1. 打开文 [!DNL TestExperiment.xls] 件（如果需要，可重命名此文件）并填写以下字段：

<table id="table_FDD6AE631C614F97AD7AE8829E53CCAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 实验 </td> 
   <td colname="col2"> <p>实验的描述性名称。 每个实验名称必须是唯一的，并且不能包含空格。 </p> <p>在 <span class="keyword"> Insight中显示实验结果时，会使用实验名称 </span>。 这些名称显示为受控实验尺寸中元素名称的前半部分。 元素名称的后半部分是此文件中“组”字段的组名称。 每个组使用实验名称后跟组名称，以下格式命名： </p> <p><i>EmperityName.Group Name</i> </p> <p>例如： <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 开始 </td> 
   <td colname="col2"> <p>您希望实验开始的日期和时间。 如果不输入值，则实验将在文件部署后立即开始。 </p> <p>格式：MM/DD/YYYY H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">如果将开始和停止时间留空，则实验将无限期地运行。 </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">您可以提前很好地预定义开始和停止时间；因此，您可以根据需要同时配置下一年的所有实验。 </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">启动和停止时间基于Web服务器的系统时间。 如果该时钟因任何原因而改变，您的实验可能会意外地开始或停止。 </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">如果您希望将实验添加为配置文件条目，但不希望该实验在不久的将来运行，则可以使用数字符号“#”注释掉实验信息，或定义过去的开始和停止时间。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop </td> 
   <td colname="col2"> <p>您希望实验结束的日期和时间。 当停止日期和时间发生时， <span class="wintitle"> 传感器将 </span> 停止向测试URI发送标识为测试组的Cookie值，并将所有Cookie发送到控制组URI。 </p> <p>格式：MM/DD/YYYY H:MM </p> <p>请参阅“开始”字段 <span class="wintitle"> 的注 </span> 释。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 群组 </td> 
   <td colname="col2"> <p>实验中每组访客的描述性名称。 组名称不能包含空格。 </p> <p>在 <span class="keyword"> Insight中显示实验结果时，使用组名称 </span>。 有关详细信息，请参阅“实验”字段说明。 </p> <p>可以隐式或显式定义控件组，具体取决于在“百分比”(Percentage)字段中输入的值。 </p> <p> <p>注意： 为了在定义的时间段内达到在统计上有效的试验所需的访客数量，您可能需要降低置信水平或增加时间段。 例如，如果您的时间范围是5天，您的置信度级别为98%，并且您需要的访客数量超过了该时间段内的预期数量，则您需要增加该时间段或降低置信度级别，直到预期的访客数量超过运行统计有效实验所需的数量。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 百分比 </td> 
   <td colname="col2"> <p>要包含在每个定义组中的网站访客百分比。 这些值可以表示为百分比值或小数值。 此外，这两个值必须大于或小于一个。 </p> <p>例如： </p> <p>33.3%和66.7% </p> <p>.99和。01 </p> <p>如果所有组的总和小于100，则未定义的超额将默认为控制组。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 原始URL </td> 
   <td colname="col2"> <p>要重新映射的内容的URI，后跟$。 此值区分大小写。 </p> <p>格式：index.asp$ </p> <p>可以使用URI末尾的美元符号($)指定原始URI，以表示需要与文件名完全匹配。 例如，表达式 <span class="filepath"> /product/product_view.asp$仅 </span> 匹配该精确页面，而 <span class="filepath"> /product匹配 </span><span class="filepath"></span> /product目录中的任何页面，并且可用于重新映射整个子树。 除非ExpPartialMatch参数设置为“on”，否则实验将忽略未在文件名末尾指定$字符的原始URL条目。有关此参数的详细信息，请参 <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> 阅修改ExpPartialMatch参数（可选） </a>。 </p> <p>受控实验功能忽略附加到URI主干的任何查询字符串。 例如，页面 </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982 </span> 不是有效的URI，但页 <span class="filepath"> 面/product/product_view.asp </span> 是有效的URI。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重新映射的URL </td> 
   <td colname="col2"> <p>替代内容的URI。 </p> <p>格式：index2.asp </p> <p>请参阅“原始URL”字段的说明。 </p> </td> 
  </tr> 
 </tbody> 
</table>

以下是已填写电子表格的示 [!DNL TextExperiment.xls] 例：

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>请勿修改电子表格中的列位置。

此示例表明，“New_Homepage”实验从2006年6月1日开始，于2006年6月30日结束，包含一个包含50%访客的控制组和一个包含50%访客的测试组，这些访客查看一个URI的不同内容。

>[!NOTE]
>
>尽管上面的示例文件定义了明确的控制组，但是不必显式地定义控制组— 实验会自动创建控制组。 如果实验中所有组的百分比之和小于100%，则向不属于显式组之一的用户分配隐式控制组。

1. 要插入注释以提供有关特定实验的其他信息，请以数字符号(#)开头的单元格，然后按注释进行操作。 注释可以插入文件中的任意位置。
1. 在实验配置电子表格中完成变量后，保存更改，然后使用配置文件的ExpFile参数中指定的名称以制表符分隔的文本格式( [!DNL *.txt])保存 [!DNL Sensor] 文件。 请参 [阅修改ExpFile参数](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

   以下是实验配置文本文件的示例：

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >由于此文件中需要使用选项卡，因此请勿手工编辑实验配置文本文件。 如果需要更改文件，请在实验配置Excel文件中进行更改，然后将文件重新保存为制表符分隔的文本文件。

如果已定义“开始”和“停止”时间，则没有理由从实验配置文件中删除实验。 将所有实验都列在实验配置文件中实际上是一种记录每个实验的定义的好方法。

## 部署配置文件和测试内容 {#section-34ff29649f584b93bc6129b75084b37c}

必须将实验配置文件部署到Web群集中运行并提供实验 [!DNL Sensor] 中涉及的页面的每台计算机。 您可以使用手动过程或现有内容管理系统执行此操作。

**部署测试内容**

* 在运行服务实验中涉及的页面的 [!DNL Sensor] 每个应用程序或Web服务器上，使用您现有的发布过程将测试内容部署到相应的位置。

   例如，如果要将测试组页面发布到 [!DNL index2.asp] 网站( [!DNL mysite.com])的测试文件夹，您应将文件发布到 [!DNL www.mysite.com/test]。

   >[!NOTE]
   >
   >请勿直接从网站上的页面链接到任何测试文件。 这样做会使测试结果和索引得分无效。

**部署实验**

* 在运行服务实验中涉及的页面的 [!DNL Sensor] 每个应用程序或Web服务器上，将实验配置文本文件放在配置文件的ExpFile参数中指定的目 [!DNL Sensor] 录中。 请参 [阅修改ExpFile参数](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

[!DNL Sensor] 根据您在文件中定义的百分比随机选择每个组的网站访客，并根据需要为他们提供测试或控制组内容。
