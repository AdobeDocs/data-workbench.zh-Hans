---
description: 如果使用 Categorize 或 FlatFileLookup 转换，对照表将加载到内存并从无格式文件填充，该文件的位置在定义转换时指定。
title: 填充对照表
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
exl-id: e83d9feb-44fe-4fa1-b559-e1f5606637b5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 95%

---

# 填充对照表{#populating-the-lookup-table}

如果使用 Categorize 或 FlatFileLookup 转换，对照表将加载到内存并从无格式文件填充，该文件的位置在定义转换时指定。

指定的无格式文件必须符合以下要求：

* 文件中的每行必须表示对照表中的一个行。
* 文件中的列必须由 ASCII 分隔符分隔。您可以使用任意不属于行结束字符，并且不会出现在事件数据本身任何位置的字符。在定义转换时，请指定哪个字符已用于分隔无格式文件中的列。

如果使用 [!DNL ODBCLookup] 转换，对照表将加载到内存并从您指定的 [!DNL ODBC] 数据库中的表或视图填充。在定义转换时，还必须指定 Data Workbench Server 建立数据库连接时必须使用的数据源、用户名和密码。

>[!NOTE]
>
>当Data Workbench Server最初开始构建数据集时，将加载查找表。 建立好之后，对照文件将不会更改。如果更改用于转换阶段的无格式文件或 [!DNL ODBC] 表，则需要重新转换整个数据集。如果更改在日志处理阶段使用的无格式文件，则新的对照数据将应用于所有进入数据集的新记录，但不会逆向应用更改。
