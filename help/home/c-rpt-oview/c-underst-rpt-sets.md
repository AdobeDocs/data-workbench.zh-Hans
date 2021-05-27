---
description: 报表集是Report Server根据Report.cfg配置文件中指定的值生成的工作区集合。
title: 了解报表集
uuid: 421055d7-0cf0-4664-b944-327a254a97a4
exl-id: 95609a1a-e70c-41e2-ace3-0cb09f77705a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---

# 了解报表集{#understanding-report-sets}

报表集是Report Server根据Report.cfg配置文件中指定的值生成的工作区集合。

在[!DNL Insight]安装文件夹中，&lt;*工作配置文件名称*>\Reports文件夹中的每个子文件夹都表示已创建的报表集。 每个报表集在该子文件夹中都有其自己的[!DNL Report.cfg]配置文件。

>[!NOTE]
>
>在Data Workbench的[!DNL Profile Manager]文件夹中，报表集显示为子文件夹。 [!DNL Reports]有关[!DNL Profile Manager]的详细信息，请参阅[Data Workbench用户指南](https://docs.adobe.com/content/help/en/data-workbench/using/home.html#Data_Workbench_Help)。

通过在[!DNL Report.cfg]文件中为报表集定义特定配置设置，可以安排报表的创建和分发，包括谁接收哪些报表以及以什么格式接收报表。
