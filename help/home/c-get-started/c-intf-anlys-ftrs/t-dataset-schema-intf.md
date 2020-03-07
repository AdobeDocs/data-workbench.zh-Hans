---
description: 更改默认可视化的步骤。
solution: Analytics
title: 配置数据集架构界面
topic: Data workbench
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Configure the Dataset Schema Interface{#configure-the-dataset-schema-interface}

更改默认可视化的步骤。

You can control which type of visualization displays when you click a dimension name in a [!DNL Dataset Schema Interface] by adding files to the Profiles\*profile name*\Context\Dimension Legend folder of the Data Workbench server installation folder. 该文件夹中的 [!DNL Default.1d] 文件控制所有维度的默认可视化类型。通过向该文件夹添加&#x200B;*维度名称*. 文件（例如 [!DNL Hour.1d].1d），可以控制该特定维度的默认可视化。

有关详细信息， [!DNL Dataset Schema Interfaces]请参 [阅数据集架构界面](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)。

**更改默认可视化**

1. 在任何工作区中创建一个可视化，其中包含您希望在新的默认可视化中显示的数据。

   例如，如果您希望维度显示在条形图中，则创建一个显示所需量度和维度的条形图可视化。

1. Right-click the top border of the callout window and click **[!UICONTROL Save]**.
1. 在窗 [!DNL Save] 口中，单 ![](assets/btn_folder_up.png)击，双击 **[!UICONTROL Context]**，然后双击 **[!UICONTROL Dimension Legend]**。
1. In the [!DNL File Name] field, type the dimension name.

   The name of the [!DNL .1d] file must match the name of the dimension exactly. 例如：[!DNL Hour.1d]。

1. Change the file extension to “1d” and click **[!UICONTROL Save]**.

   该文件将保存到User\*工作配置文件名称*\Context\Dimension Legend folder。

   The next time that you click that dimension from in a [!DNL Dataset Schema Interface], the visualization that you specified displays.

1. （可选）若要使该更改对工作配置文件的所有用户可用：

   1. 在中， [!DNL Profile Manager]单击， **[!UICONTROL Context]**&#x200B;然后单击 **[!UICONTROL Dimension Legend]**。

   1. Right-click the check mark next to the file name of the new callout in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

