---
description: 更改默认可视化的步骤。
title: 配置数据集架构界面
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 46%

---

# 配置数据集架构界面{#configure-the-dataset-schema-interface}

更改默认可视化的步骤。

通过向Profiles\*配置文件名称*\Context\Dimension Legend folder of the Data Workbench server installation folder添加文件，您可以控制在[!DNL Dataset Schema Interface]中单击某个维度名称时显示的可视化类型。 该文件夹中的 [!DNL Default.1d] 文件控制所有维度的默认可视化类型。通过向该文件夹添加&#x200B;*维度名称*. 文件（例如 [!DNL Hour.1d].1d），可以控制该特定维度的默认可视化。

有关[!DNL Dataset Schema Interfaces]的更多信息，请参阅[数据集架构界面](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)。

**更改默认可视化**

1. 在任何工作区中创建一个可视化，其中包含您希望在新的默认可视化中显示的数据。

   例如，如果您希望维度显示在条形图中，则创建一个显示所需量度和维度的条形图可视化。

1. 右键单击标注窗口的上边框，然后单击&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Save]窗口中，单击![](assets/btn_folder_up.png)，双击&#x200B;**[!UICONTROL Context]**，然后双击&#x200B;**[!UICONTROL Dimension Legend]**。
1. 在[!DNL File Name]字段中，键入维度名称。

   [!DNL .1d]文件的名称必须与维度的名称完全匹配。 例如：[!DNL Hour.1d]。

1. 将文件扩展名更改为“1d”，然后单击&#x200B;**[!UICONTROL Save]**。

   该文件将保存到User\*工作配置文件名称*\Context\Dimension Legend folder文件夹中。

   下次在[!DNL Dataset Schema Interface]中单击该维度时，将显示您指定的可视化。

1. （可选）若要使该更改对工作配置文件的所有用户可用：

   1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Context]**，然后单击&#x200B;**[!UICONTROL Dimension Legend]**。

   1. 右键单击[!DNL User]列中新标注文件名旁边的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL working profile name]**>*。
