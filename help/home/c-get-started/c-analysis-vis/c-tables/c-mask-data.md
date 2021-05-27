---
description: 掩盖指的是选择您数据的子集或某个维度中元素的子集。
title: 数据掩码
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
exl-id: 3029e08e-827f-40d7-b5a1-45630876a097
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 66%

---

# 数据掩码{#mask-data}

掩盖指的是选择您数据的子集或某个维度中元素的子集。

您可以掩盖或隐藏不希望在分析中包含的那些元素。

Data Workbench提供了两种掩盖维度元素的方法。 第一种方法使用[!DNL Mask]菜单中可用的选项。 使用[!DNL Mask]菜单选项，您可以使用鼠标选择要显示或掩盖的元素，或者在按量度对数据进行排序时显示排名靠前的元素。 掩盖维度元素的第二种方法是利用搜索。

**掩盖数据**

1. 右键单击所需维度的元素或标签，然后单击&#x200B;**[!UICONTROL Mask]**。

   ![](assets/mnu_Table_Mask.png)

1. 单击以下选项之一：

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]**，或显示 **[!UICONTROL 500]** 的按量度排序的元素
   * **[!UICONTROL Show top > All Positive]** 仅显示大于零(0)的值
   * **[!UICONTROL Display “X more”]** 显示当前被屏蔽的元素的数量
   * **[!UICONTROL At least one >]***&lt;>>*（仅在使用非正规维度时可用）**[!UICONTROL countable dimension name]**

      使用非正规维度时，使用此选项，可以通过可计数的维度来掩盖维度。选择时，表格只显示至少具有您所选择的可计数维度的一个元素的那些元素。表格最多显示 1,023 个元素。

>[!NOTE]
>
>由于Adobe[!DNL Platform]按随机顺序处理数据，因此当至少一个掩码结果导致超过1,023个元素时，比较常见和较大的元素更有可能包含在表中。

当您通过“显示前”或“至少一个”来掩盖时，默认情况下表格中的顺序与此时受选择影响的值相对应。如果您稍后更改选择，则顺序不会从原始顺序发生更改，除非对表格重新进行了排序或者启用“动态选择”。单击&#x200B;**[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**&#x200B;后，每次更改选择时都会对表重新排序。

**使用搜索掩盖数据**

* 可以使用以下搜索选项之一掩盖数据：

   * 右键单击所需维度的元素或标签，单击&#x200B;**[!UICONTROL Mask]**，然后在[!DNL Search]框中键入要搜索的短语。

      ![](assets/mnu_Table_MaskSearch.png)

   * 右键单击所需维度的元素或标签，单击&#x200B;**[!UICONTROL Mask]** > **[!UICONTROL Display search bar]**，然后在维度标签单元格中显示的搜索框中，键入要搜索的短语。

      ![](assets/vis_Table_Mask_searchBar.png)

      在键入搜索短语时，Data Workbench会更新维度以反映匹配项。

若要在搜索期间进一步约束掩盖，则可以使用以下任一方法：

* 您可以在[!DNL search]框或栏中键入“re：”，以将搜索短语解释为正则表达式。 可以在搜索短语中使用与正则表达式相关的任何语法。有关正则表达式的详细信息，请参阅《数据集配置指南》**&#x200B;中的“正则表达式”附录。
* 可以键入 $ 符号作为搜索字符串中的第一个字符，以查找以所输入字符串开头的短语，或作为最后一个字符，以查找以所输入字符串结尾的短语。
* 可以键入空格作为搜索字符串中的第一个字符，以查找以所输入字符串开头的短语中的任何单词，或作为最后一个字符，以查找以所输入字符串结尾的短语中的任何单词。

以下示例采用不同的方法通过在搜索中使用字符串“on”来掩盖表格：

* 键入“on”显示在任意位置包含字符串“on”的每个短语：“**on** line banking”、“c **on** tact buyers”、“bulli **on** coins”、“bank **on** line”、“gold opti **on** s”和“silver bulli **on**”。
* 键入“$on”显示以字符串“on”开头的每个短语：

   “**on** line banking”和“**on**-line payment”。

* 键入“on$”显示以字符串“on”结尾的每个短语：

   “silver bulli **on**”和“gold opti **on**”。

* 键入“ on”显示包含以字符串“on”开头的单词的每个短语：

   “**on** line banking”和“bank **on** line”。

* 键入“on ”显示包含以字符串“on”结尾的单词的每个短语：

   “bulli **on** coins”和“silver bulli **on**”。

* 使用“ on ”显示包含单词形式的字符串“on”的每个短语：

   “**on** line banking”和“bank **on** line”。
