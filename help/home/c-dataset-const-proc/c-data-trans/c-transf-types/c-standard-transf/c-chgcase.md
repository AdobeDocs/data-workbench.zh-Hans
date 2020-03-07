---
description: ChangeCase 转换根据 Action（操作）参数的指定更改 Input（输入）参数中字符串的大小写。
solution: Analytics
title: ChangeCase
topic: Data workbench
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ChangeCase{#changecase}

ChangeCase 转换根据 Action（操作）参数的指定更改 Input（输入）参数中字符串的大小写。

| 参数 | 描述 | 默认值 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| Action（操作） | 大写或小写。指定将大小写更改为大写还是小写。 | 小写 |
| Comments（备注） | 可选。有关转换的说明。 |  |
| Condition（条件） | 应用此转换的条件。 |  |
| Input（输入） | 日志条目中用作输入的字段名称。 |  |
| Output（输出） | 输出字段的名称。 |  |

此示例使用了从网站流量收集的数据字段，其中，s-dns 字段中的字符串大小写更改为小写，并在新字段 x-lowercase-dns 中输出新值。

![](assets/cfg_TransformationType_ChangeCase.png)

