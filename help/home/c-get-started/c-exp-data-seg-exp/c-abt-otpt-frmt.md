---
description: 有关指定输出格式的准则。
title: 输出格式
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
exl-id: e695eaf4-ebe5-4dd1-8191-8045021d6411
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 59%

---

# 输出格式{#output-format}

{{eol}}

有关指定输出格式的准则。

* 每个量度或维度的名称必须以百分号 (%) 开头和结尾。

   * %XYZ% 指定与“级别”中元素对应的维度 XYZ 的元素。如果维度 XYZ 与“级别”不是一对一或一对多关系，则会发生错误。
   * %=XYZ% 为给定的“级别”元素指定量度值或量度公式 XYZ 值。

* 包含两个或更多单词的维度名称无需添加下划线。
* 包含两个或更多单词的量度名称需要添加下划线。

>[!NOTE]
>
>如果按住Ctrl键并在 [!DNL Output Format] 字段， [!DNL Insert menu] 中。 该菜单包含通常用作分隔符的特殊字符（例如，制表符）列表。

如果要导出区段的会话持续时间数据，则必须创建一个基于“会话持续时间”量度的新量度。新量度，仅用于 [!DNL Output Format] 区段导出字段中，使Microsoft Excel能够正确解释持续时间少于一小时的会话。 要创建新的会话持续时间量度，请打开 [!DNL Session Duration.metric] 文件(从 [!DNL Profile Manager])并在ftime字符串中插入井号(#): [!DNL ftime = string: %#H:%M:%S]

该英镑符号导致在不足一小时的会话持续时间前附加一个前导“0”。因此，Excel会将0:53:21秒53分21秒。 使用其他名称保存新量度，并将其上传到相应的配置文件以供他人使用，方法是右键单击 [!DNL User] 列，单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
