---
description: 对数据排序的步骤。
solution: Analytics
title: 对表中的数据排序
topic: Data workbench
uuid: 66869478-922d-41e1-915d-3ed7bff3b08d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 对表中的数据排序{#sort-data-in-a-table}

对数据排序的步骤。

如果表格只有一个维度，则只需单击要在其上对数据进行排序的量度的标签。

1. Right-click an element or the label of the dimension that you want to sort and click **[!UICONTROL Sort]**.

   ![](assets/mnu_Table_Sort.png)

1. 单击以下选项之一：

   * **[!UICONTROL By ordinal]** 按元素的自然顺序对元素进行排序。 例如，“小时”维度的元素按时间顺序显示。如果维度没有自然顺序（如推荐人或 URI），则排序不起作用，因此您应该选择按字母顺序或按量度进行排序。
   * **[!UICONTROL Alphabetically]** 按元素名称的字母顺序排序维。
   * **[!UICONTROL By metric]** ，以选择数据排序依据的度量。 例如，您可以按“会话”量度对“推荐人”维度进行排序，以查看哪个推荐人在您的网站上贡献了最多会话。

      当您按量度进行排序时，默认情况下表格中的顺序与此时受选择影响的量度的值相对应。如果您稍后更改选择，则排序的顺序不会从原始顺序发生更改，除非对维度重新进行了排序或者启用“动态选择”。When you click **[!UICONTROL Sort]** > **[!UICONTROL Dynamic Selection]**, the table is resorted each time you change the selection.
   若要按表格中的现有量度排序，请单击该量度标签。

1. (Optional) To choose whether to sort in ascending or descending order, right-click an element or the label of the dimension that you want to sort and click **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Ascending]** or **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Descending]**.

   如果表格只有一个维度，则只需单击量度的标签即可反转排序顺序。再次单击标签可反转排序顺序。

