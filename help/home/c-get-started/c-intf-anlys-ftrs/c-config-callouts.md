---
description: 通过使用可视化中特定维度元素的虚拟选择创建新的可视化，标注可以使用户注意某个特定的维度元素。
solution: Analytics
title: 配置标注
topic: Data workbench
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置标注{#configure-a-callout}

通过使用可视化中特定维度元素的虚拟选择创建新的可视化，标注可以使用户注意某个特定的维度元素。

You can add or edit callouts by configuring the callout files stored in a Profiles\*profile name*\Context\Callout folder of the [!DNL Server] installation folder. 使用户注意工作表可视化中特定量度的标注称为量度标注。度量标注文件存储在Profiles\*配置文件名称*\Context\Metric Callout folder中。

有关向可视化添加标注或度量标注的说明，请参 [阅向工作区添加标注](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0)。

**创建新的标注类型**

1. 在任何工作区中创建一个可视化，其中包含您希望以新标注类型显示的数据。例如，如果您要创建表格型标注，则创建一个显示所需量度和维度的表格可视化。
1. Right-click the top border of the callout window and click **[!UICONTROL Save]**.
1. 在窗 [!DNL Save] 口中，单 ![](assets/btn_folder_up.png)击，双击 **[!UICONTROL Context]**，然后双击 **[!UICONTROL Callout]**。 In the [!DNL File Name] field, type a name for the file and click **[!UICONTROL Save]**. 标注文件将保存到User\*工作配置文件名称*\Context\Callout folder。

   >[!NOTE]
   >
   >在命名标注时，请选择一个描述性名称，该名称反映可视化类型及其显示的度量和维度。 例如，如果要从通过“日”维度显示“会话”量度的表格可视化创建标注，则可以将标注命名为“按日的会话表格”。

1. （可选）若要使该更改对工作配置文件的所有用户可用：

   1. 在中， [!DNL Profile Manager]单击， **[!UICONTROL Context]**&#x200B;然后单击 **[!UICONTROL Callout]**。 This folder contains all of the visualization files ( [!DNL .vw]) that define the existing callout types.

   1. Right-click the check mark next to the file name of the new callout in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**将标注更改为量度标注**

1. 在中， [!DNL Profile Manager]单击， **[!UICONTROL Context]**&#x200B;然后单击 **[!UICONTROL Callout]**。 This folder contains all of the visualization files ( [!DNL .vw]) that define the existing callout types.

1. Right-click the check mark next to the file name of the type of callout that you want to change and click **[!UICONTROL Make Local]**. After the file has been downloaded to the local computer, a check mark appears in the [!DNL User] column.

1. Right-click the check mark next to the file name in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Locate the [!DNL metric_y = ref:] entry in the callout file and replace the existing value with the word Metric. 以下文件片段中突出显示的文本显示了应插入该词语的位置。

   ```
   window = simpleBorderWindow: 
     client = graph: 
       bars = bool: true
       dim_x = ref: wdata/model/dim/dimension name
       lines = bool: false
       metrics = vector: 1 items
         0 = gr_metric: 
           metric_y = ref: Metric
           yaxis = axisLegend: 
             max_value = double: maximum y-value
             min_value = double: minimum y-value
             zoom_max = double: maximum y-zoom
             zoom_min = double: minimum y-zoom
   . . . 
   ```

1. 单击 **[!UICONTROL File]** > **[!UICONTROL Save As]**. 在窗口 **[!UICONTROL Save As]** 中，单击一次，然后双击 **[!UICONTROL Metric Callout]**。 In the [!DNL File Name] field, type a name for the file and click **[!UICONTROL Save]**. 度量标注文件将保存到User\*工作配置文件名称*\Context\Metric Callout folder。

1. (Optional) To make this metric callout available to all users of the working profile, in the [!DNL Profile Manager], right-click the check mark next to the file name in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

