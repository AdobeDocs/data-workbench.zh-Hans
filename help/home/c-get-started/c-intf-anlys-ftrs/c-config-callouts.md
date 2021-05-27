---
description: 通过使用可视化中特定维度元素的虚拟选择创建新的可视化，标注可以使用户注意某个特定的维度元素。
title: 配置标注
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 37%

---

# 配置标注{#configure-a-callout}

通过使用可视化中特定维度元素的虚拟选择创建新的可视化，标注可以使用户注意某个特定的维度元素。

您可以通过配置存储在Profiles\*profile name*\Context\Callout folder of the [!DNL Server]安装文件夹中的标注文件来添加或编辑标注。 使用户注意工作表可视化中特定量度的标注称为量度标注。量度标注文件存储在Profiles\*配置文件名称*\Context\Metric Callout folder文件夹中。

有关向可视化添加标注或量度标注的说明，请参阅[向工作区添加标注](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0)。

**创建新的标注类型**

1. 在任何工作区中创建一个可视化，其中包含您希望以新标注类型显示的数据。例如，如果您要创建表格型标注，则创建一个显示所需量度和维度的表格可视化。
1. 右键单击标注窗口的上边框，然后单击&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Save]窗口中，单击![](assets/btn_folder_up.png)，双击&#x200B;**[!UICONTROL Context]**，然后双击&#x200B;**[!UICONTROL Callout]**。 在[!DNL File Name]字段中，键入文件的名称，然后单击&#x200B;**[!UICONTROL Save]**。 标注文件将保存到User\*工作配置文件名称*\Context\Callout folder文件夹中。

   >[!NOTE]
   >
   >在命名标注时，请选择一个描述性名称，该名称反映可视化类型及其显示的量度和维度。 例如，如果要从通过“日”维度显示“会话”量度的表格可视化创建标注，则可以将标注命名为“按日的会话表格”。

1. （可选）若要使该更改对工作配置文件的所有用户可用：

   1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Context]**，然后单击&#x200B;**[!UICONTROL Callout]**。 此文件夹包含定义现有标注类型的所有可视化文件([!DNL .vw])。

   1. 右键单击[!DNL User]列中新标注文件名旁边的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL working profile name]**>*。

**将标注更改为量度标注**

1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Context]**，然后单击&#x200B;**[!UICONTROL Callout]**。 此文件夹包含定义现有标注类型的所有可视化文件([!DNL .vw])。

1. 右键单击要更改的标注类型文件名旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 将文件下载到本地计算机后，[!DNL User]列中会出现复选标记。

1. 右键单击[!DNL User]列中文件名旁边的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL In Notepad]**。

1. 在标注文件中找到[!DNL metric_y = ref:]条目，并将现有值替换为单词“Metric”。 以下文件片段中突出显示的文本显示了应插入该词语的位置。

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

1. 单击 **[!UICONTROL File]** > **[!UICONTROL Save As]**. 在&#x200B;**[!UICONTROL Save As]**&#x200B;窗口中，单击一次，然后双击&#x200B;**[!UICONTROL Metric Callout]**。 在[!DNL File Name]字段中，键入文件的名称，然后单击&#x200B;**[!UICONTROL Save]**。 量度标注文件将保存到User\*工作配置文件名称*\Context\Metric Callout folder文件夹中。

1. （可选）若要使此量度标注对工作配置文件的所有用户可用，请在[!DNL Profile Manager]中右键单击[!DNL User]列中文件名旁边的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL working profile name]**>*。
