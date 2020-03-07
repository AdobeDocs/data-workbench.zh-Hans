---
description: 有关指定输出格式的准则。
solution: Analytics
title: 输出格式
topic: Data workbench
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Output format{#output-format}

有关指定输出格式的准则。

* 每个量度或维度的名称必须以百分号 (%) 开头和结尾。

   * %XYZ% 指定与“级别”中元素对应的维度 XYZ 的元素。如果维度 XYZ 与“级别”不是一对一或一对多关系，则会发生错误。
   * %=XYZ% 为给定的“级别”元素指定量度值或量度公式 XYZ 值。

* 包含两个或更多单词的维度名称无需添加下划线。
* 包含两个或更多单词的量度名称需要添加下划线。

>[!NOTE]
>
>If you hold down the Ctrl key and right-click within the [!DNL Output Format] field, an [!DNL Insert menu] appears. 该菜单包含通常用作分隔符的特殊字符（例如，制表符）列表。

如果要导出区段的会话持续时间数据，则必须创建一个基于“会话持续时间”量度的新量度。The new metric, which is for use only with the [!DNL Output Format] field of segment export, enables Microsoft Excel to correctly interpret sessions lasting less than one hour. To create a new session duration metric, open the [!DNL Session Duration.metric] file (from the [!DNL Profile Manager]) and insert a pound sign (#) into the ftime string: [!DNL ftime = string: %#H:%M:%S]

该英镑符号导致在不足一小时的会话持续时间前附加一个前导“0”。因此，Excel 将 0:53:21 解释为 53 分 21 秒。Save the new metric with a different name and upload it to the appropriate profile for others to use by right-clicking the check mark for the file in the [!DNL User] column and clicking **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
