---
description: 与 AppendURI 转换类似，PrependURI 转换影响 Data Workbench Server 用于构建 URI 维度的内部字段。
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 100%

---

# PrependURI{#prependuri}

{{eol}}

与 AppendURI 转换类似，PrependURI 转换影响 Data Workbench Server 用于构建 URI 维度的内部字段。

[!DNL PrependURI] 转换的工作方式是将标识输入字段中的值添加到 URI 中当前值的前面。

| 参数 | 描述 | 默认 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| 评论 | 可选。有关转换的说明。 |  |
| 条件 | 应用此转换的条件。 |  |
| 默认 | 在满足条件但输入值不可用时所使用的默认值。 |  |
| Input（输入） | 其值附加到 URI 前面的字段名称。 |  |

以下示例仅将 s-dns 字段附加到 URI 前面，从而将 URI 维度的表示形式扩展为包括客户端设备请求的域。

![](assets/cfg_TransformationType_PrependURI.png)

在此示例中，将 s-dns 字段附加到以下 URI 的前面：

* [!DNL /modelview.asp&id=login]

结果得到以下 URL：

* [!DNL www.adobe.com/modelview.asp?id=login]

现在便将 URI 扩展为包括请求的域。
