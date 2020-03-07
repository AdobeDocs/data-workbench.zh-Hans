---
description: 掩盖指的是选择您数据的子集或某个维度中元素的子集。
solution: Analytics
title: 遮罩数据
topic: Data workbench
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 遮罩数据{#mask-data}

掩盖指的是选择您数据的子集或某个维度中元素的子集。

您可以掩盖或隐藏不希望在分析中包含的那些元素。

Data Workbench提供了两种蒙版维元素的方法。 The first method employs the options available in the [!DNL Mask] menu. Using the [!DNL Mask] menu options, you can use your mouse to select those elements to show or to mask, or you can show top-ranked elements when you sort the data by metric. 掩盖维度元素的第二种方法是利用搜索。

**遮罩数据**

1. Right-click an element or the label of the desired dimension and click **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. 单击以下选项之一：

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]**，或显示 **[!UICONTROL 500]** 的按量度排序的元素中
   * **[!UICONTROL Show top > All Positive]** 仅显示大于零(0)的值
   * **[!UICONTROL Display “X more”]** 显示当前被遮罩的元素的数量
   * **[!UICONTROL At least one >]***&lt; **[!UICONTROL countable dimension name]**>*（仅在处理非正规维时可用）

      使用非正规维度时，使用此选项，可以通过可计数的维度来掩盖维度。选择时，表格只显示至少具有您所选择的可计数维度的一个元素的那些元素。表格最多显示 1,023 个元素。

>[!NOTE]
>
>Because the Adobe [!DNL Platform] processes data in random order, when At least one masking results in more than 1,023 elements, the more common and larger elements have a greater chance of being included in the table.

当您通过“显示前”或“至少一个”来掩盖时，默认情况下表格中的顺序与此时受选择影响的值相对应。如果您稍后更改选择，则顺序不会从原始顺序发生更改，除非对表格重新进行了排序或者启用“动态选择”。When you click **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**, the table is resorted each time you change the selection.

**使用搜索掩盖数据**

* 可以使用以下搜索选项之一掩盖数据：

   * Right-click an element or the label of the desired dimension, click **[!UICONTROL Mask]**, then in the [!DNL Search] box type the phrase for which you want to search.

      ![](assets/mnu_Table_MaskSearch.png)

   * Right-click an element or the label of the desired dimension, click **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]**, then in the search box that displays in the dimension label cell, type the phrase for which you want to search.

      ![](assets/vis_Table_Mask_searchBar.png)

      在键入搜索短语时，Data Workbench会更新维以反映匹配项。

若要在搜索期间进一步约束掩盖，则可以使用以下任一方法：

* You can type “re:” in the [!DNL search] box or bar to have the search phrase interpreted as a regular expression. 可以在搜索短语中使用与正则表达式相关的任何语法。有关正则表达式的详细信息，请参阅《数据集配置指南》**&#x200B;中的“正则表达式”附录。
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

