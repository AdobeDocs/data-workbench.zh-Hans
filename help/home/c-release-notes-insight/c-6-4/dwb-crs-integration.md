---
description: 客户记录服务 (CRS) 导出功能允许您将 Data Workbench 数据导出到 Adobe Analytics 核心服务，以便与 Analytics 的其他功能（包括“报告与分析”）相集成。
title: 导出到 Analytics 核心服务
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 导出到 Analytics 核心服务{#exporting-to-analytics-core-services}

客户记录服务 (CRS) 导出功能允许您将 Data Workbench 数据导出到 Adobe Analytics 核心服务，以便与 Analytics 的其他功能（包括“报告与分析”）相集成。

>[!NOTE]
>
>要使CRS导出功能正常工作，访客的Analytics ID必须基于Experience Cloud ID服务(ECID)。 虽然可以在Data Workbench中为访客填充ECID，但如果客户端在宽限期内或未用ECID替换访客的Cookie，则CRS导出将不适用于该访客。 有关详细信息，请参 [阅识别访客](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) 和 [ID服务宽限期](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html)。

From a **Detail Table** (right-click **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** in a workspace), you can set attribute values and the variables required to integrate with Analytics&#39; Reports &amp; Analytics (using Adobe Pipeline Services).

1. **右键单击表格标题，然后单击“新的客户记录服务”。**

   ![](assets/6_4_CRS.png)

1. **命名导出文件并进行保存。**

   这将会打开导出文件编辑窗口。

1. **打开****“查询”>“CRS 配置”**。
1. **右键单击“CRS 属性”>“新增”。**
1. **输入**“***CRS 属性*****”参数**。

   打开新条目并且输入或验证导出文件中“*CRS 属性*”部分中的值：

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>属性名称</b> </p> </td> 
      <td colname="col2">显示在“<i>报告与分析</i>”中的“<i>客户属性</i>”变量的名称。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>属性类型</b> </td> 
      <td colname="col2"> <p>该参数接受<i>整型</i>、<i>字符串类型</i>的值。 </p> <p>注意：如果在 Analytics 中<b>未</b>订阅属性： <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">则会使用 Analytics 支持的任何有效的属性类型（对于该版本，仅限<i>字符串</i>类型和<i>整型</i>）来创建属性。 </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">如果输入了无效的属性类型，则会收到一个错误消息，声明无法订阅 Analytics。 </li> 
      </ul> </p> <p>如果<b>已经</b>在 Analytics 中订阅了属性： </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">确保为已经订阅的属性输入正确的属性类型。 </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">如果您为属性输入了错误的类型，则其行为将取决于 Analytics 对属性类型的处理。 </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>字段名称</b> </p> </td> 
      <td colname="col2">从中选择属性值的维度或量度的名称。 <p>注意：位于“<i><b>CRS 属性</b></i>”下方的<i>字段名称</i>应当与<b><i>输出字段</i> &gt; <i>字段名称</i></b>（这是基于选定的属性而自动填充）相同。如果“<i>字段名称</i>”无效，则无法运行导出。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 右键单击 **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**。
1. 请输入 **[!UICONTROL Report Suite ID]**.

   打开新条目并且输入或验证导出文件中“*报表包*”部分中的值：

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>报表包</b> </td> 
      <td colname="col2">ID of the report suite in <i>Reports &amp; Analytics</i> identifying the <i>Customer Attribute</i> variables being exported. <p> <p>注意：尽管“<i>报告与分析</i>”允许您添加多个报表包，但是 Data Workbench 6.4 只能导出一个在“<i>索引 0</i>”中标识的报表包。 <p>在此字段中输入的报表包值是报表包ID（而非报表包的名称）。 </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 输入ECID字段参数。

   **ECID字段**:您的配置文件中代表Adobe Experience Cloud ID的维的名称。 这是必填字段，输入的任何无效维值都不会导出。

1. （可选）填写访客ID字段参数。

   **访客ID字段**:如果用户希望在其数据中为访客发送任何其他自定义ID，则在此输入表示自定义访客ID的维名称。 这是一个可选字段，可以保留为空。
