---
description: 对数据排序的步骤。
title: 对表中的数据排序
uuid: 66869478-922d-41e1-915d-3ed7bff3b08d
exl-id: 9cacb9bc-1bad-417b-b506-ca54e644de00
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 70%

---

# 对表中的数据排序{#sort-data-in-a-table}

{{eol}}

对数据排序的步骤。

如果表格只有一个维度，则只需单击要在其上对数据进行排序的量度的标签。

1. 右键单击要排序的维度的元素或标签，然后单击 **[!UICONTROL Sort]**.

   ![](assets/mnu_Table_Sort.png)

1. 单击以下选项之一：

   * **[!UICONTROL By ordinal]** ，以根据元素的自然顺序对元素进行排序。 例如，“小时”维度的元素按时间顺序显示。如果维度没有自然顺序（如推荐人或 URI），则排序不起作用，因此您应该选择按字母顺序或按量度进行排序。
   * **[!UICONTROL Alphabetically]** 按元素名称的字母顺序对维度进行排序。
   * **[!UICONTROL By metric]** ，以选择要按其对数据进行排序的量度。 例如，您可以按“会话”量度对“推荐人”维度进行排序，以查看哪个推荐人在您的网站上贡献了最多会话。

      当您按量度进行排序时，默认情况下表格中的顺序与此时受选择影响的量度的值相对应。如果您稍后更改选择，则排序的顺序不会从原始顺序发生更改，除非对维度重新进行了排序或者启用“动态选择”。单击 **[!UICONTROL Sort]** > **[!UICONTROL Dynamic Selection]**，则每次更改选择时都会对表重新排序。
   若要按表格中的现有量度排序，请单击该量度标签。

1. （可选）要选择是按升序排序还是按降序排序，请右键单击要排序的维度的元素或标签，然后单击 **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Ascending]** 或 **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Descending]**.

   如果表格只有一个维度，则只需单击量度的标签即可反转排序顺序。再次单击标签可反转排序顺序。
